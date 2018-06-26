# Simple-Jenkins-DooD with docker-compose

This makes you able to run Jenkins in Docker and to run new Docker containers for Jenkins jobs in your docker host.
for example...
- pull docker images
- create and run docker containers
- build docker images
- push your docker image

This dockerfile is based on [jenkins/jenkins](https://hub.docker.com/r/jenkins/jenkins/) and install Docker CE with [Docker install Guild](https://docs.docker.com/engine/installation/linux/docker-ce/debian/).

## Getting Started
### 1. Pull or Build docker image
- Pull

```
$ docker pull kannach/jenkins-dood-compose
```

- Build

```
$ git clone https://github.com/kannach/Jenkins-dockercompose-DooD.git
$ cd Jenkins-dockercompose-DooD
$ docker build -t kannach/jenkins-dood-compose .
```

### 2. Create docker container and Start Jenkins

```
$ docker run -d --name jenkins -p 8080:8080  -p 127.0.0.1:50000:50000 -v /data/docker/jenkins:/var/jenkins_home:z -v /var/run/docker.sock:/var/run/docker.sock -v $(which docker):/usr/bin/docker -t kannach/jenkins-dood-compose

```

After a while, you can access http://localhost:8080

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details

## Acknowledgments

* [Using Docker-in-Docker for your CI or testing environment? Think twice. ](https://jpetazzo.github.io/2015/09/03/do-not-use-docker-in-docker-for-ci/)
