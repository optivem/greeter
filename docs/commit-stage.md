# Commit Stage

For a working example, see the starter templates:

- [Greeter - Java](https://github.com/optivem/greeter-java)
- [Greeter - .NET](https://github.com/optivem/greeter-dotnet)
- [Greeter - TypeScript](https://github.com/optivem/greeter-typescript)

## Verify the Template

1. Open the `monolith` folder. In any file, add a comment.
2. Commit and push your changes.
3. Go to **Actions** on your GitHub repository.
4. Verify that the `commit-stage-monolith` workflow is running.
5. Wait for it to complete. If it fails, stop and ask for support.
6. Click on the workflow run and review the summary.
7. Go to **Packages** (on your repository main page, right-hand side). You should see a `monolith` package — this is the Docker image artifact.

## Change & Push Code

1. Make some change in the source code, commit and push, verify that the Commit Stage is automatically triggered and runs successfully.
2. Make another change which causes a compile time error, commit and push, verify that the Commit Stage is automatically triggered and fails. Then revert that commit, and verify that the Commit Stage passes.
