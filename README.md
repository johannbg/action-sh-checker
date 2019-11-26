# sh-checker

A GitHub Action that performs static analysis for shell scripts using [shellcheck](https://github.com/koalaman/shellcheck). and [shfmt](https://github.com/mvdan/sh)

## Usage

Job example to check all sh files but ignore the directory `.terraform`

```
name: example
on:
  push:
jobs:
  sh-checker:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v1
      - name: Run the sh-checker
        uses: luizm/action-sh-checker@v0.1.0
        env:
          SH_CHECKER_EXCLUDE_REGEX: '/.terraform/*'
```

### Environments:

`SH_CHECKER_EXCLUDE_REGEX: '/.terraform/\'`

The regex to filter the files or directories that don't need to check.

`SH_CHECKER_SHFMT_DISABLE: "true"`

If true, it will skip the shfmt. Default is false

`SH_CHECKER_SHELLCHECK_DISABLE: "true"`

If true, it will skip the shellcheck. Default is false
