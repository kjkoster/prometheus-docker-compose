# Monitoring Demo

This repository contains a complete Docker-compose setup for a monitoring demo,
as presented in
[How To Install Prometheus And Grafana On Docker](https://www.youtube.com/watch?v=jj38y6f6UpE)
by [David McKone](https://www.techtutorials.tv/about/). In fact, this code is
99% David's code, although I ironed out a few kinks and made the first-run
experience somewhat better.

## Prerequisite Installations

David expects Docker and Docker-compose to be installed on the demo host. Since
we started with a clean Debian 11 virtual machine, that is not the case for us.
Here is
[how to install Docker on Debian 11](https://docs.docker.com/engine/install/debian/).
We'll use the convenience script.

```shell
$ curl -fsSL https://get.docker.com -o get-docker.sh
$ sudo sh get-docker.sh
$ sudo apt-get install -y uidmap docker-compose
$ sudo groupadd docker
$ sudo usermod -aG docker $USER
$ sudo reboot
```

Then run `docker run hello-world` to verify everything works.

## Start Prometheus

You can now start the whole thing by running:

```
$ docker compose up
```

You can find the `node_exporter` on port 9100 and Prometheus will listen on port
9090.

