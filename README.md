# Plone.de Site

The german destination for Plone

## Quick start

### Development Setup

- Python 3.11
- Node ^18 || ^20
- yarn
- Docker

## Structure

This monorepo is composed by two distinct codebases: api and frontend.

- **backend**: API (Backend) Plone installation using pip (not buildout). Includes a policy package named plone.de
- **frontend**: React (Volto) package named plonede

### Reasoning

- Repo contains all codebase needed to run the site (excluding existing addons for Plone and React).
- Github Workflows are triggered based on changes on each codebase (see .github/workflows)
- Easier to create Docker images for each codebase
- Showcase Plone installation/setup without buildout

## Linters and Formatting

There are some hooks to run lint checks on the code. If you want to automatically format them, you can run

`make format`

in the root folder or especifically in each backend or frontend folders.

Linters commands are available in each backend and frontend folder.

## Acceptance tests

There are `Makefile` commands in place:

`build-test-acceptance-server`: Build Acceptance Backend Server Docker image that it's being used afterwards. Must be run before running the tests, if the backend code has changed.

`start-test-acceptance-server`: Start server fixture in docker (previous build required)

`start-test-acceptance-frontend`: Start the Core Acceptance Frontend Fixture in dev mode

`test-acceptance`: Start Core Cypress Acceptance Tests in dev mode

## Credits

**This was generated by [cookiecutter-plone-starter](https://github.com/collective/cookiecutter-plone-starter) on 2022-09-22 11:15:39**
