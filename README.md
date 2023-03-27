# Sven Co-op Dedicated Server in Docker

Sven Co-op (abbreviated as SC) is a co-op variation of the 1998 first-person shooter Half-Life. The game, initially released as a mod in January 1999, enables players to play together on online servers to complete levels, many which are based on the Half-Life universe but include other genres. The standalone release, available free of charge, representing version 5.0 of the mod, was released in January 2016.

![Sven Co-op Screenshot](./.misc/screenshot1.jpg "Sven Co-op Screenshot")

## Linux

[![linux/amd64](https://github.com/emicba/gamesvr-svencoop/actions/workflows/build-linux-image.yml/badge.svg?branch=main)](https://github.com/emicba/gamesvr-svencoop/actions/workflows/build-linux-image.yml)

### Download

```shell
docker pull ghcr.io/emicba/gamesvr-svencoop;
```

### Run Self Tests

The image includes a test script that can be used to verify its contents.

```shell
docker run -it --rm ghcr.io/emicba/gamesvr-svencoop ./ll-tests/gamesvr-svencoop.sh;
```

### Run with rootless Docker

```shell
docker run -it --rm -p 27015:27015 -p 27015:27015/udp ghcr.io/emicba/gamesvr-svencoop;
```

### Run Interactive Server

```shell
docker run -it --rm --net=host ghcr.io/emicba/gamesvr-svencoop ./svends_run -num_edicts 3072 +sv_lan 1;
```
