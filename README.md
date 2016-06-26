# DOCKER-CLIENT
A docker image which let you to talk to remote hosts. Why we need it?
Because if you have CI/CD pipelines on wercker, bitbucket or any other service, you won't have docker inside your testing container (obviously) 

## Image Contents
- **docker** cli: `docker run hello-world`
- **docker-compose**: `docker-compose up`
- **rdocker**: `rdocker root@REMOTE_HOST "docker build -t IMAGE_NAME .""`
- curl

## Usage
I created this image for helping with Continuous Integration, in the end of my other projects builds I use this image for talking to a remote docker host where I send a `Dockerfile`. Also as we know docker provides a secure connection using TLS and certificates... but we know creating certs is not a fun task

Here is my usual script which I run inside a container

```
	#Sends commands to the remote docker over SSH
	rdocker root@REMOTE_HOST "docker build -t IMAGE_NAME ."
```

Tadann! With this config we can use remote docker as we do on localhost

## LICENSE
**MIT**
