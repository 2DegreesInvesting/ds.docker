
<!-- README.md is generated from README.Rmd. Please edit that file -->
<!-- README.md is generated from README.Rmd. Please edit that file -->

A series of meetups about using Docker for data science with R.

## Syllabus

The goal is to lean how to use Docker images for data science with R.
The focus is not on building your own Docker images but instead on using
existing images – particularly those from the
[Rocker](https://www.rocker-project.org) project.

At the end of this series you will be able to do things like these:

-   [ ] Use a Unix terminal, even if you are on Windows.
-   [ ] Use the latest version of R and R packages, without updating
    your own system.
-   [ ] Reproduce a problem you see with an older version of R.
-   [ ] Reproduce a problem you see with the development version of R.
-   [x] Use RStudio from the web browser, even if it’s not installed on
    your computer.
-   [ ] Share your computing environment with others so they can
    reproduce your analysis.

Each item in this syllabus corresponds to a meetup and a GitHub
[release](https://github.com/2DegreesInvesting/ds.docker/releases) that
preserves a snapshot of this repository exactly as it was shown during
thee meetup.

## Getting started with the Rocker project

This meetup introduces the Rocker project. It covers [Getting
started](https://www.rocker-project.org/) and
[volumes](https://www.rocker-project.org/use/shared_volumes/).

Objectives:

-   Run R in a docker container.
-   Run RStudio in a docker container and access it from the web
    browser.
-   Share a volume between the host computer and the Docker container.

## `docker-compose` and .env files.

`docker-compose` is a tool used to organize and simplify running Docker
containers. This sessions will cover basic usage of `docker-compose` to
specify options, and provide a consistent command for working with
Docker. We will also cover the use of .env files for storing secure
secrets.

## Use cases

This meetup covers how to start containers for common use cases like the
ones listed in the introduction of this [Syllabus](#syllabus). The goal
is to clarify what we’ve covered so far with concrete examples you’re
likely to use. This is a good stopping point if you are only interested
in the usage – not the management – of docker containers.

Objectives:

-   Revisit how to run containers with `docker` and `docker-compose`.
-   Ask questions.
-   Hear what’s next so you decide if you want to stop now.

## Managing containers

Objectives:

-   Run and name a persistent containers.
-   View the status of a container.
-   Stop, start, and attach a container.
-   Remove a container.
-   Stop and remove multiple containers at once.

## Next

-   Managing images
-   [Managing users](https://www.rocker-project.org/use/managing_users/)

## Resources

-   [Audience and
    importance](https://github.com/2DegreesInvesting/ds-incubator/issues/74).
-   [Get Docker](https://docs.docker.com/get-docker/).
-   [The Rocker project](https://www.rocker-project.org/).
-   [Reference](https://docs.docker.com/reference/).
