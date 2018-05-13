# mitmproxy

Containerized version of [mitmproxy](https://mitmproxy.org/), an interactive SSL-capable intercepting HTTP proxy.

# Usage

```sh
$ docker run --rm -it [-v ~/.mitmproxy:/home/mitmproxy/.mitmproxy] -p 8080:8080 mitmproxy/mitmproxy
```
The *volume mount* is optional: It's to store the generated CA certificates.

Once started, mitmproxy listens as a HTTP proxy on `localhost:8080`:
```sh
$ http_proxy=http://localhost:8080/ curl http://example.com/
$ https_proxy=http://localhost:8080/ curl -k https://example.com/
```

You can also start `mitmdump` by just adding that to the end of the command-line:
```sh
$ docker run --rm -it -p 8080:8080 mitmproxy/mitmproxy mitmdump
```

For `mitmweb`, you also need to expose port 8081:
```sh
# this makes :8081 accessible to the local machine only
$ docker run --rm -it -p 8080:8080 -p 127.0.0.1:8081:8081 mitmproxy/mitmproxy mitmweb
```

You can also pass options directly via the CLI:
```sh
$ docker run --rm -it -p 8080:8080 mitmproxy/mitmproxy mitmdump --set ssl_insecure=true
```

For further details, please consult the mitmproxy [documentation](http://docs.mitmproxy.org/en/stable/).

# Tags

The available release tags can be seen [here](https://hub.docker.com/r/mitmproxy/mitmproxy/tags/).

---

Thanks to [Werner Beroux](https://github.com/wernight) and [David Weinstein](https://github.com/dweinstein) for their invaluable help with the mitmproxy Docker images!
