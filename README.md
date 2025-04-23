# Python Poetry Setup

![Latest Release](https://img.shields.io/github/v/release/p6m-actions/python-poetry-setup?style=flat-square&label=Latest%20Release&color=blue)

## Description

A GitHub Action that automates the setup of Poetry (Python package manager) with built-in caching support for both Poetry installation and virtual environments. This action handles the installation of Poetry and configures caching to improve workflow execution times.

The action automatically handles:

- Poetry installation caching via pipx
- Virtual environment caching
- Version management

## Usage

Add the following step to your GitHub Actions workflow:

```yaml
- uses: p6m-actions/python-poetry-setup@v1
  with:
    version: "1.4.2" # Optional: Specify Poetry version
```

## Inputs

| Input   | Required | Default | Description                                          |
| ------- | -------- | ------- | ---------------------------------------------------- |
| version | false    | latest  | Specific version of Poetry to install (e.g. '1.4.2') |

## Outputs

| Output  | Description                                     |
| ------- | ----------------------------------------------- |
| version | The actual version of Poetry that was installed |

## Examples

Basic usage with latest Poetry version:

```yaml
steps:
  - uses: actions/checkout@v3
  - uses: p6m-actions/python-poetry-setup@v1
  - run: poetry install
```

Specify Poetry version:

```yaml
steps:
  - uses: actions/checkout@v3
  - uses: p6m-actions/python-poetry-setup@v1
    with:
      version: "1.4.2"
  - run: poetry install
```
