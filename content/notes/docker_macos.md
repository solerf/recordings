+++
title = 'Docker macos'
date = '2025-10-22T17:54:10+02:00'
draft = false
tags = ['docker', 'macos']
+++

When running `docker` in `macos` after a fresh install it might happen to complain about:

```shell
docker: Cannot connect to the Docker daemon at unix:///var/run/docker.sock. Is the docker daemon running?.
```

For those cases usually also installing `docker-desktop` should be enough, if not do the following:

```shell
sudo ln -s ~/Library/Containers/com.docker.docker/Data/docker.raw.sock /var/run/docker.sock
```

After this, it also might complain that the socket but from another location, like
`/Users/YOUR_USER/.docker/run/docker.sock`. In that case run the symlink again but pointing to this new location.

All this because ([docker_4.13.0](https://docs.docker.com/desktop/release-notes/#for-mac-63)):
> By default Docker will not create the /var/run/docker.sock symlink on the host and use the docker-desktop CLI context
> instead.

Source: https://stackoverflow.com/questions/44084846/cannot-connect-to-the-docker-daemon-on-macos

If not wanting to use `docker` the alternatives are:

- [OrbStack](https://orbstack.dev/)
- [Colima](https://github.com/abiosoft/colima)
- [Podman](https://podman.io/)
