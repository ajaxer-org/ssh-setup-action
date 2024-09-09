# ssh-setup-action
GitHub action to setup ssh file from secret

# SSH Setup Action

This GitHub Action sets up SSH for use in GitHub Actions workflows.

### Usage

```yaml
uses: ajaxer-org/ssh-setup-action@v1
with:
  ssh-private-key: ${{ secrets.SSH_PRIVATE_KEY }}
  host: github.com
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
        uses: <your-username>/actions/.github/actions/setup-ssh@v1
        with:
          ssh-private-key: ${{ secrets.SSH_PRIVATE_KEY }}
          host: github.com
          ssh-key-filename: id_rsa  # Can customize the key file name if needed
```
