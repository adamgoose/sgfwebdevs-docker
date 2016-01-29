# [fit] Try to Contain Yourselves
## Adam Engebretson
### @artisangoose
### github.com/adamgoose

![](https://www.docker.com/sites/default/files/island_1.png)

---

![fit left](https://www.docker.com/sites/default/files/what-is-docker-diagram.png)

# Virtual Machines

Each virtual machine includes the application, the necessary binaries and libraries and an entire guest operating system - all of which may be tens of GBs in size.

---

![fit right](https://www.docker.com/sites/default/files/what-is-vm-diagram.png)

# Containers

Containers include the application and all of its dependencies, but share the kernel with other containers. They run as an isolated process in userspace on the host operating system. They’re also not tied to any specific infrastructure – Docker containers run on any computer, on any infrastructure and in any cloud.

---

# The Dockerfile

```Dockerfile
FROM ubuntu:14.04
MAINTAINER Adam Engebretson <adam.engebretson@bridgeconx.com>

RUN apt-get upgrade && apt-get update

# Install your application here

EXPOSE 80
VOLUME /var/www
```

---

# Running a Container

```bash
sudo docker run --detach \
    --hostname gitlab.example.com \
    --publish 443:443 --publish 80:80 --publish 22:22 \
    --name gitlab \
    --restart always \
    --volume /srv/gitlab/config:/etc/gitlab \
    --volume /srv/gitlab/logs:/var/log/gitlab \
    --volume /srv/gitlab/data:/var/opt/gitlab \
    gitlab/gitlab-ce:latest
```

---

# [fit] ANNOYING, AMIRITE!?

---

# Using `docker-compose`

```xml
gitlab:
  hostname: gitlab.example.com
  ports:
	  - "443:443"
    - "80:80"
    - "22:22"
  restart: always
  volumes:
    - "/srv/gitlab/config:/etc/gitlab"
    - "/srv/gitlab/logs:/var/log/gitlab"
    - "/srv/gitlab/data:/var/opt/gitlab"
  image: gitlab/gitlab-ce:latest
```

`docker-compose start`

---

![](http://rancher.com/wp-content/uploads/2015/06/3up.png)

# [fit] Room for Improvement?
## Enter Rancher

---

# Rancher

## Launch Your Private Container Service

### Rancher makes it simple to deliver the power of Docker to everyone in your organization.

---

![left filtered](http://rancher.com/wp-content/uploads/2015/06/infrastructure_ss.png)

## Infrastructure Services

- Resource Management
- Container Networking
- Service Discovery
- Container Load Balancing
- Health Checks & Recovery
- Upgrade
- Store Management