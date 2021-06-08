# ⚡️ Pull request name linter with commitlint ⚡️
---
[![build](https://github.com/cognitedata/lint-pr-title-action/workflows/build/badge.svg)](https://github.com/cognitedata/lint-pr-title-action/actions)
[![test](https://github.com/cognitedata/lint-pr-title-action/workflows/test/badge.svg)](https://github.com/cognitedata/lint-pr-title-action/actions)
[![GitHub issues](https://img.shields.io/github/issues/cognitedata/lint-pr-title-action?style=flat-square)](https://github.com/cognitedata/lint-pr-title-action/issues)
[![GitHub forks](https://img.shields.io/github/forks/cognitedata/lint-pr-title-action?style=flat-square)](https://github.com/cognitedata/lint-pr-title-action/network)
[![GitHub stars](https://img.shields.io/github/stars/cognitedata/lint-pr-title-action?style=flat-square)](https://github.com/cognitedata/lint-pr-title-action/stargazers)
[![GitHub license](https://img.shields.io/github/license/cognitedata/lint-pr-title-action?style=flat-square)](https://github.com/cognitedata/lint-pr-title-action/blob/master/LICENSE)
[![Watch on GitHub](https://img.shields.io/github/watchers/cognitedata/lint-pr-title-action.svg?style=social)](https://github.com/cognitedata/lint-pr-title-action/watchers)
[![Tweet](https://img.shields.io/twitter/url/https/github.com/cognitedata/lint-pr-title-action.svg?style=social)](https://twitter.com/intent/tweet?text=Checkout%20this%20library%20https%3A%2F%2Fgithub.com%2Fcognitedata%2Flint-pr-title-action)
---

**GitHub action** to automatically **lint pull request name** with [**commitlint**](https://commitlint.js.org).

**Note**: If you are looking to lint the commits of your pull request with commitlint you can use [commitlint-github-action](https://github.com/wagoid/commitlint-github-action)

This package are using the commitlint 12 version

## Configuration

## Usage

### Create `.github/workflows/pr-name.yml`

Create a workflow (eg: `.github/workflows/pr-name.yml` see [Creating a Workflow file](https://help.github.com/en/articles/configuring-a-workflow#creating-a-workflow-file)).
Here is an example of configuration

```yaml
name: pr-name-linter
on:
  pull_request:
    types: ['opened', 'edited', 'reopened', 'synchronize']

jobs:
  lint:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v2
    - name: Install Dependencies
      run: npm install @commitlint/config-conventional
    - uses: cognitedata/lint-pr-title-action@v0.2.0
```

**Note**: make sure you install your dependencies that commitlint use 
