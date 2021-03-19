# Create gh-pages Branch if not exists

A github action which can be in a template or component job that automates creation
of gh-pages branch if it does not already exist. After it exists, it does nothing.

## Usage:

In your GitHub Actions workflow, add a `uses:` declaration before calling the
`sbt` command. checkout@v2 or greater is required to push changes.

```diff
+++ .github/workflows/ci.yml
  name: CI
  on:
    push:
  jobs:
    build:
      runs-on: ubuntu-latest
      steps:
      - uses: actions/checkout@v2
+     - uses: christopherdavenport/create-ghpages-ifnotexists@v1
```