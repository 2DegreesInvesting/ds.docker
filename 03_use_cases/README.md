# Use cases of the docker image rocker/verse

All of these use cases do the following:

* Allow you to interact with the container (`ti`).

* Remove the container when you exit it (`--rm`).

* Make your local home directory available in the container at /home
  (`${HOME}:/home`).

* Make /home the working directory (`--workdir /home`).

* Make you the owner of any file you create or modify from inside the
  container (`--user rstudio`).

Resources:

* Details of this image: https://hub.docker.com/r/rocker/verse

* Overview of other images: https://www.rocker-project.org/images/

## Use case 1: Use a terminal (`bash`)

You may use it to access a unix terminal (like in mac and linux)
from windows.

```bash
docker run -ti  --rm -v ${HOME}:/home --workdir /home --user rstudio rocker/verse bash
```

## Use case 2: Use the latest version of R (`R`)

You may use it to try the latest version of R without changing the
versoin installed in your computer.

```bash
docker run -ti  --rm -v ${HOME}:/home --workdir /home --user rstudio rocker/verse R
```

## Use case 3: Use a specific versoin of R, e.g. 4.0 (`rocker/verse:4.0`)

You may use it to reproduce a bug exposed with R version 4.0, without
changing the version installed in your computer.

```bash
docker run -ti  --rm -v ${HOME}:/home --workdir /home --user rstudio rocker/verse:4.0 R
```

## Use case 4: Use RStudio from the web browser at <http://localhost:8787/>

You may use it to work with RStudio if it's not installed in your
computer.

```bash
docker run --rm -v ${HOME}:/home -e PASSWORD=yourpassword -p 8787:8787 rocker/verse
```

## What about `docker-compose`?

`docker` commands can be translated to the `docker-compose` syntax
and written to a docker-compose.yml file. This allows you to share a
computing a environment with your colleagues (e.g. ubuntu with R 4.1.1
and latest R packages) in three steps:

1. Clone the repository containing the docker-compose.yml file.
2. `cd` into your local copy of that repository.
3. Run `docker-compose up`.
