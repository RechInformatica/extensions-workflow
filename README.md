# VSCode Extension Workflow

This repository contains a **centralized GitHub Actions workflow** used to:

- Automatically **bump the version** of a VSCode extension (`package.json`)
- Create and push a **git tag** based on the new version
- (Optionally) **publish** the extension to the Visual Studio Code Marketplace

---

## How to Use

To reuse this workflow in another repository (e.g., your VSCode extension), create a file like this:

### `.github/workflows/bump-version.yml`

```yaml
name: Bump version via shared workflow

on:
  push:
    branches:
      - master

jobs:
  bump:
    uses: RechInformatica/extension-workflow/.github/workflows/bump-version.yml@master
    with:
      bump: patch  # or "minor", "major"
