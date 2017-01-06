# weechat
# docker run -it --rm \
#   -v /etc/localtime:/etc/localtime:ro \
#   -v $HOME/.weechat:/root/.weechat \
#   markhuge/weechat
FROM alpine

MAINTAINER Mark Wilkerson <mark@markwilkerson.me>

RUN apk --no-cache add weechat weechat-python weechat-ruby weechat-aspell 

ENTRYPOINT ["/usr/bin/weechat"]
