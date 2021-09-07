# Use the latest version of R and R packages without updating your system

* Run an ephemeral container running the latest (release) version of R.

* Access your home directory from the container.

* Ensure you own any file in your home that you create or modify from
  the container.

```bash
docker run --rm -ti \
  -v ${HOME}:/home --workdir /home \
  --user rstudio \
  rocker/verse R
```

Or `cd` into this directory, start `R` with `docker-compose run --rm app`,
quit R with `q()`, and stop the container with `docker-compose down`.
