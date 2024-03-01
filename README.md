# Monorepo Semantic Release Project

This repository is a monorepo containing multiple packages, including a design system and potentially other shared libraries or applications. We use `semantic-release` with the `semantic-release-monorepo` configuration to automate versioning and release processes based on conventional commit messages.

## Structure

The monorepo is structured into two main directories:

- `/packages` - Contains individual packages, each with its own lifecycle and versioning.
  - `/design-system` - Houses our shared design system components.
  - `/another-package` - An example of another package within the monorepo.
- `/apps` - Contains React applications or other types of applications that may consume the packages within `/packages`.

## Getting Started

To get started with this monorepo, ensure you have [Yarn](https://yarnpkg.com/) installed, as we use Yarn Workspaces for dependency management.

```bash
# Clone the repository
git clone https://github.com/vale-c/semantic-release-monorepo.git

# Install dependencies
yarn install

# Run an application (example)
yarn workspace app_one start
```

## Semantic Release

Each package in `/packages` can be independently versioned and released using `semantic-release`. The `.releaserc.json` configuration file within each package directory specifies the release process for that package.

### Commit Message Convention

We adhere to the [Conventional Commits](https://www.conventionalcommits.org/) specification for commit messages. This standard allows us to automate versioning and CHANGELOG generation.

Examples:

```bash
# Adding a new feature
git commit -m "feat(design-system): add new button variant"

# Fixing a bug
git commit -m "fix(app-one): resolve routing issue"

# Making non-functional changes (e.g., formatting)
git commit -m "chore: run prettier on all files"
```

### Triggering Releases

Releases are triggered automatically via our CI/CD pipeline on merges to the `main` branch. Ensure your commits follow the conventional commit format to correctly version and release updates.

## Development Workflow

1. **Start Development**: Work on your changes in a new branch.
2. **Commit Changes**: Use conventional commit messages to describe your changes.
3. **Open a Pull Request**: Merge your changes into the `main` branch through a pull request.
4. **CI/CD Pipeline**: Our pipeline runs tests, lints, and other checks. If everything passes, the changes will be merged.
5. **Automatic Release**: `semantic-release` analyzes commit messages and triggers a release if necessary.

