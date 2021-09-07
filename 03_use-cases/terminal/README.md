# Use a unix terminal, even if you are on windows

* Run an ephemeral, interactive bash terminal.

* Access your home directory from the container.

* Ensure you own any file in your home that you create or modify from
  the container.

```bash
docker run --rm -ti \
  -v "${HOME}:/home" --workdir /home \
  --user docker \
  rocker/r-base bash
```

Or `cd` into this directory, start the terminal with `docker-compose run --rm app`,
exit it with `exit`, and stop the container with `docker-compose down`.
