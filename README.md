
# electrumx-docker

[![Image Layers](https://images.microbadger.com/badges/image/peerchemist/electrumx.svg)](https://microbadger.com/images/peerchemist/electrumx)
[![Docker Pulls](https://img.shields.io/docker/pulls/peerchemist/electrumx.svg)](https://hub.docker.com/r/peerchemist/electrumx/)

An easily configurable Docker image for running an Electrum server.

## Run

Make sure your local docker and docker-compose installation can handle docker-compose syntax `3.5`. This basically means: "run latest code".

> mkdir -p  /opt/electrum/{peercoin,db}

> docker-compose up -d

or

```
docker run \
  -v $HOME/electrumx:/data \
  -e DAEMON_URL=user:pass@host \
  -e COIN=Peercoin \
  -p 50002:50002 \
  peerchemist/electrumx
```

## Tweak

Edit "environment" sections of `peercoind` and `electrumx` in `docker-compose.yml` to setup the ElectrumX daemon.
Note: Your electrumx DAEMON_URL **must** end in `@peercoind` e. g. `DAEMON_URL=USER:PASS@peercoind`

You can view all ElectrumX environment variables here: https://github.com/kyuupichan/electrumx/blob/master/docs/environment.rst
