# Production Stage - Multi Component

For a working example, see the [Greeter Multi Component](https://github.com/optivem/greeter-multi-comp) template.

## Update Image References

Open the file `prod-stage.yml`.

Find the word `monolith` inside `base-image-urls` — there's one line. Copy-paste that line so you have two lines. In the first line, replace `monolith` with `frontend`. In the second line, replace `monolith` with `backend`.

Manually trigger the PROD Stage (using the RC that you used in QA Stage above).

Verify that PROD Stage passes.

## Checklist

1. Production Stage deploys all component artifacts
2. Final system version tag applied to all component artifacts
3. `prod-stage` workflow completes successfully
