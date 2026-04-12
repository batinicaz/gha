# GHA
Repository containing re-usable workflows & actions for use within GitHub actions.

<!-- TOC -->
* [GHA](#gha)
  * [Workflows](#workflows)
  * [Actions](#actions)
<!-- TOC -->

## Workflows

- [Release](docs/workflows/release): Automated creation of tagged versions when merging to main branch.
- [Terraform Docs](docs/workflows/terraform-docs): Updates terraform-docs output on Renovate branches using a GitHub App token.

## Actions

- [pre-commit](docs/actions/pre-commit): Installs tooling and runs pre-commit hooks.
- [setup-terraform-docs](docs/actions/setup-terraform-docs): Installs the terraform-docs binary from GitHub releases.
