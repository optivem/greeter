# Commit Stage - Multi Repo

For a working example, see the [Greeter Multi Repo](https://github.com/optivem/greeter-multi-repo) template.

## 1. Separate Frontend

Create a new frontend repository (e.g. `eshop-frontend`).

1. In the system repository README, add a link to the new frontend repository.
2. Move the `frontend` folder and `.github/workflows/commit-stage-frontend.yml` to the frontend repository.
3. Move the frontend Commit Stage badge from the system repository README to the frontend repository README. Update the badge URL to point to the new repository.
4. Commit and push in the frontend repository.
5. Verify the frontend Commit Stage passes.
6. Verify the frontend package is created in the frontend repository.
7. Delete the frontend package from the system repository (Packages → click the package → Package settings → Delete).
8. Copy the frontend Commit Stage badge from the frontend repository back into the system repository README for a consolidated view.

## 2. Separate Backend

Repeat the same process for the backend.

> After moving components to separate repositories, the Acceptance Stage, QA Stage, and Production Stage will fail because they still reference the old image URLs. This is expected — you will update each stage in the corresponding multi-repo lessons in later modules. For now, only verify that the Commit Stages pass.
