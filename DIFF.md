# Reference of differences between the different PG 10.x images

## docker: bitnami/postgresql
* https://github.com/bitnami/bitnami-docker-postgresql/tree/master/10/debian-9
Data
    $BITNAMI_APP_DIR/data
    $BITNAMI_APP_VOL_PREFIX/conf
Docker-compose persistence
    /bitnami
    /opt/bitnami/postgresql/conf/
Env
    BITNAMI_APP_NAME
    BITNAMI_IMAGE_VERSION

    POSTGRESQL_PASSWORD                     fixed
    POSTGRESQL_USERNAME                     fixed
    POSTGRESQL_DATABASE                     fixed
    POSTGRESQL_MASTER_HOST                  doesn't seem to be used in timescale/timescaledb nor postgresql
    POSTGRESQL_MASTER_PORT_NUMBER           doesn't seem to be used in timescale/timescaledb nor postgresql
    POSTGRESQL_PORT_NUMBER                  doesn't seem to be used in timescale/timescaledb nor postgresql
    POSTGRESQL_REPLICATION_MODE             doesn't seem to be used in timescale/timescaledb nor postgresql
    POSTGRESQL_REPLICATION_PASSWORD         doesn't seem to be used in timescale/timescaledb nor postgresql
    POSTGRESQL_REPLICATION_USER             doesn't seem to be used in timescale/timescaledb nor postgresql

# docker: timescale/timescaledb
* https://github.com/timescale/timescaledb-docker
Data
    /var/lib/postgresql/data
Env
    POSTGRES_PASSWORD
    POSTGRES_USER
    PGDATA
    POSTGRES_DB
    TIMESCALEDB_TELEMETRY

# docker: postgres
* https://github.com/docker-library/postgres/10
Data
    /var/lib/postgresql/data
Env
    POSTGRES_PASSWORD
    POSTGRES_USER
    PGDATA
    POSTGRES_DB
    POSTGRES_INITDB_ARGS
    POSTGRES_INITDB_WALDIR

#PostgreSQL v10
# https://www.postgresql.org/docs/10/libpq-envars.html

    PGHOST
    PGHOSTADDR

    PGPORT
    PGDATABASE
    PGUSER
    PGPASSWORD

    PGPASSFILE
    PGSERVICE
    PGSERVICEFILE
    PGOPTIONS
    PGAPPNAME
    PGSSLMODE
    PGREQUIRESSL

    PGSSLCOMPRESSION
    PGSSLCERT
    PGSSLKEY
    PGSSLROOTCERT
    PGSSLCRL
    PGREQUIREPEER
    PGKRBSRVNAME
    PGGSSLIB
    PGCONNECT_TIMEOUT
    PGCLIENTENCODING
    PGTARGETSESSIONATTRS

    PGDATESTYLE
    PGTZ
    PGGEQO

    PGSYSCONFDIR
    PGLOCALEDIR