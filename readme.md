## Installing Docker

Installation instructions for Docker can be found [here](https://docs.docker.com). For linux, the following command will suffice:

```bash
wget -qO- https://get.docker.com/ | sh
```

## Installing Docker Compose

Installation instructions for Docker Compose can be found [here](https://docs.docker.com/compose/install/). For linux, the following command will suffice:

```bash
curl -L https://github.com/docker/compose/releases/download/1.5.2/docker-compose-\`uname -s\`-\`uname -m\` > /usr/local/bin/docker-compose && chmod +x /usr/local/bin/docker-compose\`
```

## Installing Rancher

Installation instructions for Rancher can be found [here](http://docs.rancher.com/rancher/installing-rancher/installing-server/). On any machine running docker, the following command will suffice.

```bash
sudo docker run -d --restart=always -p 8080:8080 rancher/server
```
