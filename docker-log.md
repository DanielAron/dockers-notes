https://training.docker.com/self-paced-training
https://docs.docker.com/engine/installation/mac/
https://hub.docker.com/

< http://heidloff.net/article/17.08.2015084655NHE9YE.htm

>docker images
>docker run ubuntu:14.04 echo "hello world"
>docker run ubuntu ps ax
>docker run -i -t ubuntu:14.04 /bin/bash
>docker run -it ubuntu bash
to exits: CTRL + P + Q
>ps -ef
>docker ps
>docker attach [docker id]
>docker run -d ubuntu ping 127.0.0.1 -c 100
>docker logs -f [docker id]
>docker ps -a
>docker run -d -P tomcat:7
>docker ps
ir a navegador: 0.0.0.0:port

FIN VIDEO 1
# CREATE IMAGES WITH COMMIT
>docker run -it ubuntu bash
>apt-get install emacs -y
>exit
>docker ps -a
>docker commit [docker id] daniel/emacs:1.0
>docker run -it daniel/emacs:1.0 bash
>emacs test.txt
>exit

# Test with Dockerfile
[
#Example of a comment
FROM ubuntu
RUN apt-get install emacs -y
] EOF

>docker build -t daniel/myimage:1.0 .

# Default command
# ENTRYPOINT
# Start and Stop Containers

# Getting terminal access
>docker ps
>docker exec -it [docker id] bash

# Remote dockers
>docker rm [docker id]
# Remote images
>docker rmi [image]


# Pushing Images to Docker Hub
docker push [repo:tag]

# Tagging Images
docker tag [image id] [repo:tag]


--------------------------------
Test change files on the fly
>docker run -dP jprjr/ubuntu-nginx:14.04
>docker exec -it [docker id] bash
>find . -name "*.html"
>apt-get install emacs -y


---------------------------------
>docker run -it ubuntu:14.04 bash
>>apt-get install apache2
>exit
>docker ps -a
>docker commit <containerid> ubuntu:apache2
>docker run -d -p 80:80 ubuntu:apache2 /usr/sbin/apache2ctl -D FOREGROUND

