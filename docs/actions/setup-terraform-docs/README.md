# setup-terraform-docs

Action File: [action.yml](../../../.github/actions/setup-terraform-docs/action.yml)

Downloads and installs the terraform-docs binary from GitHub releases into `/usr/local/bin`.

Used by the [pre-commit](../pre-commit) action and the [terraform-docs](../../workflows/terraform-docs) workflow
to ensure a consistent terraform-docs version across CI.

## Usage

```yaml
steps:
  - name: Setup terraform-docs
    uses: batinicaz/gha/.github/actions/setup-terraform-docs@v1
    with:
      version: "v0.22.0"
```

### Configuration Reference

| Name    | Description                    | Default   | Required |
|:--------|:-------------------------------|:----------|:---------|
| version | terraform-docs version to install | `v0.22.0` | No       |
