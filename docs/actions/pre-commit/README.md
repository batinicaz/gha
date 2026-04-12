# pre-commit

Action File: [action.yml](../../../.github/actions/pre-commit/action.yml)

Installs pre-commit and required tooling (Terraform, TFLint, terraform-docs) natively on the runner,
caches hook environments between runs, and executes `pre-commit run --all-files`.

Hook environments are cached in `~/.cache/pre-commit` using `actions/cache`, keyed on `.pre-commit-config.yaml`.
On cache hit, hook setup is skipped entirely. PR branches inherit the cache from the base branch.

## Usage

```yaml
  pre-commit:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v6

      - name: Run pre-commit
        uses: batinicaz/gha/.github/actions/pre-commit@v1
```

### Configuration Reference

| Name                   | Description                                                      | Default                   | Required |
|:-----------------------|:-----------------------------------------------------------------|:--------------------------|:---------|
| path                   | The path to the configuration to run pre-commit against          | `${{ github.workspace }}` | No       |
| python-version         | Python version for pre-commit                                    | `3.x`                     | No       |
| terraform-version      | Terraform version for terraform-fmt and terraform-validate hooks | `latest`                  | No       |
| tflint-version         | TFLint version for tflint hook                                   | `latest`                  | No       |
| terraform-docs-version | terraform-docs version for terraform-docs-system hook            | `v0.22.0`                 | No       |
