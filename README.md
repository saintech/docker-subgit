### SubGit in a docker.

[![Pulls on Docker Hub](https://img.shields.io/docker/pulls/saintech/subgit.svg)](https://hub.docker.com/r/saintech/subgit) [![](https://images.microbadger.com/badges/image/saintech/subgit.svg)](https://microbadger.com/images/saintech/subgit)

[Docker Image](https://registry.hub.docker.com/u/saintech/subgit/) with SubGit. It's using tiny image provided by Alpine.  

[SubGit Website](https://subgit.com/)  

Purpose of this image was to simplify the process of using SubGit.

Workdir is set to `/subgit`

### Usage

    docker run \
      -ti \
      --name subgit \
      polinux/subgit \
      subgit <subgit-commands>

Mount Volume into working directory

    docker run \
      -ti \
      --name subgit \
      -v ${PWD}/workdir:/subgit \
      polinux/subgit \
      subgit <subgit-commands>

### Build

    docker build -t polinux/subgit .

Docker troubleshooting
======================

Use docker command to see if all required containers are up and running:
```
$ docker ps
```

Check logs of subgit server container:
```
$ docker logs subgit
```

Sometimes you might just want to review how things are deployed inside a running
 container, you can do this by executing a _bash shell_ through _docker's
 exec_ command:
```
docker exec -ti subgit /bin/bash
```

History of an image and size of layers:
```
docker history --no-trunc=true polinux/subgit | tr -s ' ' | tail -n+2 | awk -F " ago " '{print $2}'
```

## Author

- Przemyslaw Ozgo (<linux@ozgo.info>)
- [saintech](https://github.com/saintech)
