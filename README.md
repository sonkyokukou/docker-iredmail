# iRedMail Dockerfile in CentOS 7

This repository contains a Dockerfile to build a Docker Machine for iRedMail in CentOS 7

## Base Docker Image

* [zokeber/centos](https://registry.hub.docker.com/u/zokeber/centos/)

## Usage

### Installation

1. Install [Docker](https://www.docker.com/).

2. You can download automated build from public Docker Hub Registry:

``` docker pull zokeber/iredmail:latest ```

**Another way: build from Github**

To create the docker image, clone this repository and execute the following command on the docker-iredmail folder:

`docker build -t zokeber/iredmail:latest .`

Another alternatively, you can build an image directly from Github:

`docker build -t="zokeber/iredmail:latest" github.com/zokeber/docker-iredmail`

### Create and running a container

**IMPORTANT: edit the iredmail.cfg file and change domain and password.**

**Create container:**

``` docker create --privileged -it --restart=always -p 80:80 -p 443:443 -p 25:25 -p 587:587 -p 110:110 -p 143:143 -p 993:993 -p 995:995 -h your_domain.com --name iredmail zokeber/iredmail ```

**Start container:**

``` docker start iredmail ```


**Another way to create and start a container:**

``` docker run --privileged -it --restart=always -p 80:80 -p 443:443 -p 25:25 -p 587:587 -p 110:110 -p 143:143 -p 993:993 -p 995:995 -h your_domain.com --name iredmail zokeber/iredmai ```
