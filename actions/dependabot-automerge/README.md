# dependabot-automerge

Composite action that approves and squash-merges **Dependabot** pull requests
for **`github-actions`** dependencies when the bump is a **patch** or **minor**
update. Major bumps and every other ecosystem are left open for manual review.

## What it does

| Dependabot PR | Result |
| --- | --- |
| `github-actions` · patch (`7.0.0 → 7.0.1`) | ✅ approved, squash-merged |
| `github-actions` · minor (`7.0.0 → 7.1.0`) | ✅ approved, squash-merged |
| `github-actions` · major (`7.x → 8.0.0`) | ❌ left open |
| any other ecosystem (npm, composer, …) | ❌ left open |
| non-Dependabot PR | ❌ ignored |

## Usage in another repository

Add a workflow that runs on Dependabot PRs and calls this action. No checkout is
needed — the action is pulled from `he4rt/.github`.

```yaml
# .github/workflows/dependabot-automerge.yml
name: Dependabot auto-merge

on:
  # zizmor: ignore[dangerous-triggers] — no PR code is executed, only metadata + API calls
  pull_request_target:
    branches: [main] # match your default branch

permissions: {}

jobs:
  automerge:
    name: Auto-merge Dependabot patch & minor
    runs-on: ubuntu-latest
    if: github.event.pull_request.user.login == 'dependabot[bot]'
    timeout-minutes: 5
    permissions:
      contents: write # squash-merge the PR
      pull-requests: write # approve the PR
    steps:
      - uses: he4rt/.github/actions/dependabot-automerge@main # pin to a commit SHA in production
```

> `pull_request_target` is required: Dependabot PRs get a read-only token under
> `pull_request` and cannot merge. This workflow does not check out PR code, so
> the trigger is safe.

## Requirements

- **Settings → Actions → General → "Allow GitHub Actions to create and approve
  pull requests"** must be enabled for the approval step.
- The merge uses plain `gh pr merge --squash`, which merges immediately and only
  needs `contents: write`. If the target repo has **branch protection with
  required checks**, switch the action's merge command to `gh pr merge --auto`
  so it waits for green checks instead.

## How it works

1. [`dependabot/fetch-metadata`](https://github.com/dependabot/fetch-metadata)
   reads `package-ecosystem` and `update-type`.
2. If `package-ecosystem == github_actions` and the update is patch or minor,
   the PR is approved and squash-merged.
