# [Getting started with the Rocker project](https://github.com/2DegreesInvesting/ds.docker#getting-started-with-the-rocker-project)

This document shows how to find the information you need to learn Docker from
examples in the wild.

## [Run R inside a container](https://www.rocker-project.org/):

```bash
docker run -e PASSWORD=yourpassword --rm -p 8787:8787 rocker/rstudio
```

Add a volume mount

```bash
docker run -e PASSWORD=yourpassword --rm --mount type=bind,source="$(pwd)"/R,target=/home/rstudio/R -p 8787:8787 rocker/rstudio
```

move password to `.env`. Now we can add `.env` to `.gitignore`

```bash
docker run --rm --env-file .env --mount type=bind,source="$(pwd)"/R,target=/home/rstudio/R -p 8787:8787 rocker/rstudio
```

## Docker-compose

see `docker-compose.yml`

```bash
docker-compose up
```

