# Tornado Cookiecutter template

[![Build Status](https://travis-ci.org/hkage/cookiecutter-tornado.svg?branch=development)](https://travis-ci.org/hkage/cookiecutter-tornado)

This is my cookiecutter template to build a simple, fast and rock solid website based upon
the [Tornado](http://www.tornadoweb.org/) framework. There are quite many Tornado templates  out there,
but I wanted to start something from scratch, that fits my needs and evolves out
of years of experiences (positive and negative alike) with other Python based webframeworks
like Turbogears and Django.

Of course this template is not designed for larger data structures. The main
focus is on scalability, fast data access and small library dependencies.

## Features

* Configurable as a [Cookiecutter](https://github.com/audreyr/cookiecutter) template
* Basic [HTML5 Boilerplate](https://html5boilerplate.com/)
* (Optional) pytest
* (Optional) tox
* (Optional) [Bumpversion](https://github.com/peritus/bumpversion) for updating version information
* (Optional) Docker support
* (Optional) Vagrant support

## Usage

Install [Cookiecutter](https://github.com/audreyr/cookiecutter):

    $ pip install cookiecutter

Initialize the project with cookiecutter and answer some questions for the newly started project:

    $ cookiecutter https://github.com/hkage/cookiecutter-tornado

    project_name [project_name]: tornado_test
    project_slug [tornado_test]:
    author_name [Your name]: Your name
    email [Your e-mail]: yourname@example.com
    github_username [yourname]: yourusername
    repo_name [tornado-project]:
    description [A short description of the project.]: This is my Tornado project
    version [0.1.0]:
    use_pytest [y]: y
    use_tox [y]: y
    use_docker [y]: y
    use_vagrant [y]: y
    use_bumpversion [y]: y
    Select open_source_license:
    1 - MIT license
    2 - BSD license
    3 - ISC license
    4 - Apache Software License 2.0
    5 - GNU General Public License v3
    6 - Not open source
    Choose from 1, 2, 3, 4, 5, 6 [1]: 1

## Development

### Testing

All tests will be added to the `tests` directory, whether you are using pytest for testing or other tools like nose- or unittests.

#### pytest

With pytest you will be able to run the tests with:

    $ py.test

### Running the application

To start the final application, just run the following fabric command:

    $ fab devserver

This will tell Tornado to start the application with the default port 8888. If
you want to use another port, just type:

    $ fab devserver:port=8000

In addition to that, see the fabfile.py Script for other parameters and
commands.

#### Vagrant

To run the server within a Vagrant VM, you need to install Vagrant 1.7.x and
start the development server with the following command:

    $ vagrant up
    $ fab vagrant devserver

You can now access your application via `http://localhost:8000`

#### Docker

Install docker and docker compose in the latest version. Then start the tornado
project with docker-compose:

    $ docker-compose up

You can now access your application via `http://localhost:8000`
