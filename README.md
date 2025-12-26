# passh-static-binaries

passh-static-binaries for <https://github.com/clarkwang/passh>


```bash
docker run --pull always --name passh-static-binaries -d dyrnq/passh-static-binaries:master sh "tail -f /dev/null"
docker cp passh-static-binaries:/usr/bin/passh .
docker rm -f passh-static-binaries
./passh
```