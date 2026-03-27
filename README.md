# Greeter

A simple greeter application with tests across multiple languages.

## Starter Templates

- [Greeter - Java](https://github.com/optivem/greeter-java)
- [Greeter - .NET](https://github.com/optivem/greeter-dotnet)
- [Greeter - TypeScript](https://github.com/optivem/greeter-typescript)

## Customized Templates

- [Greeter - Multi Language](https://github.com/optivem/greeter-multi-lang)
- [Greeter - Multi Component](https://github.com/optivem/greeter-multi-comp)
- [Greeter - Multi Repository](https://github.com/optivem/greeter-multi-repo)

## Usage

1. Open up the template based on your chosen language (see [Starter Templates](#starter-templates) above).
   - *If your chosen language is not on the list, no worries, just choose any of the templates because the Pipeline Architecture is the same — you can do language replacement afterwards.*
2. Download that template repository.
3. Open up YOUR repository.
4. Copy paste the following from the template repository into YOUR repository:
   - `.github`
   - `monolith`
   - `system-test`
   - `README.md` (only the top part, that contains the status badges)
5. Replace `optivem/greeter-{language}` with `<your_repo_owner>/<your_repo_name>` in the whole project:
   - In the README file, so that the status badges point to your workflows (not the template workflows)
   - In `system-test/docker-compose.yml`, to reference your Docker Image (not the template image)
6. In the Docker Compose file, ensure that everything is lowercase in the image url.
7. Commit and push.
8. Manually trigger `commit-stage-monolith` and wait for it to finish successfully.
9. Follow the [Acceptance Stage](docs/acceptance-stage.md) setup and verification steps.

## Customization

*Skip this section if your chosen language already matches the template you applied.*

### Monolith Language

1. Open the `monolith` folder.
2. **If your target language is Java, .NET, or TypeScript:**
   - Find the target language template in [Starter Templates](#starter-templates) above.
   - Delete the `monolith` folder in your repo.
   - Copy from the target template: `monolith` folder, `system-test/docker-compose.yml` (overwrite), `.github/workflows/commit-stage-monolith.yml` (overwrite).
   - In `system-test/docker-compose.yml`, replace `optivem/greeter-{lang}` with `<your_repo_owner>/<your_repo_name>` for the image field.
3. **If your target language is something else:**
   - Rewrite the `monolith` folder in your target language (or use an LLM to assist).
   - Update the `monolith` README.md with build and run instructions.
   - Build and run locally. Note the port (e.g. 2500).
   - In `system-test/docker-compose.yml`, set ports to `8080:YOUR_PORT`.
   - In `.github/workflows/commit-stage-monolith.yml`, replace the steps between 'Checkout Repository' and 'Publish Docker Image' with your language's setup and build commands.
4. Commit and push.
5. Verify that `commit-stage-monolith` passes.
6. Verify that `acceptance-stage` passes (trigger manually after Commit Stage succeeds).

### System Test Language

*Skip this section if your developers and QA automation engineers use the same language.*

1. Open the `system-test` folder.
2. **If your target language is Java, .NET, or TypeScript:**
   - Find the target template in [Starter Templates](#starter-templates) above.
   - Delete everything in `system-test` **except** `docker-compose.yml`.
   - Copy from the target template: `system-test` folder (except `docker-compose.yml`), `.github/actions/deploy-docker-images/action.yml`, `.github/workflows/acceptance-stage.yml`.
3. **If your target language is something else:**
   - Rewrite the `system-test` folder in your target language. Check Playwright language support; switch to Selenium if needed.
   - Update the `system-test` README.md with instructions to run tests.
   - In `.github/actions/deploy-docker-images/action.yml`, replace the steps after 'Wait for Application to be Ready' with your language setup and smoke test commands.
   - In `.github/workflows/acceptance-stage.yml`, replace the steps after 'Deploy System' with your language setup and E2E test commands.
4. Commit and push.
5. Verify that `acceptance-stage` passes (trigger manually with **Force run** selected).

> **Why different languages?** It is common for development teams and QA teams to use different languages. For background, see the multi-language template at [greeter-multi-lang](https://github.com/optivem/greeter-multi-lang).

## Namespace Replacement

1. Find template namespace references:
   - Java: `com.optivem.greeter`
   - .NET: `Optivem.Greeter`
   - TypeScript: `@optivem/greeter-system-test`
   - Also search for any other references like "accelerator" and "Accelerator"
   - For TypeScript, also update `author`, `license`, `description` in `package.json`
2. Replace all references with your corresponding namespace and info.
3. Commit and push.
4. Verify that `commit-stage-monolith` and `acceptance-stage` workflows still pass.

## Checklist

1. Template has been applied to your repository
2. All references to the template repository name have been replaced with your own
3. Namespace customization is complete
4. Root README file contains correct links to GitHub Actions
5. Docker Compose file (in System Test) has the correct monolith image url
6. `commit-stage-monolith` and `acceptance-stage` workflows pass

## Docs

- [Commit Stage](docs/commit-stage.md)
- [Commit Stage - Multi Component](docs/commit-stage-multi-component.md)
- [Commit Stage - Multi Repo](docs/commit-stage-multi-repo.md)
- [Acceptance Stage](docs/acceptance-stage.md)
- [Acceptance Stage - Multi Component](docs/acceptance-stage-multi-component.md)
- [Acceptance Stage - Multi Repo](docs/acceptance-stage-multi-repo.md)

## License

[![Unlicense](https://img.shields.io/badge/license-Unlicense-lightgrey.svg)](http://unlicense.org/)

This project is released under [The Unlicense](http://unlicense.org) — a public domain dedication.

## Contributors

- [Valentina Jemuović](https://www.linkedin.com/in/valentinajemuovic/)
- [Jelena Cupać](https://www.linkedin.com/in/jelenacupac/)
