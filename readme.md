# proto plugin tools get no updates

## Current behavior

`.prototools` pins two tools installed through proto TOML plugins: `buf` from an `https://` plugin URL and `typos` from a local `file://` plugin. Renovate's `proto` manager reports both as `unsupported-datasource`, so neither gets an update PR. The [Dependency Dashboard](https://github.com/jlouazel/renovate-proto-plugin-repro/issues/1) shows `.prototools` detected with no dependencies listed and no pending branches.

## Expected behavior

Renovate reads each plugin's `[resolve] git-url`, looks up that repository's tags, and opens update PRs for `buf` and `typos`, the same way `proto outdated` reports newer versions.

## Link to the Renovate PR

https://github.com/renovatebot/renovate/pull/47578
