# valigator

> Check your backups before you wreck yourself !

[![Code Issues](https://www.quantifiedcode.com/api/v1/project/6b2de325c287407aaf4998cf49c1c09e/badge.svg)](https://www.quantifiedcode.com/app/project/6b2de325c287407aaf4998cf49c1c09e)

Use Docker to perform database backup validation.

This tool exposes a HTTP API to trigger a backup restoration inside a Docker container.

Supported databases:

* MongoDB
* MySQL (5.5/5.6)


## Setup

Ensure you have Python >= 3.4 installed on your machine.

Install the following dependencies:

```bash
$ sudo pip install -r requirements.txt
```

## Docker images

You'll need to build the Docker images:

```bash
$ docker build -t my_mongodb26 docker/mongodb
$ docker build -t my_mysql55 docker/mysql/55
```

Do not forget to update the *settings.py* file after changing the images name.

## Usage

Start the API:

```bash
$ sudo python valigator.py
```

## Notifications

A notification of failure is sent via email in the following cases:

* An error occured during the archive extraction
* An error occured during the restoration phasis
