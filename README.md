# OtterWise GitHub Actions Workflow

## Minimal usage

```yaml
- uses: getOtterWise/github-action@v1
  with:
    token: ${{ secrets.OTTERWISE_TOKEN }}
```

## All inputs

| Input | Description | Required | Default |
|---|---|---|---|
| `token` | OtterWise Repo token | No* | `''` |
| `org-token` | OtterWise Org token | No* | `''` |
| `file` | Path to coverage file | No | `''` |
| `mutation-file` | Path to mutation testing results file | No | `''` |
| `type-coverage-file` | Path to type coverage file | No | `''` |
| `log-file` | Path to test log file (JUnit XML) | No | `''` |
| `quiet` | Suppress verbose output | No | `false` |
| `fail-on-errors` | Exit with error code 1 if processing fails | No | `false` |
| `flag` | Custom identifier/tag for this upload | No | `''` |
| `base-dir` | Base directory for relative file references | No | `''` |
| `endpoint` | Custom API endpoint URL | No | `''` |
| `bash-uploader-sha` | Git ref for the bash uploader script | No | `main` |

\* At least one of `token` or `org-token` must be provided.

## Examples

Using org token:

```yaml
- uses: getOtterWise/github-action@v1
  with:
    org-token: ${{ secrets.OTTERWISE_ORG_TOKEN }}
```

With coverage and type coverage:

```yaml
- uses: getOtterWise/github-action@v1
  with:
    token: ${{ secrets.OTTERWISE_TOKEN }}
    file: build/coverage/clover.xml
    type-coverage-file: pest-type-cov.json
```

Full example:

```yaml
- uses: getOtterWise/github-action@v1
  with:
    token: ${{ secrets.OTTERWISE_TOKEN }}
    file: build/coverage/clover.xml
    mutation-file: infection.json
    type-coverage-file: pest-type-cov.json
    log-file: junit.xml
    flag: unit-tests
    quiet: true
    fail-on-errors: true
```
