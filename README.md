# .github

Repository dedicated to Libon GitHub shared config & workflows.

> **WARNING**: This is a public repository, do not commit any sensible information ! 

## Generate release and changelog on your project

- If your repository already have at least a tag, do a release manually on GitHub on the latest tag. This is needed 
  otherwise the first release note written by the job will contain all changelog from your repository. 

- Add the file below in your repository in the path `.github/workflows/release-workflow.yml`

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