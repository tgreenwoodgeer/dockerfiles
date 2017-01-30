# transmission-daemon
# modified from jess/transmission
#
# docker run -d \
#   -v $HOME/Downloads/Torrents:/transmission/download \
#   -p 9091:9091 -p 51413:51413 -p 51413:51413/udp \
#   --name transmission \
#   markhuge/transmission

FROM alpine:edge

MAINTAINER Mark Wilkerson <mark@markwilkerson.me>

RUN apk --no-cache add transmission-daemon \
  && mkdir -p /transmission/{download,watch,incomplete,config} \
  && chmod 1777 /transmission

ENV TRANSMISSION_HOME /transmission/config

EXPOSE 9091

ENTRYPOINT ["/usr/bin/transmission-daemon"]
CMD [ "--allowed", "127.*,10.*,192.168.*,172.*", "--watch-dir", "/transmission/watch", "--encryption-preferred", "--foreground", "--config-dir", "/transmission/config", "--incomplete-dir", "/transmission/incomplete", "--dht", "--no-auth", "--download-dir", "/transmission/download" ]


