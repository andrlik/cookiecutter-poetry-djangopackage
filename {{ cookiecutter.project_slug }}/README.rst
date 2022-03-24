{% set is_open_source = cookiecutter.open_source_license != 'Not open source' -%}
{% for _ in cookiecutter.project_name %}={% endfor %}
{{ cookiecutter.project_name }}
{% for _ in cookiecutter.project_name %}={% endfor %}

{% if is_open_source %}
.. image:: https://img.shields.io/pypi/v/{{ cookiecutter.project_slug }}.svg
        :target: https://pypi.python.org/pypi/{{ cookiecutter.project_slug }}

.. image:: https://img.shields.io/github/license/{{ cookiecutter.github_username }}/{{ cookiecutter.project_slug }}
        :target: https://github.com/{{ cookiecutter.github_username }}/{{ cookiecutter.project_slug }}/blob/main/LICENSE
        :alt: License {{ cookiecutter.open_source_license }}

.. image:: https://img.shields.io/badge/code%20style-black-000000.svg
        :target: https://github.com/ambv/black
        :alt: Black code style

.. image:: https://img.shields.io/badge/pre--commit-enabled-brightgreen?logo=pre-commit&logoColor=white
        :target: https://github.com/{{ cookiecutter.github_username }}/{{ cookiecutter.project_slug }}/blob/main/.pre-commit-config.yaml
        :alt: Pre-commit

.. image:: https://img.shields.io/badge/security-bandit-green.svg
        :target: https://github.com/PyCQA/bandit
        :alt: Security: bandit

.. image:: https://img.shields.io/badge/%20%20%F0%9F%93%A6%F0%9F%9A%80-semantic--versions-e10079.svg
        :target: https://github.com/{{ cookiecutter.github_username }}/{{ cookiecutter.project_slug }}/releases

.. image:: https://github.com/{{ cookiecutter.github_username }}/{{ cookiecutter.project_slug }}/actions/workflows/test.yml/badge.svg?branch=main
        :target: https://github.com/{{ cookiecutter.github_username }}/{{ cookiecutter.project_slug }}/actions/workflows/test.yml
        :alt: Build status badge

.. image:: https://github.com/{{ cookiecutter.github_username }}/{{ cookiecutter.project_slug }}/actions/workflows/codestyle.yml/badge.svg?branch=main
        :target: https://github.com/{{ cookiecutter.github_username }}/{{ cookiecutter.project_slug }}/actions/workflows/codestyle.yml
        :alt: Codestyle test status

 {% if cookiecutter.use_coveralls == 'y' %}

.. image:: https://coveralls.io/repos/github/{{ cookiecutter.github_username }}/{{ cookiecutter.project_slug }}/badge.svg?branch=main
        :target: https://coveralls.io/github/{{ cookiecutter.github_username }}/{{ cookiecutter.project_slug }}?branch=main
        :alt: Code coverage badge

 {% endif %}


.. image:: https://readthedocs.org/projects/{{ cookiecutter.project_slug | replace("_", "-") }}/badge/?version=latest
        :target: https://{{ cookiecutter.project_slug | replace("_", "-") }}.readthedocs.io/en/latest/?version=latest
        :alt: Documentation Status


{%- endif %}

{{ cookiecutter.project_short_description }}

{% if is_open_source %}
* Free software: {{ cookiecutter.open_source_license }}
* Repository and Issue Tracker: https://github.com/{{ cookiecutter.github_username }}/{{ cookiecutter.project_slug}}/
* Documentation: https://{{ cookiecutter.project_slug | replace("_", "-") }}.readthedocs.io.
{% endif %}

Features
---------

- TODO

Credits
--------

This package was created with Cookiecutter_ and the `andrlik/cookiecutter-poetry-djangopackage`_ template.

.. _Cookiecutter: https://github.com/audreyr/cookiecutter
.. _`andrlik/cookiecutter-poetry-djangopackage`: https://github.com/andrlik/cookiecutter-poetry-djangopackage
