# speedtest-cli
#
# docker run --rm markhuge/speedtest

FROM alpine:edge

MAINTAINER Mark Wilkerson <mark@markwilkerson.me>

RUN apk --no-cache add python py2-pip

RUN pip install speedtest-cli

ENTRYPOINT ["/usr/bin/speedtest-cli"]
