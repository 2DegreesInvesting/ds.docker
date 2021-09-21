## Managing images

* List all images and filter some

```bash
docker images

docker images ubuntu
```

* Remove one and multiple images at once.

```bash
docker rmi ubuntu:14.04

docker images ubuntu -q | xargs docker rmi
```

* [Show untagged images
(dangling)](https://docs.docker.com/engine/reference/commandline/images/#filtering).

* The [versioned image-stack](https://www.rocker-project.org/images/) helps reproduce analyses.

* Use the latest, development, and specific versions of R.

```bash
docker run --rm -ti rocker/verse:latest bash

docker run --rm -ti rocker/verse:devel bash

docker run --rm -ti rocker/verse:4.0.3 bash
```

