# Managing containers

```
docker -ps --help
```

Explore an ephemeral container (`--rm`).

```
docker run  --rm -ti rocker/r-base

docker ps
docker ps -a
```

Managing a single persistent container (default).

* run R
* stop

* create
* start
* attach
* exec
* stop
* remove

The `-q` flag.

Managing multiple containers at once

* Stop in batch
* Remove in batch

Managing with docker-compose

### Reference

* https://www.rocker-project.org/
* https://docs.docker.com/engine/reference/commandline/docker/

