# Acceptance Stage - Multi Component

For a working example, see the [Greeter Multi Component](https://github.com/optivem/greeter-multi-comp) template.

## Update Image References

Open the file `acceptance-stage.yml`.

Find the word `monolith` inside `image-urls` — there's one line. Copy-paste that line so you have two lines. In the first line, replace `monolith` with `frontend`. In the second line, replace `monolith` with `backend`.

Commit and push.

Manually trigger `acceptance-stage` (with the "Force run" option).

Verify that it is successful.

Note the RC version.

## Checklist

1. Acceptance Stage finds latest artifacts for all components
2. All component artifacts deployed together
3. System RC version tags applied to all component artifacts
4. `acceptance-stage` workflow completes successfully
