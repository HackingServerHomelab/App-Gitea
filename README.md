# App-Gitea

## First Time Prerequisites

1. `rm ./Data/postgres/.gitkeep`
2. Run [Traefik](https://github.com/mattlombana/App-Traefik)

## Running the Containers

1. Update the following volumes in [docker-compose.yml](./Docker/docker-compose.yml)
    * `../Data/gitea:/data`
    * `../Data/postgres:/var/lib/postgresql/data`
2. Update the following environment variables in [docker-compose.yml](./Docker/docker-compose.yml)
    * `DB_PASSWD=changeme`
    * `POSTGRES_PASSWORD=changeme`
    * `DOMAIN=localhost`
3. Update the Traefik host label in [docker-compose.yml](./Docker/docker-compose.yml)
    * ``"traefik.http.routers.gitea.rule=Host(`localhost`)"``
4. Run `docker-compose -f ./Docker/docker-compose.yml up -d`

## First Time Setup

1. Visit <https://your-ip>
