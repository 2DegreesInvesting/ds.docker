
## Using and managing volumes and users

Objectives:

* Create a volume to access your home directory from inside a container.

```bash
docker run --rm \
    -v $(pwd):/home/rstudio \
    --user rstudio \
    -e PASSWORD=123 \
    -p 8787:8787 \
    rocker/verse:4.0.3
```

* Use `--user rstudio` so you own the files and directories you share with the
container and modified from it.

```bash
docker run --rm -ti -v $(pwd):/home/rstudio --user rstudio rocker/verse bash
```

* Use `-e ROOT=true` so you can use `sudo` inside the container.

```bash
docker run --rm \
    -v $(pwd):/home/rstudio \
    --user rstudio \
    -e ROOT=true \
    -e PASSWORD=123 \
    -p 8787:8787 \
    rocker/verse:4.0.3
```
