# sickbeard
# docker run -d \
#   -v /etc/localtime:/etc/localtime \
#   -v /var/sickbeard:/datadir \
#   -v /media:/media \
#   -p 8081:8081 \
#   markhuge/sickbeard 

FROM alpine:edge

MAINTAINER Mark Wilkerson <mark@markwilkerson.me>

RUN apk --no-cache --repository https://dl-3.alpinelinux.org/alpine/edge/testing add \
    ca-certificates \
    git \
    py-cheetah 

RUN git clone git://github.com/midgetspy/Sick-Beard.git /sickbeard

VOLUME ["/datadir", "/media"]

EXPOSE 8081

WORKDIR /sickbeard

ENTRYPOINT [ "python", "SickBeard.py" ]

CMD [ "--datadir", "/datadir" ]
