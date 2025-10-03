# OtterWise GitHub Actions Workflow

## Minimal usage

```yaml
- uses: getOtterWise/coverage-action@v1
  with:
    token: ${{ secrets.OTTERWISE_TOKEN }}
```

Or specify file if not placed in common path:

```yaml
- uses: getOtterWise/coverage-action@v1
  with:
    token: ${{ secrets.OTTERWISE_TOKEN }}
    file: build/coverage/clover.xml
```
