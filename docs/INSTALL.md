# asciinema web app install guide

The only officially supported installation procedure of asciinema web app
is [Docker](https://www.docker.com/) based. You must have SSH access to a
64-bit Linux server with Docker support.

If you really, really want to install everything manually then look
at [Dockerfile](../Dockerfile) and [docker-compose.yml](../docker-compose.yml)
to see what's required by the app.

## Hmm, why Docker?

Hosting non-trivial web applications is complicated. Setting this one up
requires installation of fair number of system packages and build tools,
configuring monitoring of several processes, as well as configuring Nginx. Also,
you need PostgreSQL, Redis, and SMTP server.

With Docker, you get the battle tested configuration (similar to what's running
on asciinema.org), in a stable container, along with all required services
preconfigured.

It also makes upgrading to new versions much easier.

## Hardware Requirements

- modern single core CPU, dual core recommended
- 1 GB RAM minimum (with swap)
- 64 bit Linux compatible with Docker
- 10 GB disk space minimum

## Service Requirements

asciinema web app requires the following services:

- [Postgres 9.5+](http://www.postgresql.org/download/)
- [Redis 2.6+](http://redis.io/download)
- SMTP server

If you go with the provided [docker-compose.yml](../docker-compose.yml) file you
don't need to worry about these - they're included and already configured to
work with this app.

## Installation

This guide assumes you already
have [Docker engine](https://docs.docker.com/engine/)
and [docker-compose](https://docs.docker.com/compose/) running on the
installation host.

You don't have to use docker-compose to use asciinema web app Docker image. Feel
free to inspect docker-compose.yml file and run required services manually with
`docker run ...`. However, for the sake of simplicity and to miminize
configuration issues the rest of this guide is based on the provided/suggested
docker-compose configuration.

### TODO

...

## Using asciinema recorder with your instance

Once you have your instance running, point asciinema recorder to it by setting
API URL in `~/.config/asciinema/config` file as follows:

    [api]
    url = https://your.asciinema.host