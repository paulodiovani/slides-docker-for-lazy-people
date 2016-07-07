# Docker for Lazy People

![sleepy-whale](img/sleepy-whale.jpg)
https://www.flickr.com/photos/37060680@N04/4441496167 <!-- .element: class="credits" -->

Or how to use Docker to leverage dependency management and
reduce hard work

<small>Version 0.1.0</small>

====

<!-- .slide: class="half-slide" data-background="url(img/paulodiovani.jpg)" data-background-size="contain" data-background-repeat="no-repeat" data-background-position="right" -->

### <i class="fa fa-user"></i> Paulo Diovani Gonçalves

Tecnólogo em Sistemas para Internet pela Universidade Feevale.
Desenvolvedor na Codeminer 42.
Usuário GNU/Linux.

[blog.diovani.com][blog]

[slides.diovani.com][slides]

[@paulodiovani][twitter]

[![codeminer42][code-logo]][code-site] <!-- .element: class="no-border no-background" -->

[avatar]: img/avatar.jpg
[blog]: http://blog.diovani.com
[slides]: http://slides.diovani.com
[twitter]: http://twitter.com/paulodiovani
[code-logo]: img/codeminer42.png
[code-site]: http://codeminer42.com/

----

## Yet another talk about Docker

...not realy (or I hope so)

Note:
We have been having a lot of Docker talks recently.
Most of then a lot complicated.

====

```bash
# running a container on interactive tty
$ docker run -i -t image_name [command]

# forwarding ports
$ docker run -p 9999:9999 image_name

# mounting volumes
$ docker run -v /host/path:/guest/path image_name

# running on background
$ docker run -d image_name

# removing after use
$ docker run --rm -it image_name [command]
```

```bash
# hosting static content with NGINX
$ docker run --name some-nginx \
        -v /some/content:/usr/share/nginx/html:ro \
        -p 8080:80 \
        -d nginx
```

Note:
...Giving us a lot of sample commands hard to remember.

> Look at that huge command...

====

> ## It's the Future
>
> ![future](img/future.jpg)

Source: https://circleci.com/blog/its-the-future/

Note:
A fun post on circle-ci blog introduces Docker and containers
(and a lot more) as ~~an alternative~~ the new way for a simple
web hosting.

Thanks, Azzi.

====

### The Docker ecosystem

Docker official tools          | Third Parties
---                            | ---
Docker Engine                  | Kitematic
Docker Compose                 | Azk
Docker Hub                     | Kubernetes
Docker Cloud                   | Apache Mesos
Docker Trusted Registry        | CoreOS
Docker Universal Control Plane |
Docker Machine                 |
Docker Toolbox (old)           |

Note:
And we have so much more

====

> # So much information,
> # I can't follow you!

Note:
The gotcha is that, even with the full, amazing,
capabilities of Docker, one cannot handle all
the information and deal with advantages at once.

...And a lot speakers want to tell you all of it. :(

====

![docker-fails](img/docker-fails.jpg)
https://infoslack.com/rubyconf2015/docker/#/13 <!-- .element: class="credits" -->

Note:
In the end, people just walk away from Docker. :'(

====

## Being practical

This talk introduces Docker in a way...

- Easy to understand
- Easy to use
- Functional
- Able to solve problems
- Just works

Note:
Goal: You'll be able to start using docker today,
with little or no impact on daily work

====

Docker

# Must be easier

For me to start using it

Note:
In short, this is why

----

![Docker](img/docker-logo.png) <!-- .element: class="no-border no-background" -->

A little words about Docker and containers

Note:
But what is Docker, anyway?

I promise that this is a brief introduction.

====

### Docker

> **Docker** is an open-source project that automates the
> deployment of applications inside software containers.

Note:
Source Wikipedia

====

### Docker

> Docker containers wrap a piece of software in a complete
> filesystem that contains **everything needed** to run: code,
> runtime, system tools, system libraries – anything that
> can be installed on a server. This guarantees that the
> software **will always run the same**, regardless of its
> environment.

Note:
source https://www.docker.com/what-docker

====

### Software container

> **Operating-system-level virtualization** is a server
> virtualization method in which the kernel of an operating
> system allows the existence of multiple isolated user-space
> instances, instead of just one.

Note:
Source Wikipedia

In other words, is a virtualization technique
that does not emulates hardware.

====

Docker is **not** about virtualization, it is about *services*

Note:
The tricky (and greatest) thing about Docker is
that it's made to run services, and not a full-fledged
environment.

----

## Before we start

====

## What do we need?

- Docker Engine
  + https://docker.com
- Docker Compose
  + https://docs.docker.com/compose/
- Docker Hub
  + https://hub.docker.com/

====

### Installation

- GNU/Linux
  + https://www.docker.com/products/docker#/linux
- Mac OSX
  + https://www.docker.com/products/docker#/mac
- MS Window
  + https://www.docker.com/products/docker#/windows

====

#### Note 1: Arch Linux

```bash
$ sudo pacman -Sy docker docker-compose
```

Note:
The easiest distro to install Docker

====

#### Note 2: Mac and Windows

##### Before

- boot2docker (`until 1.7`)
- Docker Toolbox (`1.8 ~ 1.11`)
  - with Docker Machine

<p></p>
##### Now

- Docker for Mac (`since 1.12-rc3`)
  + requires Yosemite `10.10`
  + uses a `xhyve` based Hypervisor
- Docker for Windows (`since 1.12-rc3`)
  + requires Requires Window `10 64bit`
  + uses `Hyper-V`

Note:
Until version 1.11 Docker for Mac and Windows
was not as easy to use, depending on a Virtual Box
VM, environment variables and etc.

Recenty, with 1.12, Docker uses a native client
and native Hypervisors.
