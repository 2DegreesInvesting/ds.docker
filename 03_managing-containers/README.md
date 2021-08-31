
# Managing images and containers

Run some containers for examples

``` bash
docker run -ti --name container1 rocker/r-base
docker run --rm -ti --name container2 rocker/r-base bash
```

## View docker containers

<https://docs.docker.com/engine/reference/commandline/ps/>

``` bash
docker ps --help

Usage:  docker ps [OPTIONS]

List containers

Options:
  -a, --all             Show all containers (default shows just running)
  -f, --filter filter   Filter output based on conditions provided
      --format string   Pretty-print containers using a Go template
  -n, --last int        Show n last created containers (includes all
                        states) (default -1)
  -l, --latest          Show the latest created container (includes all
                        states)
      --no-trunc        Don't truncate output
  -q, --quiet           Only display container IDs
  -s, --size            Display total file sizes
```

View the status of all containers (running and stopped).

``` bash
docker ps -a
CONTAINER ID   IMAGE            COMMAND   CREATED       STATUS          PORTS                    NAMES
a20382c347e0   rocker/r-base    "R"       2 hours ago   Up 16 minutes                            container1
02ff4fc328b7   rocker/rstudio   "/init"   3 hours ago   Up 3 hours      0.0.0.0:8787->8787/tcp   busy_mayer
```

## Stop a container

``` bash
docker stop container1
```

## Start a stopped container

``` bash
docker start container1
```

## Excecute commands on a running container

``` bash
# Excecute a command directly from outside the container
docker exec container1 Rscript -e "install.packages('fs')"
# Or execute bash, then any command from inside the container, interactively
docker exec -ti container1 bash
```

## Remove all stopped containers (but not any actively running ones)

<https://docs.docker.com/engine/root/reference/commandline/rm/>

``` bash
docker rm --help

Usage:  docker rm [OPTIONS] CONTAINER [CONTAINER...]

Remove one or more containers

Options:
  -f, --force     Force the removal of a running container (uses SIGKILL)
  -l, --link      Remove the specified link
  -v, --volumes   Remove anonymous volumes associated with the container
```

``` bash
docker rm -v $(docker ps -a -q)
```

## View docker images

Reference:
<https://docs.docker.com/engine/reference/commandline/docker/images>

``` bash
docker images
REPOSITORY       TAG          IMAGE ID       CREATED       SIZE
rocker/r-ver     devel        5f728922df7b   7 days ago    851MB
pacta_core       0.0.0.9000   cab779f97b4b   8 days ago    1.01GB
rocker/verse     latest       d9b99cc8f314   11 days ago   3.58GB
rocker/rstudio   latest       aef29a109e47   11 days ago   1.93GB
rocker/r-ver     4.1          b9961cf6ee0e   11 days ago   851MB
r-base           latest       c27c3714f004   2 weeks ago   762MB
rocker/r-base    latest       70afd999e53f   3 weeks ago   776MB
rocker/r-ver     latest       d9f4d826c19c   3 weeks ago   851MB
ubuntu           latest       1318b700e415   5 weeks ago   72.8MB
```

View images

``` bash
docker images
REPOSITORY       TAG          IMAGE ID       CREATED       SIZE
rocker/r-ver     devel        5f728922df7b   7 days ago    851MB
pacta_core       0.0.0.9000   cab779f97b4b   8 days ago    1.01GB
rocker/verse     latest       d9b99cc8f314   11 days ago   3.58GB
rocker/rstudio   latest       aef29a109e47   11 days ago   1.93GB
rocker/r-ver     4.1          b9961cf6ee0e   11 days ago   851MB
r-base           latest       c27c3714f004   2 weeks ago   762MB
rocker/r-base    latest       70afd999e53f   3 weeks ago   776MB
rocker/r-ver     latest       d9f4d826c19c   3 weeks ago   851MB
ubuntu           latest       1318b700e415   5 weeks ago   72.8MB
```

View images from a specific repository

``` bash
docker images rocker/r-ver
REPOSITORY     TAG       IMAGE ID       CREATED       SIZE
rocker/r-ver   devel     5f728922df7b   7 days ago    851MB
rocker/r-ver   4.1       b9961cf6ee0e   11 days ago   851MB
rocker/r-ver   latest    d9f4d826c19c   3 weeks ago   851MB
```

Filter images with a reference (repository:tag) pattern

<https://docs.docker.com/engine/reference/commandline/images/#filtering>

``` bash
docker images --filter "reference=rocker/*latest"
REPOSITORY       TAG       IMAGE ID       CREATED       SIZE
rocker/verse     latest    d9b99cc8f314   11 days ago   3.58GB
rocker/rstudio   latest    aef29a109e47   11 days ago   1.93GB
rocker/r-base    latest    70afd999e53f   3 weeks ago   776MB
rocker/r-ver     latest    d9f4d826c19c   3 weeks ago   851MB
```

Show and untagged images (dangling)

``` bash
docker images --filter "dangling=true" -q
```

Remove and untagged images (dangling)

``` bash
docker images --filter "dangling=true" -q | xargs docker rmi

# Same
docker rmi $(docker images --filter "dangling=true" -q)
```

## Resources

<https://www.rocker-project.org/use/managing_containers/>

<https://docs.docker.com/engine/reference/commandline/docker/>
