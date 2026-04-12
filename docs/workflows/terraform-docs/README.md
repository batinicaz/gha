# Terraform Docs

Workflow File: [terraform-docs.yml](../../../.github/workflows/terraform-docs.yml)

Reusable workflow for updating terraform-docs output on Renovate branches. Uses a GitHub App token
to push changes so that the push triggers subsequent CI workflows (e.g. lint & plan).

<!-- TOC -->
* [Terraform Docs](#terraform-docs)
  * [Features](#features)
  * [Requirements](#requirements)
  * [Usage](#usage)
    * [Configuration Reference](#configuration-reference)
<!-- TOC -->

## Features

- Installs terraform-docs via the [setup-terraform-docs](../../actions/setup-terraform-docs) action
- Optionally updates the Terraform provider lock file before generating docs
- Supports recursive processing for repos with submodules
- Pushes changes with a GitHub App token to trigger downstream CI workflows

## Requirements

- A GitHub App with `contents: write` permission, installed on the repository
- Repository secrets `DOCUMENTATION_APP_ID` and `DOCUMENTATION_PRIVATE_KEY` for the App

## Usage

Basic (single module at repo root):

```yaml
name: Update Terraform Docs
on:
  push:
    branches:
      - "renovate/**"

jobs:
  terraform-docs:
    uses: batinicaz/gha/.github/workflows/terraform-docs.yml@v1
    secrets:
      DOCUMENTATION_APP_ID: ${{ secrets.DOCUMENTATION_APP_ID }}
      DOCUMENTATION_PRIVATE_KEY: ${{ secrets.DOCUMENTATION_PRIVATE_KEY }}
```

With recursive submodules and lock file update:

```yaml
jobs:
  terraform-docs:
    uses: batinicaz/gha/.github/workflows/terraform-docs.yml@v1
    with:
      working_directory: terraform
      output_file: ../README.md
      recursive: true
      update_lock_file: true
    secrets:
      DOCUMENTATION_APP_ID: ${{ secrets.DOCUMENTATION_APP_ID }}
      DOCUMENTATION_PRIVATE_KEY: ${{ secrets.DOCUMENTATION_PRIVATE_KEY }}
```

### Configuration Reference

| Configuration Type | Name                    | Description                                          | Default Value                                        | Required |
|--------------------|-------------------------|------------------------------------------------------|------------------------------------------------------|:---------|
| input              | working_directory       | Directory containing Terraform configuration         | `.`                                                  | No       |
| input              | output_file             | Output file path for terraform-docs                  | `README.md`                                          | No       |
| input              | recursive               | Recursively process submodules                       | `false`                                              | No       |
| input              | update_lock_file        | Run terraform providers lock before generating docs  | `false`                                              | No       |
| input              | terraform_docs_version  | terraform-docs version to install                    | `v0.22.0`                                            | No       |
| input              | git_commit_message      | Commit message for docs update                       | `docs: update terraform docs following renovate patch` | No       |
| secret             | DOCUMENTATION_APP_ID    | GitHub App ID for pushing docs commits               |                                                      | Yes      |
| secret             | DOCUMENTATION_PRIVATE_KEY | GitHub App private key for pushing docs commits    |                                                      | Yes      |
