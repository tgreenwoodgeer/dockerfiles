# Mostly copied from @jfrazelle because she's the shit and my container hero
# Only diff is privoxy config and I'm using edge instead of latest alpine.
FROM alpine:edge
MAINTAINER Mark Wilkerson <mark@markwilkerson.me>

RUN apk --no-cache add privoxy
COPY privoxy.conf /etc/privoxy/config

EXPOSE 8118

RUN chown -R privoxy /etc/privoxy
USER privoxy

ENTRYPOINT [ "privoxy", "--no-daemon" ]
CMD [ "/etc/privoxy/config" ]

