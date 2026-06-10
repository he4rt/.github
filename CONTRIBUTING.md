# Contributing to He4rt Developers

Thank you for your interest in contributing! Whether you're fixing a typo, reporting a bug, or building a new feature, your help is welcome here. No contribution is too small, and we value contributors of all experience levels.

This guide applies to all repositories under the [he4rt](https://github.com/he4rt) GitHub organization unless a repository provides its own `CONTRIBUTING.md` with project-specific instructions.

## Getting Started

### Prerequisites

- A [GitHub](https://github.com) account
- [Git](https://git-scm.com/) installed on your machine
- Familiarity with basic Git operations (or the willingness to learn!)

### Finding Something to Work On

- Look for issues labeled [`good first issue`](https://github.com/search?q=org%3Ahe4rt+label%3A%22good+first+issue%22+state%3Aopen&type=issues) or [`help wanted`](https://github.com/search?q=org%3Ahe4rt+label%3A%22help+wanted%22+state%3Aopen&type=issues)
- Check the repository's README for project-specific setup and open tasks
- Not sure where to start? Ask in our [Discord](https://discord.gg/he4rt) — we are happy to help

## How to Contribute

### Fork and Pull Request Workflow

1. **Fork** the repository by clicking the "Fork" button on the top right of the repo page

2. **Clone** your fork locally:
   ```bash
   git clone https://github.com/YOUR-USERNAME/REPO-NAME.git
   cd REPO-NAME
   ```

3. **Create a branch** for your changes:
   ```bash
   git checkout -b my-new-feature
   ```

4. **Make your changes** — write code, fix bugs, improve docs

5. **Stage and commit** your work:
   ```bash
   git add .
   git commit -m "Add brief description of your change"
   ```

6. **Push** your branch to your fork:
   ```bash
   git push origin my-new-feature
   ```

7. **Open a Pull Request** — go to the original repository on GitHub and click "Compare & pull request". Provide a clear title and description of what you changed and why.

### Commit Messages

- Use the imperative mood: "Add feature" not "Added feature"
- Keep the subject line under 72 characters
- Reference related issues when applicable (e.g., `Fix #42`)

### Pull Request Guidelines

- Provide a clear title and description
- Reference any related issues
- Keep changes focused — one pull request per feature or fix
- Make sure existing tests pass (if applicable)
- Be responsive to review feedback

## Reporting Bugs

Before opening a new issue, check if the bug has already been reported. If not, create a new issue including:

- A clear, descriptive title
- Steps to reproduce the behavior
- Expected behavior vs. actual behavior
- Environment details (OS, browser, language version, etc.)
- Screenshots or logs, if relevant

## Suggesting Features

We welcome ideas that improve our projects. Open an issue describing:

- The problem you want to solve
- Your proposed solution
- Any alternatives you considered

## Code Standards

Each repository may define its own code standards and tooling. When in doubt:

- Follow the existing code style in the repository
- Write clean, readable code
- Include tests when the project has a test suite
- Run any linters or formatters the project provides before submitting

## Community

- Join our [Discord](https://discord.gg/he4rt) for questions, discussions, and mentoring
- Follow us on [Twitter](https://twitter.com/He4rtDevs) for updates

## Code of Conduct

All contributors are expected to follow our [Code of Conduct](CODE_OF_CONDUCT.md). Please read it before participating.

## Security

To report security vulnerabilities, **do not open a public issue**. Please see our [Security Policy](SECURITY.md) for instructions on private reporting.

## License

By contributing to any He4rt Developers project, you agree that your contributions will be licensed under the same license as the project you are contributing to.
