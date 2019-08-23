# Debian Packaging

[![made-with-Markdown](https://img.shields.io/badge/Made%20with-Markdown-1f425f.svg)](http://commonmark.org) [![Open Source Love](https://badges.frapsoft.com/os/v1/open-source.png?v=103)]() 





Footnote testing...

Bla bla <sup id="a1">[1](#f1)</sup>





#### Introduction

---------

So, what is a **package**?

> "A Debian package is a collection of files that allow 
> for applications or libraries to be distributed via the Debian package 
> management system. The aim of packaging is to allow the automation of 
> installing, upgrading, configuring, and removing computer programs for 
> Debian in a consistent manner. "
>
> --- Debian Wiki



For packaging software, it is recommended to use the Debian Sid as it contain the latest software dependencies. If you have a Debian-Sid Machine you are good to go. If not we need to setup a packaging environment. There are many virtualization softwares in Linux like,

- Docker
- LXC 
- VM (Using vagrant or manually installed)

Here, we are using Docker for preparing the environment.



#### Installing Docker

--------

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

-------------

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

------------

The docker image using here is from [FSCI](https://fsci.org.in/) repositories. We had a [new one](https://gitlab.com/fsci/resources/pipelines) build  especially for this event. Thanks to [@balasankarc](https://balasankarc.in/) for the effort.😘

For pulling the image,

```bash
  $ docker pull registry.gitlab.com/fsci/resources/debian-dev:latest
```

We need to start a container using this image.

```bash
  $ docker run --name debian-dev -it registry.gitlab.com/fsci/resources/debian-dev:latest bash
```

**For packaging some packages, we may need to run the docker in a privileged mode. Also we might need to move files from the host to container and vice-versa.** To do so,

```bash
sudo docker run --privileged=true -v "$(pwd)"/workarea:/root -w /root -it registry.gitlab.com/fsci/resources/debian-dev bash
```

While you are inside the container do update to get the latest packages.

*P.S: Default sudo password for the user developer is developer itself.*

```bash
$ sudo apt-get update && sudo apt-get dist-upgrade
```

Exit the docker container by using ``Ctrl + D`` or ``$ exit``.

To start and attach the previously made container use,

```bash
$ sudo docker start debian-dev
$ sudo docker attach debian-dev
```

For packaging workshops, pulling from upstream registry use quite some bandwidth and time. To solve this, the image can be exported as a tarball and distributed among others.

Run the following to export the image,

```bash
$ sudo docker save registry.gitlab.com/fsci/resources/debian-dev:latest > debian-dev.tar
$ gzip debian-dev.tar
```

Now we get ``debian-dev.tar.gz`` file which is ready to be distributed.

To load the image from the tarball use,

```bash
$ sudo docker load < debian-dev.tar.gz
```



#### Packaging Work-flow

--------

The packaging work flow is usually like this: 

- Step 1: Rename the upstream tarball 
- Step 2: Unpack the upstream tarball 
- Step 3: Add the Debian packaging files 
- Step 4: Build the package 
- Step 5: Install the package 

Then you can test your package on your computer. The source and binary packages can be uploaded to Debian. 



#### Installing Packaging Tools

--------

Now, after setting up our Debian-Sid, we need to install tools for helping us in packaging.

| Packaging Tool |                     man                      |
| :------------: | :------------------------------------------: |
|    gem2deb     |           For packaging ruby gems            |
|    npm2deb     |        For packaging Node.js modules         |
| dh-make-golang |          For packaging go packages           |
|    dh-make     | Generic tool; if no specific tool for a lang |

If the packaging tools are not installed,then install them by,

```bash
$ sudo apt-get install gem2deb npm2deb dh-make
```

<b id="f1">1</b> Footnote content here. [↩](#a1)

#### Use the Source, Luke!

-------------

This documentation will not be possible without the below sources.

- [Debian Prerequisites by Pirate Praveen](https://www.loomio.org/d/LTpSdMuX/debian-packaging-pre-requisites) 
- [DebianWiki](https://wiki.debian.org/Packaging)
- [Official Docker Documentation](https://docs.docker.com/)
- [Stackoverflow (Our last Hope!!)](https://stackoverflow.com)



#### License

<a rel="license" href="http://creativecommons.org/licenses/by/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by/4.0/88x31.png" /></a>

This work by <a xmlns:cc="http://creativecommons.org/ns#" href="https://github.com/abspython/" property="cc:attributionName" rel="cc:attributionURL">Abhijith Sheher</a> is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by/4.0/">Creative Commons Attribution 4.0 International License</a>.



