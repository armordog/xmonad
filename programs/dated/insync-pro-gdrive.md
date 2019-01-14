# Install InSync for Google Drive

> [Reference](https://ubuntuhirek.wordpress.com/2012/11/19/install-insync-unofficial-google-docsdriver-client-on-ubuntu-via-repository/)

## Add Repo Key
```shell
wget -qO - https://d2t3ff60b2tol4.cloudfront.net/services@insynchq.com.gpg.key | sudo apt-key add -
```

## Add Repo
```shell
sudo sh -c 'echo "deb http://apt.insynchq.com/ubuntu trusty non-free" >> /etc/apt/sources.list.d/insync.list' 
```

## Install
```shell
sudo apt-get update
sudo apt-get install insync
```

## Autostart
Edit `~/.xmonad/autostart` and add the lines
```shell
# start insync
if [ -z "$(pgrep -x insync)" ] ; then
  /usr/bin/insync start
fi
```

## Misc
* Run `insync get_sync_progress` to get more detailed sync information
* Run `insync help` to list available commands
