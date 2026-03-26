# Production Stage

For a working example, see the [Greeter](https://github.com/optivem/greeter) template.

## Verify the Production Stage

1. Go to **Actions** on GitHub.
2. Click on `prod-stage`, then **Run workflow**.
3. Enter the prerelease version that passed QA sign-off (e.g. `v0.0.1-rc`).
4. Click **Run workflow** and wait for completion. If it fails, stop and ask for support.
5. Click on the workflow run and review the summary. Note the release version (e.g. `v0.0.1` — the `-rc` suffix is removed).
6. Go to **Releases**. You should see a release marked as **Latest** with the release version.

## Checklist

1. `prod-stage` workflow completes successfully
2. Release is tagged and marked as Latest in GitHub Releases
3. Monolith Package has final version tag (e.g. `-rc` suffix removed)
