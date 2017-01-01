# speedtest-cli
#
# docker run --rm markhuge/speedtest

FROM alpine

MAINTAINER Mark Wilkerson <mark@markwilkerson.me>

RUN apk --no-cache add python py-pip

RUN pip install speedtest-cli

ENTRYPOINT ["/usr/bin/speedtest-cli"]
