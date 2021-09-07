# Use cases

Some use cases for the docker image rocker/verse:

* Use RStudio from the web browser, even if you didn't install it. 

* Use a Unix terminal, even if you are on Windows.

* Use a specific version of R (e.g. latest or older releases).

Resources:

* Details of this image: https://hub.docker.com/r/rocker/verse

* Overview of other images: https://www.rocker-project.org/images/

## Usage with `docker`

The command below tells docker to do this:

* Run an ephemeral container running R 4.1.1.

* Access your home directory from the container.

* Make RStudio available at http://localhost:8787/.

* Set Username: rstudio and Password: yourpassword.

```bash
docker run --rm \
  -v ${HOME}:/home --workdir /home \
  -p 8787:8787 \
  -e PASSWORD=yourpassword \
  rocker/verse:4.1.1 
```

## Usage with `docker-compose`

```bash
# cd into this directory
docker-compose up
```

