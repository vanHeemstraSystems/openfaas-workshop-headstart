# 300 - Docker Hub (optional)

## 100 - Sign up for a Docker Hub account. 

The [Docker Hub](https://hub.docker.com/) allows you to publish your Docker images on the Internet for use on multi-node clusters or to share with the wider community. We will be using the Docker Hub to publish our functions during the workshop.

You can sign up here: [Docker Hub](https://hub.docker.com/)

Open a Terminal or Git Bash window and log into the Docker Hub using the username you signed up for above.

```$ docker login```

***Note***: Tip from community - if you get an error while trying to run this command on a Windows machine, then click on the Docker for Windows icon in the taskbar and log into Docker there instead "Sign in / Create Docker ID".

## 200 - Set your OpenFaaS prefix for new images

OpenFaaS images are stored in a Docker registry or the Docker Hub, we can set an environment variable so that your username is automatically added to new functions you create. This will save you some time over the course of the workshop.

Edit ```~/.bashrc``` or ```~/.bash_profile``` - create the file if it doesn't exist.

Now add the following - changing the URL as per the one you saw above (e.g. "wvanheemstra").

```export OPENFAAS_PREFIX="" # Populate with your Docker Hub username```
