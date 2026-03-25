# Commit Stage - Multi Component

For a working example, see the [Greeter Multi Component](https://github.com/optivem/greeter-multi-comp) template.

## 1. Decompose System

Suppose your architecture is Frontend + Backend.

1. Create `frontend` and `backend` folders in your repo.
2. Migrate functionality from `monolith` into `frontend` and `backend`.
3. Delete the `monolith` folder.
4. Run frontend and backend locally and verify the application loads in your browser.

Do not commit/push yet.

## 2. Decompose Commit Stage

In `.github/workflows`:

**Create the Frontend Commit Stage:**

1. Copy `commit-stage-monolith.yml` to `commit-stage-frontend.yml`.
2. Find-replace `monolith` with `frontend`.
3. Replace the build steps (between Checkout Repository and Publish Docker Image) with your frontend language's build commands.

**Create the Backend Commit Stage:**

1. Copy `commit-stage-monolith.yml` to `commit-stage-backend.yml`.
2. Find-replace `monolith` with `backend`.
3. Replace the build steps with your backend language's build commands.

**Delete the Monolith Commit Stage:**

1. Delete `commit-stage-monolith.yml`.

**Commit and push.**

> After pushing, the Acceptance Stage, QA Stage, and Production Stage will fail because they still reference "monolith". This is expected — you will update each stage in the corresponding multi-component lessons in later modules. For now, only verify that the Commit Stages pass.

Verify:

- `commit-stage-frontend` passes
- `commit-stage-backend` passes
- `commit-stage-monolith` no longer exists

In Packages:

1. Verify `frontend` and `backend` packages exist.
2. Delete the `monolith` package (Package → Package settings → Delete this package).

## 3. Update README

Delete the `commit-stage-monolith` status badge and replace it with badges for `commit-stage-frontend` and `commit-stage-backend`.

## 4. Update Docker Compose

In `system-test/docker-compose.yml`:

1. Replace the single monolith service with separate `frontend` and `backend` services.
2. Update the image references accordingly.
3. Run Docker Compose locally and verify the application loads.
4. Run the system tests locally and verify they pass.

## Frontend + Microservice Backend

*Only if your project uses a microservice architecture.* Complete the Frontend + Backend steps above first, then split the backend into microservices — create a separate Commit Stage per microservice and update the README and Docker Compose accordingly.
