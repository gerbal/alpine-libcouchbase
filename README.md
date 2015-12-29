# alpine-libcouchbase
Alpine APK package for libcouchbase

APK build using [dnephin/docker-apk-build](https://github.com/dnephin/docker-apk-build)

See Releases for relese versions

Install in a docker image add this to your alpine docker file:

```
RUN curl -Ls https://github.com/gerbal/alpine-libcouchbase/releases/download/2.5.4/libcouchbase-2.5.4-r0.apk > /tmp/libcouchbase.apk && \ 
    apk-install --allow-untrusted /tmp/libcouchbase.apk && \
    rm /tmp/libcouchbase.apk
```