# docker-releases
Docker releases for for the mitmproxy project

# Download

Pull the release you'd like from [Docker hub](https://hub.docker.com/r/mitmproxy/releases/). The release tags can be seen [here](https://hub.docker.com/r/mitmproxy/releases/tags/).

```sh
$ docker pull mitmproxy/releases:0.14
```

# Example

With shared network with your host (e.g., on OS X and using `docker-machine`)

```sh
$ docker run -t -i --rm --net="host" mitmproxy/releases:0.14 mitmdump
192.168.99.1:59289: clientconnect
192.168.99.1 GET https://www.google.com/
 << 200 OK 187.61kB
 192.168.99.1:59289: clientdisconnect

# in another window/session...
$ https_proxy="http://$(docker-machine ip default):8080" curl -k -L https://www.google.com
```

