# Alpine Linux in Docker

### Current Alpine Version 3.6.2 (Released Jun 17, 2017)

This docker image is the base Alpine Linux.

----

## What is Alpine Linux?
Alpine Linux is a Linux distribution built around musl libc and BusyBox. The image is only 5 MB in size and has access to a package repository that is much more complete than other BusyBox based images. This makes Alpine Linux a great image base for utilities and even production applications. Read more about Alpine Linux here and you can see how their mantra fits in right at home with Docker images.

## How to use this image
#### Usage
Use like you would any other base image:

```
FROM dockerindo/alpine
RUN apk add --no-cache mysql-client
ENTRYPOINT ["mysql"]
```
This example has a virtual image size of only 36.5MB. Compare that to our good friend Ubuntu:

```
FROM ubuntu:16.04
RUN apt-get update \
    && apt-get install -y --no-install-recommends mysql-client \
    && rm -rf /var/lib/apt/lists/*
ENTRYPOINT ["mysql"]
```
This yields us a virtual image size of about 184MB image.

ref:
https://bitbucket.org/yobasystems/alpine
