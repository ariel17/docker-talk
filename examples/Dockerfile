FROM ubuntu:14.10
MAINTAINER Ariel Gerardo Ríos
RUN apt-get update
RUN apt-get install -y htop
RUN apt-get install -y nginx
RUN apt-get install -y cpuburn

ADD . /code
WORKDIR /code

# ENTRYPOINT ["burnP6"]
EXPOSE 80

RUN echo "Hello world!"
RUN service nginx start
