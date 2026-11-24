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

## Participant ports

The participant Ledger API and Admin API listen on 5001 and 5002. Set `PARTICIPANT_LEDGER_API_PORT` and
`PARTICIPANT_ADMIN_API_PORT` in `.env` to move them; `participant.yml`, `validator.yml` and `rpc-shared.yaml` all read
the same two variables, so the validator follows. Anything else that dials the participant directly, such as a Traefik
route, `grpcurl` or a Canton console, needs the new ports too. The gRPC and HTTP health ports (5061, 5071), the JSON
API (7575) and metrics (10013) are unchanged.

## Customization

`custom.yml` is not tracked by git and can be used to override anything in the provided yml files. If you use it,
add it to `COMPOSE_FILE` in `.env`

## Version

canton-docker Docker uses a semver scheme.

This is canton-docker Docker v1.0.0
