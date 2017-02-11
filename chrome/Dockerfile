FROM ubuntu:16.04
MAINTAINER Mark Wilkerson <mark@markwilkerson.me>

RUN apt-get update && apt-get install -y \
    chromium-browser 
ENTRYPOINT [ "/usr/bin/chromium-browser" ]
CMD [ "--user-data-dir=/data" ]

