# markhuge/vim

vim in a docker container

I added python3 to support UltiSnips and git to support git shiz.

I have a handy zsh function that makes this work the way you'd expect:

```
v () {
  container_home=/home/user
  current_dir=${$(pwd)/$HOME/$container_home}

  if [[ "$1" = "." || -z "$1" ]]; then
    cmd=$current_dir
  elif [[ "$1" =~ "^$HOME" ]]; then
    cmd=${1/"$HOME"/"$container_home"}
  else
    cmd=$current_dir/$1
  fi

  docker run -it --rm \
    -v /etc/localtime:/etc/localtime \
    -v $HOME:$container_home \
    -v $HOME/.vim:$container_home/.vim \
    -v $HOME/.vimrc:$container_home/.vimrc \
    -w $current_dir \
  markhuge/vim \
  vim $cmd 
}
```
