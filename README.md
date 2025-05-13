# Overview

Docker Compose fo the Canton Network

Meant to be used with [central-proxy-docker](https://github.com/CryptoManufaktur-io/central-proxy-docker) for traefik
and Prometheus remote write; use `:ext-network.yml` in `COMPOSE_FILE` inside `.env` in that case.

## Quick Start

The `./cantond` script can be used as a quick-start:

`./cantond install` brings in docker-ce, if you don't have Docker installed already.

`cp default.env .env`

`nano .env` and adjust variables as needed.

`./cantond up`

## Software update

To update the software, run `./cantond update` and then `./cantond up`

## Customization

`custom.yml` is not tracked by git and can be used to override anything in the provided yml files. If you use it,
add it to `COMPOSE_FILE` in `.env`

## Version

canton-docker Docker uses a semver scheme.

This is canton-docker Docker v1.0.0
