{% set is_open_source = cookiecutter.open_source_license != 'Not open source' -%}
{% for _ in cookiecutter.project_name %}={% endfor %}
{{ cookiecutter.project_name }}
{% for _ in cookiecutter.project_name %}={% endfor %}

{% if is_open_source %}
[![PyPI version](https://img.shields.io/pypi/v/{{ cookiecutter.project_slug }}.svg)](https://pypi.python.org/pypi/{{ cookiecutter.project_slug }})

[![{{ cookiecutter.open_source_license }}](https://img.shields.io/github/license/{{ cookiecutter.github_username }}/{{ cookiecutter.project_slug }})](https://github.com/{{ cookiecutter.github_username }}/{{ cookiecutter.project_slug }}/blob/main/LICENSE)

[![Black code style](https://img.shields.io/badge/code%20style-black-000000.svg)](https://github.com/ambv/black)

[![Pre-commit enabled](https://img.shields.io/badge/pre--commit-enabled-brightgreen?logo=pre-commit&logoColor=white)](https://github.com/{{ cookiecutter.github_username }}/{{ cookiecutter.project_slug }}/blob/main/.pre-commit-config.yaml)

[![Security: bandit](https://img.shields.io/badge/security-bandit-green.svg)](https://github.com/PyCQA/bandit)

[![Semantic versions](https://img.shields.io/badge/%20%20%F0%9F%93%A6%F0%9F%9A%80-semantic--versions-e10079.svg)](https://github.com/{{ cookiecutter.github_username }}/{{ cookiecutter.project_slug }}/releases)

[![Build status badge](https://github.com/{{ cookiecutter.github_username }}/{{ cookiecutter.project_slug }}/actions/workflows/test.yml/badge.svg?branch=main)](https://github.com/{{ cookiecutter.github_username }}/{{ cookiecutter.project_slug }}/actions/workflows/test.yml)

[![Codestyle test status](https://github.com/{{ cookiecutter.github_username }}/{{ cookiecutter.project_slug }}/actions/workflows/codestyle.yml/badge.svg?branch=main)](https://github.com/{{ cookiecutter.github_username }}/{{ cookiecutter.project_slug }}/actions/workflows/codestyle.yml)

 {% if cookiecutter.use_coveralls == 'y' %}

[![Code coverage badge](https://coveralls.io/repos/github/{{ cookiecutter.github_username }}/{{ cookiecutter.project_slug }}/badge.svg?branch=main)](https://coveralls.io/github/{{ cookiecutter.github_username }}/{{ cookiecutter.project_slug }}?branch=main)

 {% endif %}


[![Documentation](https://img.shields.io/badge/docs-mkdocs-blue)](https://{{ cookiecutter.github_username }}.github.io/{{ cookiecutter.project_slug }}/)

{%- endif %}

{{ cookiecutter.project_short_description }}

{% if is_open_source %}
* Free software: {{ cookiecutter.open_source_license }}
* Repository and Issue Tracker: https://github.com/{{ cookiecutter.github_username }}/{{ cookiecutter.project_slug}}/
* Documentation: https://{{ cookiecutter.project_slug | replace("_", "-") }}.readthedocs.io.
{% endif %}

## Features

- TODO

## Developing

If you don't already have poetry installed on your system, you can use:

```bash
$ {% if cookiecutter.use_just == "y" %}just{% else %}make{% endif %} poetry-download
```

Then install all the dependencies:

```bash
{% if cookiecutter.use_just == "y" -%}
$ just setup
{% else -%}
$ {% if cookiecutter.use_just == "y" %}just{% else %}make{% endif %} install
$ {% if cookiecutter.use_just == "y" %}just{% else %}make{% endif %} pre-commit-install
{% endif -%}
```

Run codestyle:

```bash
$ {% if cookiecutter.use_just == "y" %}just{% else %}make{% endif %} codestyle
```

If you want to run safety checks:

```bash
$ {% if cookiecutter.use_just == "y" %}just{% else %}make{% endif %} check-safety
```

If you want to run tests:

```bash
$ {% if cookiecutter.use_just == "y" %}just{% else %}make{% endif %} test
```

If you want to check types:

```bash
$ {% if cookiecutter.use_just == "y" %}just{% else %}make{% endif %} mypy
```

If you want to check everything:

```bash
$ {% if cookiecutter.use_just == "y" %}just{% else %}make{% endif %} lint
```

In order to submit a pull request, it is expected that you've written tests and documentation for your changes,
and that running `{% if cookiecutter.use_just == "y" %}just{% else %}make{% endif %} lint` passes without issue.

## Credits

This package was created with [Cookiecutter][cc] and the [`andrlik/cookiecutter-poetry-djangopackage`][acpd] template.

[cc]: https://github.com/audreyr/cookiecutter
[acpd]: https://github.com/andrlik/cookiecutter-poetry-djangopackage
