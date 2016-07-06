# Docker for Lazy People

![sleepy-whale](img/sleepy-whale.jpg)
https://www.flickr.com/photos/37060680@N04/4441496167 <!-- .element: class="credits" -->

Or how to use docker to leverage dependency management and 
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

> # It's too much information, 
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
