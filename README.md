
# docker-electrumx

[![Build Status](https://travis-ci.org/lukechilds/docker-electrumx.svg?branch=master)](https://travis-ci.org/lukechilds/docker-electrumx)
[![Image Layers](https://images.microbadger.com/badges/image/lukechilds/electrumx.svg)](https://microbadger.com/images/lukechilds/electrumx)
[![Docker Pulls](https://img.shields.io/docker/pulls/lukechilds/electrumx.svg)](https://hub.docker.com/r/lukechilds/electrumx/)

> Run an Electrumx server with one command

An easily configurable Docker image for running an Electrumx server.

## Usage

```
docker run \
  -v /home/username/electrumx:/data \
  -e DAEMON_URL=http://user:pass@host:port \
  -e COIN=Groestlcoin \
  -p 50002:50002 \
  groestlcoin/electrumx
```

If there's an SSL certificate/key (`electrumx.crt`/`electrumx.key`) in the `/data` volume it'll be used. If not, one will be generated for you.

You can view all ElectrumX environment variables here: https://github.com/kyuupichan/electrumx/blob/master/docs/environment.rst

### TCP Port

By default only the SSL port is exposed. You can expose the unencrypted TCP port with `-p 50001:50001`, although this is strongly discouraged.

### Version

You can also run a specific version of ElectrumX if you want.

```
docker run \
  -v /home/username/electrumx:/data \
  -e DAEMON_URL=http://user:pass@host:port \
  -e COIN=Groestlcoin \
  -p 50002:50002 \
  groestlcoin/electrumx:version-1.9.1
```

## License

MIT © Luke Childs
