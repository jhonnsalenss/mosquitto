 #docker build -t salenss/mosquitto .
 #docker run --name client1 -p 1883:1883 -it salenss/mosquitto /bin/sh
 # Example
 # mosquitto_sub -h 172.17.0.3 -t hello
 # mosquitto_pub -h 172.17.0.3 -t hello -m "client1"



FROM alpine:latest

MAINTAINER Jhonn Salenss <jhonnsalenss@gmail.com>

RUN apk add --no-cache mosquitto
RUN apk add --no-cache mosquitto-clients
