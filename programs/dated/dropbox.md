# Install Dropbox

> [Reference](www.ubuntuupdates.org/ppa/dropbox)

## Install Dependencies
```shell
sudo apt-get install libxslt1.1
```

## Add Repo Key
```shell
sudo apt-key adv --keyserver pgp.mit.edu --recv-keys 5044912E
```

## Add repo
```shell
sudo sh -c 'echo "deb http://linux.dropbox.com/ubuntu/ xenial main" >> /etc/apt/sources.list.d/dropbox.list' 
```

## Install
```shell
sudo apt-get update
sudo apt-get install dropbox
```

## Setup
```shell
/usr/bin/dropbox start -i
```
To check the status run
```shell
/usr/bin/dropbox status
```

## Autostart
Edit `~/.xmonad/autostart` and add the lines
```shell
# start dropbox
if [ -z "$(pgrep -x dropbox)" ] ; then
  /usr/bin/dropbox start
fi
```

## Misc
* Modify sync speed by using 

  ```shell
dropbox throttle unlimited unlimited
```
