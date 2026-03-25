# Acceptance Stage - Multi Repo

For a working example, see the [Greeter Multi Repo](https://github.com/optivem/greeter-multi-repo) template.

## 1. Create Token

1. In the top-right corner of any GitHub page, click your profile photo → **Settings**.
2. Go to **Developer Settings** → **Personal access tokens** → **Tokens (classic)**.
3. Click **Generate new token** → **Generate new token (classic)**.
4. In Note, write: `DOCKER_REGISTRY_TOKEN`
5. Under Select scopes, tick: `write:packages`, `read:packages`.
6. Click **Generate token**.
7. Copy the token value — you won't see it again.

Add the PAT as a system repository secret:

1. In your system repository, go to **Settings** → **Secrets and variables** → **Actions**.
2. Click **New repository secret**:
   - Name: `DOCKER_REGISTRY_TOKEN`
   - Secret: paste the token value.

## 2. Update Image References

Open `acceptance-stage.yml`.

In the job `find-latest-images`, find the input `image-urls`. For each component, replace `${{ github.event.repository.name }}` with the corresponding component repository name.

Example:

```
image-urls: |
  ghcr.io/${{ github.repository_owner }}/eshop-frontend/frontend:latest
  ghcr.io/${{ github.repository_owner }}/eshop-backend/backend:latest
```

## 3. Update RC Tagging

In the step `Tag Docker Images for Prerelease`, set the value `GITHUB_TOKEN: ${{ secrets.DOCKER_REGISTRY_TOKEN }}`.

## 4. Update Docker Compose

Update `system-test/docker-compose.yml` to reference the component images from their respective repositories.

## 5. Verify

Commit and push.

Manually trigger `acceptance-stage` (with the "Force run" option).

Verify that it is successful.
