# QA Stage - Multi Repo

For a working example, see the [Greeter Multi Repo](https://github.com/optivem/greeter-multi-repo) template.

## Update Image References

Open the file `qa-stage.yml`.

In the job `resolve-docker-images`, find the input `base-image-urls`. For each component, replace `${{ github.event.repository.name }}` with the corresponding component repository name.

Example:

```
base-image-urls: |
  ghcr.io/${{ github.repository_owner }}/eshop-frontend/frontend
  ghcr.io/${{ github.repository_owner }}/eshop-backend/backend
```

Manually trigger the QA Stage and verify it passes.

> **Note:** After updating the QA Stage, the Production Stage may still fail because it still references the old image URLs. This is expected — you will update it in the Production Stage multi-repo section. For now, only verify that the QA Stage passes.

## Checklist

1. QA Stage references correct image URLs from component repositories
2. Cross-repository tagging works with `DOCKER_REGISTRY_TOKEN`
3. `qa-stage` workflow completes successfully
