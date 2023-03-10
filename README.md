## Usage

To get started, make sure you have [Docker installed](https://docs.docker.com/docker-for-mac/install/) on your system, and then clone this repository.

Next, navigate in your terminal to the directory you cloned this, and spin up the containers for the web server by running `docker-compose up -d --build`.

After that completes, follow the steps from the [src/README.md](src/README.md) file to get your Laravel project added in (or create a new blank one).

Bringing up the Docker Compose network with `site` instead of just using `up`, ensures that only our site's containers are brought up at the start, instead of all of the command containers as well. The following are built for our web server, with their exposed ports detailed:

- **nginx** - `:80`
- **mysql** - `:3306`
- **postgres** - `:5432`
- **php** - `:9000`






## MailHog

The current version of Laravel (8 as of today) uses MailHog as the default application for testing email sending and general SMTP work during local development. Using the provided Docker Hub image, getting an instance set up and ready is simple and straight-forward. The service is included in the `docker-compose.yml` file, and spins up alongside the webserver and database services.

To see the dashboard and view any emails coming through the system, visit [localhost:8025](http://localhost:8025) after running `docker-compose up -d site`.

## Access The CLI

docker ps

docker exec -it <redis container ID> redis-cli 

## PSQL Access & Export Import

docker exec -it <postgres container ID> bash

root@containerID:/# psql -U postgres

`docker exec -i pg_container_name pg_dump --username pg_username --password pg_password database_name > /desired/path/on/your/machine/dump.sql`

`docker exec -i pg_container_name psql --username pg_username --password pg_password database_name < /path/on/your/machine/dump.sql`


`docker volume create pgdata`

`docker volume inspect pgdata`

`docker network create DockerNet`

`docker network connect DockerNet postgres`

`docker network connect DockerNet php`

`docker network inspect DockerNet`
