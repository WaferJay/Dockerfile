
# Fiddler

## Fiddler Alpha for Mono

The origin of binary files is <http://fiddler.wikidot.com/mono>. 

Download link: [4.4.8.4 Built: June 13 2014](http://ericlawrence.com/dl/MonoFiddler-v4484.zip).

## How to use

Run it like many other X Window Client in docker.

```shell
docker build -t waferjay/fiddler:4.4.8.4 .
xhost +
docker run -d --net=host \
        -e DISPLAY=$DISPLAY \
        -v /tmp/.X11-unix:/tmp/.X11-unix \
        waferjay/fiddler:4.4.8.4
```

Note that `--net=host` is required when you will access Fiddler Echo Service (Proxy listens on default port 8888).
