# calibre
# docker run -d \
#   -v /media/books:/opt/calibre/library
#   -p  8080:8080
#   markhuge/calibre

FROM ubuntu:xenial

RUN apt-get update -y \
  && apt-get install -y calibre xvfb imagemagick\
  && apt-get clean \
  && rm -rf /var/cache/apt/* /var/lib/apt/lists/*

EXPOSE 8080

RUN mkdir /opt/calibre && mkdir /opt/calibre/library

VOLUME        ["/opt/calibre/library"]
ENTRYPOINT           ["/usr/bin/calibre-server", "--with-library=/opt/calibre/library"]
