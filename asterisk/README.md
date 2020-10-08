# Asterisk
## Build

_Watch for line endings in .sh files, should be set to LF_
_When using Zoiper make sure to set the host local IP as the outbound proxy_

```
docker build -t docker-voice/asterisk .
```

## Run
```
docker run -it -p 5060:5060/udp -p 8088:8088 --expose=10000-20000 docker-voice/asterisk:latest
```