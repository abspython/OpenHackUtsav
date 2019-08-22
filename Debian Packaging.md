# Debian Packaging

[![made-with-Markdown](https://img.shields.io/badge/Made%20with-Markdown-1f425f.svg)](http://commonmark.org) [![Open Source Love](https://badges.frapsoft.com/os/v1/open-source.png?v=103)]() 



For packaging software, it is recommended to use the Debian Sid as it contain the latest software dependencies. If you have a Debian-Sid Machine you are good to go. If not we need to setup a packaging environment. There are many virtualization softwares in Linux like,

- Docker
- LXC 
- VM (Using vagrant or manually installed)

Here, we are using Docker for preparing the environment.



#### Installing Docker

For **Debian** _Stretch_ and later and for **Ubuntu** _Xenial_ 16.04 (LTS) & later,



Setup the Docker Repository by ,

```bash
$ sudo apt-get update
$ sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg2 \
    software-properties-common
```

Add Docker’s official GPG key,

```bash
$ curl -fsSL https://download.docker.com/linux/debian/gpg | sudo apt-key add -
```

Verify whether you have done it right,

```bash
$ sudo apt-key fingerprint 0EBFCD88
```

Add the stable repository by,

```bash
$ sudo add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/debian \
   $(lsb_release -cs) \
   stable"
```

Update ``apt`` package index.

```bash
$ sudo apt-get update
```

Install the latest **Docker Community Engine** (Docker CE),

```bash
$ sudo apt-get install docker-ce docker-ce-cli containerd.io
```

Verify that Docker Engine - Community is installed correctly by running the `hello-world`
image.

```bash
$ sudo docker run hello-world
```

And you are ready to move to next section..



For **Arch** Linux,

```bash
sudo pacman -S docker
```

And you know what to do :)



#### Docker Prerequisites

We will learn about the basic commands of docker..

|       Docker Command        |                    man                    |
| :-------------------------: | :---------------------------------------: |
|        docker images        | Shows the images pulled/builded in docker |
|        docker ps -a         |       Shows the all the containers        |
|    docker rmi [image-id]    |          Delete the resp. image           |
|  docker pull [repository]   |     Pulls the image from a repository     |
| docker start [containerid]  |            Starts a container             |
| docker attach [containerid] |     Attach the container to terminal      |

*P.S : Default Docker may not work without sudo. For this you may need to add your user to the docker group.*



#### Installing Debian-Sid in Docker

#### Use the Source, Luke!

- [Debian Prerequisites by Pirate Praveen](https://www.loomio.org/d/LTpSdMuX/debian-packaging-pre-requisites) 
- [DebianWiki](https://wiki.debian.org/Packaging)
- [Official Docker Documentation](https://docs.docker.com/)
- [Stackoverflow (Our last Hope!!)](https://stackoverflow.com)



#### License

<a rel="license" href="http://creativecommons.org/licenses/by/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by/4.0/88x31.png" /></a>

This work by <a xmlns:cc="http://creativecommons.org/ns#" href="https://github.com/abspython/" property="cc:attributionName" rel="cc:attributionURL">Abhijith Sheher</a> is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by/4.0/">Creative Commons Attribution 4.0 International License</a>.