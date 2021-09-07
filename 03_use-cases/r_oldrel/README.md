# Reproduce a problem you see with an older version of R

* Run an ephemeral container running R 3.6.

* Access your home directory from the container.

* Make RStudio available at http://localhost:8787/, so you can
  use the interactive dubugger.

* Set credentials: Username: rstudio and Password: yourpassword.

```bash
docker run --rm \
  -v ${HOME}:/home --workdir /home \
  -p 8787:8787 \
  -e PASSWORD=yourpassword \
  rocker/verse:3.6 
```

Or `cd` into this directory, start `RStudio` at from the web brower
at http://localhost:8787/ with `docker-compose run --rm app`,
quit R with `q()`, and stop the container with `docker-compose down`.
