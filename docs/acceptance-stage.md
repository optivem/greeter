# Acceptance Stage

For a working example, see the [Greeter](https://github.com/optivem/greeter) template.

## Verify the Acceptance Stage

1. Go to **Actions** on GitHub.
2. Click on `acceptance-stage`, then **Run workflow**.
3. Leave "Force run" unticked.
4. Click **Run workflow** and wait for completion. If it fails, stop and ask for support.
5. Click on the workflow run and review the summary.
6. Go to **Releases**. You should see a prerelease candidate with a version like `v0.0.1-rc`.
7. Go to **Packages**, click on the `monolith` package. Confirm the tag (e.g. `v0.0.1-rc`) has been applied to the Docker image.

*The Acceptance Stage is a scheduled workflow. You don't normally trigger it manually — we triggered it above to verify your setup without waiting for the scheduled run.*

*Since your repository is public, GitHub Actions usage is free (for standard GitHub-hosted runners) and you don't need to worry about minutes cost.*
