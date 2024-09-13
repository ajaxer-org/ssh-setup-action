# ssh-setup-action
GitHub action to setup ssh file from secret

# SSH Setup Action

This GitHub Action sets up SSH for use in GitHub Actions workflows.

### Usage

```yaml
uses: ajaxer-org/ssh-setup-action@latest
with:
  ssh-private-key: ${{ secrets.SSH_PRIVATE_KEY }}
  host: github.
  ssh-key-filename: id_rsa  # Can customize the key file name if needed
```

### Example

```yaml
name: My Workflow

on:
  push:
    branches:
      - main

jobs:
  setup:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout code
        uses: actions/checkout@v3

      - name: Set up SSH
        uses: ajaxer-org/ssh-setup-action@latest
        with:
          ssh-private-key: ${{ secrets.SSH_PRIVATE_KEY }}
          host: github.com
          ssh-key-filename: id_rsa  # Can customize the key file name if needed
```
