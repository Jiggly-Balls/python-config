<div align="center">

[![Github Releases](https://img.shields.io/github/v/release/Jiggly-Balls/python-config?color=blue&include_prereleases&label=Latest%20Release&logo=github&sort=semver&style=for-the-badge&logoColor=white)](https://github.com/Jiggly-Balls/python-config/releases)

</div>

# python-config

My configuration files for python projects.

## Table of Contents

- [Python Version and Tools](#python-version-and-tools)
- [Automation](#automation)
- [Configuration](#configurations)
  - [Ruff](#ruff-rules)
  - [Basedpyright](#basedpyright-rules)
- [Tips](#tips)

### Python Version and Tools

- Python version: 3.12
- Tools-
  - [ruff](https://docs.astral.sh/ruff) - For formatting & linting.
  - [basedpyright](https://docs.basedpyright.com/latest) - For strict type checking.

### Automation

I use Makefiles to automate running commands. If you have `make` on your system, you can run the following commands-

- `make` - For formatting, lint checking and auto fixing stuff it can.
- `make check` - For running the type checker.

### Configurations

#### Ruff Rules

- Selected-

  - [ANN](https://docs.astral.sh/ruff/rules/#flake8-annotations-ann) - Flake8 Annotations
  - [E](https://docs.astral.sh/ruff/rules/#error-e) - Error
  - [F](https://docs.astral.sh/ruff/rules/#pyflakes-f) - PyFlakes
  - [I](https://docs.astral.sh/ruff/rules/#isort-i) - Isort

- Ignored-

  - [ANN401](https://docs.astral.sh/ruff/rules/any-type) - Any Type

- Fixable-

  - [I](https://docs.astral.sh/ruff/rules/#isort-i) - Fixes all imports with ruff's isort configuration.
  - [F401](https://docs.astral.sh/ruff/rules/unused-import) - Removes all unused imports.

#### Basedpyright Rules

In basedpyright, all type checking rules are enabled by default. These are the ones disabled-

- reportImportCycles

  > Ignore import cycles for type annotations.

- reportUnnecessaryIsInstance

  > Ignore for enforcing type checks.

- reportImplicitStringConcatenation

  > Ignore for splitting long strings into multiple strings in each line for implicit concatenation.

- reportUnusedCallResult

  > Ignore to reduce verbosity in creating unused variables.

- reportMissingTypeStubs

  > Ignore for third party libraries that do not have stubs.

- reportAny

  > Ignore for third party libraries that do not support specific / explicit Any type. The `ANN` ruff linter rule will alert any untyped parameters / return value.

- reportExplicitAny

  > Ignore as explicit Any has been applied for a reason.

- reportImplicitOverride

  > To reduce verbosity.

- reportDeprecated

  > Specifically for ignoring older typing standards. This is for supporting backward compatibility in library development.

### Tips

I personally prefer to use `uv run` for running these tools, which means I also need to add them to my environment before running which I don't mind.

Others recommend using `uvx` or `uv tool run` for running CLI tools. If you don't want to have separate dev dependancies for formatting/linting/type checking,
you can use the other method.
