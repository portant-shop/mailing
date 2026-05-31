[![CircleCI](https://dl.circleci.com/status-badge/img/gh/portant-shop/mailing/tree/master.svg?style=svg)](https://dl.circleci.com/status-badge/redirect/gh/portant-shop/mailing/tree/master)

# mailing
a django app for sending emails in portant

# Build and deploy

## 1. Set up the environment

Create and activate a virtual environment with uv, then install the dependencies:

    uv venv
    source .venv/bin/activate
    uv pip install -r requirements.txt

## 2. Bump the version

Before building a release, increment `version` in `setup.py`:

    setup(
        name=NAME,
        version="1.0.8",  # <-- bump this
        ...
    )

The project follows semantic versioning (`MAJOR.MINOR.PATCH`):

- **PATCH** (`1.0.8` -> `1.0.9`) — backwards-compatible bug fixes.
- **MINOR** (`1.0.8` -> `1.1.0`) — new, backwards-compatible functionality.
- **MAJOR** (`1.0.8` -> `2.0.0`) — backwards-incompatible changes.

Commit the version bump (and tag the release, e.g. `git tag v1.0.9`) before publishing.

## 3. Build

Build the source distribution into `dist/` using uv's built-in build front-end:

    uv build --sdist

Drop `--sdist` to build both the sdist and the wheel.

## 4. Deploy

Publish the contents of `dist/` to the package index:

    uv publish

Configure the target index and credentials via `UV_PUBLISH_URL` /
`UV_PUBLISH_TOKEN` (or `--publish-url` / `--token`) as appropriate for your
registry.
