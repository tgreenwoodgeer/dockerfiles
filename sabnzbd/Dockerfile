# sabnzbd
#
# docker run -d \
#   -v /etc/localtime:/etc/locatime:ro \
#   -v datadir:/datadir \
#   -v media:/media \
#   -p 8080:8080 \
#   markhuge/sabnzbd

FROM alpine:edge

MAINTAINER Mark Wilkerson <mark@markwilkerson.me>

RUN apk --no-cache --repository https://dl-3.alpinelinux.org/alpine/edge/testing add \
  autoconf \
  automake \
  ca-certificates \
  curl \
  g++ \
  git \
  make \
  py-cheetah \
  tar \
  unrar

# Install Sabnzbd
RUN curl -o /tmp/sabnzbd.tar.gz https://codeload.github.com/sabnzbd/sabnzbd/tar.gz/1.1.1 \
    && tar xzf /tmp/sabnzbd.tar.gz \
    && mv sabnzbd-* sabnzbd 

# Build par2
RUN curl -o /tmp/par2cmdline.tar.gz https://codeload.github.com/Parchive/par2cmdline/tar.gz/v0.6.14 \
    && tar xzf /tmp/par2cmdline.tar.gz -C /tmp \
    && cd /tmp/par2cmdline-* \
    && aclocal \
    && automake --add-missing \
    && autoconf \
    && ./configure \
    && make \
    && make install 

# Clean up build tools
RUN apk del \ 
  automake \
  autoconf \
  make \
  g++ 

EXPOSE 8080

VOLUME ["/datadir", "/media"]

WORKDIR /sabnzbd

ENTRYPOINT ["python", "SABnzbd.py"]

CMD ["-b","0","-f","/datadir/config.ini","-s", "0.0.0.0:8080"]
