# Contributor Guide

Thank you for your interest in improving this project.
This project is open-source under the [MIT license] and
welcomes contributions in the form of bug reports, feature requests, and pull requests.

Here is a list of important resources for contributors:

- [Source Code]
- [Documentation]
- [Issue Tracker]
- [Code of Conduct]

[mit license]: https://opensource.org/licenses/MIT
[source code]: https://github.com/robbievanleeuwen/concrete-properties
[documentation]: https://concrete-properties.readthedocs.io/
[issue tracker]: https://github.com/robbievanleeuwen/concrete-properties/issues

## How to report a bug

Report bugs on the [Issue Tracker].

When filing an issue, make sure to answer these questions:

- Which operating system and Python version are you using?
- Which version of this project are you using?
- What did you do?
- What did you expect to see?
- What did you see instead?

The best way to get your bug fixed is to provide a test case,
and/or steps to reproduce the issue.

## How to request a feature

Features that improve `concreteproperties` can be suggested on the [Issue Tracker].
It's a good idea to first submit the proposal as a feature request prior to submitting
a pull request as this allows for the best coordination of efforts by preventing the
duplication of work, and allows for feedback on your ideas.

## How to set up your development environment

You need Python 3.9, 3.10 or 3.11, and the following tools:

- [Poetry]
- [Nox]
- [nox-poetry]

Recommended dependency installation method:

1. Install [pipx](https://pypa.github.io/pipx/installation/):

```shell
python3 -m pip install --user pipx
python3 -m pipx ensurepath
```

2. Install [Poetry]:

```shell
pipx install poetry
poetry --version
```

3. Install [Nox] and [nox-poetry]:

```shell
pipx install nox
pipx inject nox nox-poetry
```

4. If you do not have `pandoc` installed, it will be required to build the docs. The
   [installation method](https://pandoc.org/installing.html) depends on what OS you are
   running.

Now that you have all the dependencies up and running, you can install
`concreteproperties` with development requirements:

```shell
git clone https://github.com/robbievanleeuwen/concrete-properties.git
cd concrete-properties
poetry install --all-extras
```

You can now run an interactive Python session, or the command-line interface:

```shell
poetry run python
poetry run concreteproperties
```

[poetry]: https://python-poetry.org/
[nox]: https://nox.thea.codes/
[nox-poetry]: https://nox-poetry.readthedocs.io/

## How to test the project

Run the full test suite:

```shell
nox
```

List the available Nox sessions:

```shell
nox --list-sessions
```

You can also run a specific Nox session. For example, invoke the unit test suite like
this:

```shell
nox --session=tests
```

Unit tests are located in the _tests_ directory, and are written using the [pytest]
testing framework.

[pytest]: https://pytest.readthedocs.io/

## How to submit changes

Open a [pull request] to submit changes to this project.

Your pull request needs to meet the following guidelines for acceptance:

- The Nox test suite must pass without errors and warnings.
- Include unit tests. This project aims for a high code coverage.
- If your changes add functionality, update the documentation accordingly.

To run linting and code formatting checks before committing your change, you can install
pre-commit as a Git hook by running the following command:

```shell
nox --session=pre-commit -- install
```

It is recommended to open an issue before starting work on anything.
This will allow a chance to talk it over with the owners and validate your approach.

[pull request]: https://github.com/robbievanleeuwen/concrete-properties/pulls
[code of conduct]: CODE_OF_CONDUCT.md
