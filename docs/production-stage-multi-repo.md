# Production Stage - Multi Repo

For a working example, see the [Greeter Multi Repo](https://github.com/optivem/greeter-multi-repo) template.

## Update Image References

Open the file `prod-stage.yml`.

In the job `resolve-docker-images`, find the input `base-image-urls`. For each component, replace `${{ github.event.repository.name }}` with the corresponding component repository name.

In the step `Tag Docker Images for Production`, set the value `GITHUB_TOKEN: ${{ secrets.DOCKER_REGISTRY_TOKEN }}`.

Manually trigger the PROD Stage and verify it passes.

## Checklist

1. Production Stage references correct image URLs from component repositories
2. Cross-repository final version tagging works with `DOCKER_REGISTRY_TOKEN`
3. `prod-stage` workflow completes successfully
