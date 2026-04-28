# flywheel-sandbox

Test infrastructure for [`point-source/flywheel`](https://github.com/point-source/flywheel).
This repo exists exclusively to host real PRs, real labels, real auto-merges,
and real semantic-release tags driven by Flywheel's Layer 2 (integration) and
Layer 3 (end-to-end) test suites — never used for anything else.

See [`flywheel/docs/sandbox-setup.md`](https://github.com/point-source/flywheel/blob/main/docs/sandbox-setup.md)
for the provisioning contract.

## Long-lived branches

| Branch | Stream | Role |
|---|---|---|
| `e2e-main` | `main-line` | terminal production branch |
| `e2e-staging` | `main-line` | staging |
| `e2e-develop` | `main-line` | development |
| `e2e-customer-acme` | `customer-acme` | single-branch customer stream |
| `integration-test-base` | `integration` | PR target for Layer 2 tests |

Tests own their own branches under `e2e/<scenario>-<unix-millis>` (Layer 3)
or `test/<scenario>-<unix-millis>` (Layer 2). The long-lived branches above
are immutable from the test perspective; tests target them but never push
to them directly.
