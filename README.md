# .github

Repository dedicated to Libon GitHub shared config & workflows.

## Generate release and changelog on your project

To use this common GitHub Action, you need to add the file below in your repository in the path
`.github/workflows/release-workflow.yml`

```yaml
name: Release Drafter

on:
  push:
    # branches to consider in the event; optional, defaults to all
    branches:
      - master
      - main
    tags:
      - '**'
jobs:
  compliance:
    uses: libon/.github/.github/workflows/release-drafter-workflow.yml@main
```