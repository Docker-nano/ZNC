Nano ZNC
========

[![Build status][Build image]][Build]

This is the [Docker Nano](https://github.com/Docker-nano) image for [ZNC](http://znc.in) v1.4 with IPv6 and SSL support.

* Docker Hub image: [`nano/znc`][Docker Hub repo]
* Size: ~9MB

The *run as root* restriction has been removed so the `-r` switch does nothing now.

Usage
-----

ZNC's runtime data directory is mapped to `/var/znc` and can be mirrored to the host using volumes as shown in the following commands. Additionally, ZNC's configuration directory is mapped to `/etc/znc`, but everything is accessible via `/var/znc`.

To create a new configuration run a command similar to the following. Make sure to specify the same port number in the run line and the configuration. When configuration is complete use [Ctrl]+[P], [Ctrl]+[Q] to detach from the Docker session.

* `docker run -itp 1337:1337 -v /var/znc:/var/znc nano/znc:latest znc -fc`

To run as a daemon using an existing configuration on the host try the following. Use `docker logs` to inspect the output if there is a problem.

* `docker run -dp 1337:1337 -v /var/znc:/var/znc nano/znc:latest`

  [Build]: http://travis-ci.org/Docker-nano/ZNC
  [Build image]: http://img.shields.io/travis/Docker-nano/ZNC.svg "Build status"
  [Docker Hub repo]: https://registry.hub.docker.com/u/nano/znc/

