# Contributing

Contributions are welcome, and they are greatly appreciated! Every
little bit helps, and credit will always be given.

You can contribute in many ways:

## Types of Contributions

### Report Bugs

Report bugs at [github:LiteRev/issues](https://github.com/thegraphnetwork-literev/LiteRev/issues).

If you are reporting a bug, please include:

  - Your operating system name and version.
  - Any details about your local setup that might be helpful in
    troubleshooting.
  - Detailed steps to reproduce the bug.

### Fix Bugs

Look through the GitHub issues for bugs. Anything tagged with “bug” and
“help wanted” is open to whoever wants to implement it.

### Implement Features

Look through the GitHub issues for features. Anything tagged with
“enhancement” and “help wanted” is open to whoever wants to implement
it.

### Write Documentation

Documentation files are located at `./docs`.
Since the `API` documentation is based on the docstrings in the python files, writing good docstrings will help us to have better documentation.

### Submit Feedback

The best way to send feedback is to file an issue at
[github:LiteRev/issues](https://github.com/thegraphnetwork-literev/LiteRev/issues).

If you are proposing a feature:

  - Explain in detail how it would work.
  - Keep the scope as narrow as possible, to make it easier to
    implement.
  - Remember that this is a volunteer-driven project, and that
    contributions are welcome :)

## Get Started!

For development, we encourage you to use `conda`. If you don't know
what is that, check these links:

* In Spanish: https://opensciencelabs.org/blog/como-instalar-y-comenzar-utilizar-conda/
* In English: https://cloudsmith.com/blog/what-is-conda/

We recommend you to use mamba-forge, a combination of
miniconda + conda-forge + mamba. You can download it from here:
https://github.com/conda-forge/miniforge#mambaforge

Ready to contribute? Here’s how to set up LiteRev for local development.

1. Clone this repository locally:
```bash
$ git clone git@github.com:thegraphnetwork-literev/LiteRev.git
```
2. Create a conda environment and activate it:
```bash
$ cd LiteRev
$ mamba env create --file conda/base.yaml
```
and
```bash
$ conda activate literev
```
3. Install your local project copy into your conda environment:
```bash
$ poetry install
```
4. Create a branch for local development:
```bash
$ git checkout -b name-of-your-bugfix-or-feature
```
5. When you’re done making changes, check that your changes pass flake8
    and the tests, including testing other Python versions with tox:
```bash
$ makim tests.lint
$ makim tests.unittest
```
6. Commit your changes and push your branch to GitHub:
```bash
$ git add .
$ git commit -m "Your detailed description of your changes."
$ git push origin name-of-your-bugfix-or-feature
```
7. Submit a pull request through the GitHub website.

## Pull Request Guidelines

Before you submit a pull request, check that it meets these guidelines:

1.  The pull request should include tests.
2.  If the pull request adds functionality, the docs should be updated.
    Put your new functionality into a function with a docstring, and add
    the feature to the list in README.rst.
3.  The pull request should work for Python >= 3.8.1.

## Tips

### Debugging

This project uses pdb++ for debugging, so it would help in a bunch of ways.
One of the most useful command you can use is `sticky` that will show you
where is the current line that is executed, inside a context (some lines above
and below), and for each `next` command, it will update the screen
automatically.

For more information, check its GitHub repository: https://github.com/pdbpp/pdbpp


# .env

LiteRev manages the environment variables using `.env`. In order to have
the services running, it is necessary to have a `.env` files, one in which
of the following folders: `./` (root of the project), `./containers/literev/`,
and `./containers/postgres/`.

The `.env` file is not presented in the git repository, so it is necessary to
create it locally. The easiest way to create that is from the `.env.tpl` inside
which of that folders for example: `cp .env.tpl .env`. Next, change the values
of the variables in which file for their desired values.

These are examples of values used by all the three `.env` files:


`./.env`:

```.env
ENV=dev
POSTGRES_HOST=literev-postgres
POSTGRES_PORT=35432
POSTGRES_DB=postgres
POSTGRES_USER=postgres
POSTGRES_PASSWORD=postgres
POSTGRES_DB_LITEREV=literev
POSTGRES_USER_LITEREV=literev
POSTGRES_PASSWORD_LITEREV=literev
FRONTEND_HOST_ADDRESS=literev
FRONTEND_HOST_PORT=8000
```

`./containers/literev/.env`:

```.env
NUMBER_ARTICLE_BY_PAGE=30
NUMBER_THREADS_ALLOWED=4
NUMBER_TRIALS=300
UPDATE_INTERVAL=2700000
X_INTERVAL_BIG=1000
X_INTERVAL_LITTLE=500
Y_INTERVAL_BIG=4000
Y_INTERVAL_LITTLE=1000
FRONTEND_HOST_ADDRESS=literev
FRONTEND_HOST_PORT=8000
DJANGO_SECRET_KEY=django-insecure-96*q09uh20(^i4sdxqh3n_v#d-$o=**7zrri&k-j3@f10hm88)
DJANGO_ENV=dev
ORCID_APP_ID=APP-31MN9C4D9DA27N9X
ORCID_APP_SECRET=d14daed7-aed2-4e5a-b4c2-6533195a6cb1
ORCID_BASE_DOMAIN=sandbox.orcid.org
```

`./containers/postgresql/.env`:

```.env
POSTGRES_PORT=35432
POSTGRES_DB=postgres
POSTGRES_USER=postgres
POSTGRES_PASSWORD=postgres
POSTGRES_DB_LITEREV=literev
POSTGRES_USER_LITEREV=literev
POSTGRES_PASSWORD_LITEREV=literev
```

## Docker

The easiest way to run LiteRev is using docker.
In order to have a simple workflow, LiteRev uses
[containers-sugar](https://github.com/osl-incubator/containers-sugar) and
[makim](https://github.com/osl-incubator/makim).

These are the steps necessary to have your services up and running:

1. `sugar build`
2. `makim containers.migrate`
3. `sugar ext restart`

These three steps should be enough to have the services running
locally.

## Django

### How to create a django super user

In order to create a django super user, you can run the following command:

```bash
$  makim django.create-superuser \
  --username myusername \
  --password mypassword \
  --email my@email.com
```

*Note: Remember to replace the placeholder used in the command.*

### Running Django with Jupyter

[Django Extensions](https://github.com/django-extensions/django-extensions)
allow us to run the LiteRev Django project inside a Jupyter Notebook.

First, ensure you have the environment variable `POSTGRES_HOST=localhost` in your
`.env` file. `.env` should be located in the root of the project.

Then, load the environment variables:

```bash
$ export $(cat .env)
```

Finally, run Django in notebook mode:

```bash
$ python src/manage.py shell_plus --notebook
```

If you would like to share any experimental notebooks, please store it at `docs/notebooks`.

If you have any issues while trying to follow the steps presented here, please check if
the PostgreSQL service is running. You can start the server using the following command:

```bash
$ sugar ext restart --services literev-postgres --options -d
```

### Tests

To run a subset of tests, you can use the parameter `--params`.
It is possible to pass module name, class name and/or test function name.
For example,

```
$ makim tests.unittest --app BackEnd --params "-v3 --failfast -k test_medrxiv_collector.MedrXivCollectorGetArticleParallelTestCase"
```

### Run Django application
You can run the django application using makim:

```bash
$ makim django.runserver
```

If you want to use it locally (instead of from a docker-container), run:

```bash
$ makim django.runserver --local
```

## Release

This project uses semantic-release in order to cut a new release
based on the commit-message.

### Commit message format

**semantic-release** uses the commit messages to determine the consumer
impact of changes in the codebase. Following formalized conventions for
commit messages, **semantic-release** automatically determines the next
[semantic version](https://semver.org) number, generates a changelog and
publishes the release.

By default, **semantic-release** uses [Angular Commit Message
Conventions](https://github.com/angular/angular/blob/master/CONTRIBUTING.md#-commit-message-format).
The commit message format can be changed with the `preset` or `config`
options\_ of the
[@semantic-release/commit-analyzer](https://github.com/semantic-release/commit-analyzer#options)
and
[@semantic-release/release-notes-generator](https://github.com/semantic-release/release-notes-generator#options)
plugins.

Tools such as [commitizen](https://github.com/commitizen/cz-cli) or
[commitlint](https://github.com/conventional-changelog/commitlint) can
be used to help contributors and enforce valid commit messages.

The table below shows which commit message gets you which release type
when `semantic-release` runs (using the default configuration):

| Commit message                                                 | Release type     |
|----------------------------------------------------------------|------------------|
| `fix(pencil): stop graphite breaking when pressure is applied` | Fix Release      |
| `feat(pencil): add 'graphiteWidth' option`                     | Feature Release  |
| `perf(pencil): remove graphiteWidth option`                    | Chore            |
| `fix!: The graphiteWidth option has been removed`              | Breaking Release |

source:
<https://github.com/semantic-release/semantic-release/blob/master/README.md#commit-message-format>

As this project uses the `squash and merge` strategy, ensure to apply
the commit message format to the PR's title.

## Troubleshooting

* Poetry package hash not found: Hash for <package-name> (<package-version>)
  from archive <package-file> not found in known hashes
  (was: sha256:<package-hash>).

  If you are experiencing this issue, maybe this command can fix that:

  ```bash
  $ rm -rf ~/.cache/pypoetry
  ```

  If it doesn't fix your problem, please check this github issue:
  https://github.com/python-poetry/poetry/issues/4523
