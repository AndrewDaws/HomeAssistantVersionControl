# Contributing to Home Assistant Version Control

Thanks for your interest in contributing!

## Where to Submit PRs

| Type of Change | Target Branch |
|----------------|---------------|
| **New features** | `develop` |
| **Bug fixes** for current stable | `main` (or `develop` if it affects beta) |
| **Documentation** | Either branch is fine |

### How to Change PR Target

When creating a PR, use the "base" dropdown to select `develop` instead of `main`.

If you've already created a PR targeting `main`, you can change it by clicking "Edit" next to the base branch on the PR page.

## Development Workflow

1. Fork the repository
2. Create a feature branch from `develop`
3. Make your changes
4. Submit a PR targeting `develop`
5. Your changes will be tested in beta, then merged to `main` for stable releases

## Release Process

| Environment | Branch | Docker Tag | Repo |
|-------------|--------|------------|------|
| **Beta** | `develop` | `beta` | `ha-addons-beta` |
| **Stable** | `main` | `latest` | `ha-addons` |

- **For Beta Tracking:** Simply push to the `develop` branch.
- **For Official Release:** Merge `develop` → `main`, then create a **GitHub Release** on `main`. This will tag the image with the version number and update `latest`.

## Questions?

Open an issue if you're unsure where your contribution should go!
