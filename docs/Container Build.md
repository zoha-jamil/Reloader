# Container Build

> **WARNING:** As a user of Reloader there is no need to build containers, the open source version is available on [Docker Hub](https://hub.docker.com/r/stakater/reloader/).

Multi-architecture approach is based on original work by [@mdh02038](https://github.com/mdh02038/Reloader).

Images are tested on linux/arm, linux/arm64 and linux/amd64.

## Install Pre-Reqs

The build environment requires the following packages (tested on `Ubuntu 20.04`):

* Golang
* `make`
* `qemu` (for arm, arm64 etc. emulation)
* binfmt-support
* Docker engine

## Docker

Follow instructions on [Install using the apt repository](https://docs.docker.com/engine/install/ubuntu/#install-using-the-repository).

Once installed, enable the experimental CLI:

```bash
export DOCKER_CLI_EXPERIMENTAL=enabled
```

Login to enable publishing of packages:

```bash
sudo docker login
```

## Remaining Pre-Reqs

Remaining Pre-Reqs can be installed via:

```bash
sudo apt install golang make qemu-user-static binfmt-support -y
```

## Publish Multi-Architecture Image

To build/ publish multi-arch Docker images clone repository and execute from repository root:

```bash
sudo make release-all
```

## Additional Links/Info

[Building Multi-Architecture Docker Images With `Buildx`](https://medium.com/@artur.klauser/building-multi-architecture-docker-images-with-buildx-27d80f7e2408)
