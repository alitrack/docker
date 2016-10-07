# Firefox Docker
[Chinese tutorial](http://alitrack.com/2016/10/07/%E5%A6%82%E4%BD%95%E5%9C%A8mac-osx%E4%B8%8B%E7%9A%84docker%E9%87%8C%E8%BF%90%E8%A1%8Clinux%E6%A1%8C%E9%9D%A2%E7%A8%8B%E5%BA%8F/)


## Tutorial(How to run a Linux GUI application(Firefox) on OSX using Docker)

### Install brew

```
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

### Install and run scat

```
brew install socat
socat TCP-LISTEN:6000,reuseaddr,fork UNIX-CLIENT:\"$DISPLAY\"
```

### Install and configure XQuartz

![In X11 preferences in XQuartz, in the security tab, check both boxes](http://alitrack.com/wp-content/uploads/2016/10/Screen-Shot-2016-10-07-at-3.09.23-PM.png)

### Grab a image

```
docker pull alitrack/firefox
```

### Run it

```
docker run --rm -e DISPLAY=$DISPLAY  \
-i -t -v ${HOME}:/home/${USER} \
-v /tmp/.X11-unix:/tmp/.X11-unix \
alitrack/firefox firefox
```

### references,

* [How to run a Linux GUI application on OSX using Docker](http://kartoza.com/en/blog/how-to-run-a-linux-gui-application-on-osx-using-docker/#disqus_thread)
* [Running GUI apps with Docker](http://fabiorehm.com/blog/2014/09/11/running-gui-apps-with-docker/)

