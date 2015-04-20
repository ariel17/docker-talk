FROM ubuntu:14.10
MAINTAINER Ariel Gerardo Ríos
RUN apt-get update
RUN apt-get install -y htop

ADD . /code
WORKDIR /code

EXPOSE 80

RUN echo "Hello world!"
