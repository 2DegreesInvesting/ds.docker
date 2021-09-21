## Using and managing volumes and users

### `--volume /path/in/host:/path/in/container`

Volumes allow you to access directories in your (host) computer from inside a
docker container.

* Access you working directory inside the container at /home/rstudio

```bash
docker run --rm -ti -v $(pwd):/home/rstudio rocker/verse bash
```

### `--user rstudio`

`--user rstudio` allows you to own the files and directories you share with the
container, even if they are created or modified inside the container.

* Explore ownership when working from RStudio server, without `--user rstudio`
(above) and with it (below).

```bash
docker run --rm -ti -v $(pwd):/home/rstudio --user rstudio rocker/verse bash
```

### `-e ROOT=true`

In rstudio server, `-e ROOT=true` enables super user privileges (`sudo`) inside
the container.

```bash
docker run --rm \
    -v $(pwd):/home/rstudio \
    --user rstudio \
    -e ROOT=true \
    -e PASSWORD=123 \
    -p 8787:8787 \
    -d \
    rocker/verse:4.0.3

apt-get update
sudo apt-get update
```
