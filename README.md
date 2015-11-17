# docker-releases
Docker releases for for the mitmproxy project

# Usage

Pull the release you'd like from [Docker hub](https://hub.docker.com/r/mitmproxy/releases/). The release tags can be seen [here](https://hub.docker.com/r/mitmproxy/releases/tags/).


For example:

```sh
docker pull mitmproxy/releases:0.12.1
docker run -t -i --rm -v `pwd`:/data mitmproxy/releases:0.12.1 /bin/bash
root@aa92bad91dd7:/# mitmdump -n -r /data/log.mitmproxy
172.16.1.13 GET http://media.admob.com/sdk-core-v40.js
 << 200 OK 49.57kB
172.16.1.13 POST https://74.6.34.30/aap.do
 << 200 OK 0B
172.16.1.13 GET http://googleads.g.doubleclick.net/mads/...
 << 200 OK 82B

```
