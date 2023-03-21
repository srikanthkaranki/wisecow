# Cow wisdom web server

## Prerequisites

```
sudo apt install fortune-mod cowsay -y
```

## How to use?

1. Run `./wisecow.sh`
2. Point the browser to server port (default 4499)

## What to expect?
![cow wisdom](https://user-images.githubusercontent.com/9133227/225524281-e81a6673-5550-4db0-9bd0-63f9bbc7c2bc.png)

## About WiseCow Docker images

1. Created two Dockerfile to deploy wisecow application on two different os.
2. Dockerfile_ubuntu is to deploy wisecow on ubuntu os
3. Dockerfile_alpine is to deploy wisecow on alpine os 

# How to Build the docker images

1. To build ubuntu wisecow image, execute below command

command:- docker build -t wisecow:ubuntu -f Dockerfile_ubuntu .

2. To build alpine wisecow image, execute below command

command:- docker build -t wisecow:alpine -f Dockerfile_alpine .

# How To Start WiseCow Container

1. To start ubuntu wisecow container, execute below command

command:- docker run -d -p hostport:containerport --name wisecow_ubuntu wisecow:ubuntu

2. To start alpine wisecow container, execute below command

command:- docker run -d -p hostport:containerport --name wisecow_alpine wisecow:alpine

# Why do we need to create multiple docker images on different os

Creation of multiple images is completely optional. When we go with docker we have to keep few things in mind, docker image size should be smaller as much as possible.

OS like alpine is very lightweight but, It may not be suitable for all kinds of application, In this case we may have to go with the other OS options like ubuntu, centos etc.

Sometimes we may have os preference and we are not worried about the size of the image, that we can go with other os options.

Below is the size comparision between the ubuntu and alpine image and the wisecow image created with both os

|      OS      |    Size    |
|    ------    |   ------   |
|    ubuntu    |   77.8MB   |
|    alpine    |   7.05MB   |

|       App      |    OS     |   Size    |
|   ---------    | --------  | --------  |
|    wisecow     |  ubuntu   |  170MB    |
|    wisecow     |  alpine   |  52.2MB   |




   
