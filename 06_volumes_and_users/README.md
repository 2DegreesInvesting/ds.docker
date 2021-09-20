## Using and managing volumes and users

### `--volume /path/in/host:/path/in/container`

Volumes allow you to access directories in your (host) computer from inside a
docker container.

* Access you working directory inside the container at /home/rstudio

```bash
docker run --rm \
    -v $(pwd):/home/rstudio \
    -e PASSWORD=123 \
    -p 8787:8787 \
    rocker/verse:4.0.3
```

### `--user rstudio`

`--user rstudio` allows you to own the files and directories you share with the
container, even if they are created or modified inside the container.

* Explore ownership when working from RStudio server

```bash
docker run --rm -ti -v $(pwd):/home/rstudio \
    -e PASSWORD=123 \
    -p 8787:8787 \
    -d \
    rocker/verse

touch a
ls -l
docker stop rstudio
ls -l
rm a
```

* Explore ownership with and without `--user rstudio`

```bash
docker run --rm -ti -v $(pwd):/home/rstudio --user rstudio rocker/verse bash
```

### `-e ROOT=true`

`-e ROOT=true` enables super user privileges (`sudo`) inside the container.

* Attempt to install `tree` without `-e ROOT=true`.

```bash
docker run --rm \
    -v $(pwd):/home/rstudio \
    --user rstudio \
    -e ROOT=true \
    -e PASSWORD=123 \
    -p 8787:8787 \
    -d \
    rocker/verse:4.0.3

tree
apt-get update & apt-get install tree
```
