# Vim  - all my vims

# Helper function to run this as expected:
#container_home=/home/user
#
#
#v () {
#  container_home=/home/user
#  current_dir=${$(pwd)/$HOME/$container_home}
#  if [[ "$1" = "." || -z "$1" ]]; then
#    cmd=$current_dir
#  elif [[ "$1" =~ "^$HOME" ]]; then
#    cmd=${1/"$HOME"/"$container_home"}
#  else
#    cmd=$current_dir/$1
#  fi
#
#  docker run -it --rm \
#    -v /etc/localtime:/etc/localtime \
#    -v $HOME:$container_home \
#    -v $HOME/.vim:$container_home/.vim \
#    -v $HOME/.vimrc:$container_home/.vimrc \
#    -w $current_dir \
#  markhuge/vim \
#  vim $cmd 
#}


FROM alpine:edge

MAINTAINER Mark Wilkerson <mark@markwilkerson.me>

RUN addgroup -g 1000 user \
    && adduser -D -h /home/user -G user -u 1000 user

RUN apk --no-cache add vim python3 git

USER user
ENV HOME /home/user
ENV TERM xterm-256color
RUN mkdir $HOME/.vim

ENV LANG C.UTF-8

CMD vim
