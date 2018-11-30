# TimescaleDB

[TimescaleDB](https://www.timescale.com/) is an open-source time-series database powered by PostgreSQL.

## TL;DR;

```console
$ helm install ./timescaledb
```

## Introduction
This repo contains charts for [TimescaleDB](https://github.com/timescale/timescaledb-docker) deployment on a [Kubernetes](http://kubernetes.io) cluster using the [Helm](https://helm.sh) package manager.

Only single node configuration are supported for now.

# Rationale
The drive for this repo started after realization that the official helm chart for postgres did not longer provide proper support for TimescaleDB. While in the 1.0.1/9.6 chart used standard postgres:9.6 docker image, the new 2.x.x/10.x.x chart used bitnami/postgresql.
Since bitnami image uses different conventions than the official image, getting TimescaleDB to work with helm was no longer a matter of replacing the image:tag entry in values.yml.

An alternative approach would be to use a timescaledb image based on bitnami ( https://github.com/hsz-devops/timescaledb--timescaledb-docker )  on the 2.x image.

The charts included here are based on:
* @stable/postgresql 1.0.1 (_/postgres)
* @stable/postgresql 2.6.0 (bitnami/postgresql)

Besides the obvious differences in terms of environment variables, permissions, the 1.x image uses Deployments while 2.x uses StatefulSets.

The 1.x series is the easiest and more direct to get done, but has the objective to preserve compatibility for deployments that worked in the past, and with the non-bitnami image
The 2.x series is an attempt to migrate to STS and to an image that is due to be maintained.

# structures
    `./1.0-pg10-1x`     Deployment based chart, based on @stable/postgresql 1.x (non-bitnami)
    `./1.0-pg10-bn`     StatefulSet based chart, based on @stable/postgresql 1.x (bitnami)s

