# docker-syncthing

[![CircleCI](https://circleci.com/gh/mtlynch/docker-syncthing.svg?style=svg)](https://circleci.com/gh/mtlynch/docker-syncthing)
[![Docker Version](https://img.shields.io/docker/v/mtlynch/syncthing?sort=semver&maxAge=86400)](https://hub.docker.com/r/mtlynch/syncthing/)
[![Docker Pulls](https://img.shields.io/docker/pulls/mtlynch/syncthing.svg?maxAge=604800)](https://hub.docker.com/r/mtlynch/syncthing/)
[![License](http://img.shields.io/:license-mit-blue.svg?style=flat-square)](LICENSE)

Unofficial Docker image of syncthing

## Overview

This is a Docker image for Syncthing built specifically for [deploying on fly.io](https://github.com/mtlynch/syncthing-fly.io).

For a more general-purpose Syncthing Docker image, see [linuxserver/docker-syncthing](https://github.com/linuxserver/docker-syncthing).

## Build from source

```bash
docker build -t syncthing

docker run \
  --name=syncthing \
  -e PUID=1000 \
  -e PGID=1000 \
  -e TZ=Etc/UTC \
  -p 8384:8384 \
  -p 22000:22000/tcp \
  -p 22000:22000/udp \
  -p 21027:21027/udp \
  -v ./data:/var/syncthing \
  --restart unless-stopped \
  syncthing
```
