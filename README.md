# action-pdk-validate

This action runs `pdk validate` on your puppet module codebase and fails the step if there are static validation failures.

## Usage

To use the action add the following step to your workflow file (e.g. `.github/workflows/pdk-validate.yml`)

```yaml
name: Run pdk static validation

on:
  - push
  - pull_request

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
    - name: Clone repository
      uses: actions/checkout@v2

    - name: Run pdk validate
      uses: edrude/action-pdk-build@v1
      with:
        puppet-version: ""
        # [optional]
        # A string indicating the Puppet version to validate against, such as "5.4.2" or "5.5".
        pe-version: ""
        # [optional]
        # A string indicating the PE version to validate against, such as "2017.3.5" or "2018.1".
```
