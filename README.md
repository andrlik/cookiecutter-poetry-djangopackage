# cookiecutter-poetry-djangopackage

Use this template to get a modern skeleton for a reusable Django app that
makes uses a `pyproject.toml` file for packaging, `poetry` for
managing dependencies and builds, and MkDocs for building documentation from Markdown. 
It also supports safety checks via bandit and exhaustive linting. It can also 
optionally generate a Justfile if you'd prefer to use [`just`](https://github.com/casey/just)
rather than `make`.

## Usage

First, make sure you have cookiecutter installed on your machine.

    $ pip install cookiecutter

Then run:

    $ cookiecutter gh:andrlik/cookiecutter-poetry-djangopackage

Answer the questions when prompted and you'll have your project skeleton!
