## Managing images

Objectives:

* List and filter docker images, e.g. "dangling" images.

```bash
docker images ubuntu
```
* Remove one and multiple images at once.

```bash
docker rmi ubuntu 14.04

docker images ubuntu -q | xargs docker rmi
```

* Understand the need of the [versioned
image-stack](https://www.rocker-project.org/images/) for reproducible research.

* Learn how to use the latest, development, and specific versions of R.

```bash
docker run --rm -ti rocker/verse:latest bash

docker run --rm -ti rocker/verse:devel bash

docker run --rm -ti rocker/verse:4.0.3 bash
```

