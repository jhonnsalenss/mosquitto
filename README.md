# Mosquitto broker

Hello world mosquitto broker -client with docker

## Mosquitto from alpine

### Run mosquitto broker

```sh
$ docker run --name mosquitto-broker -p 1883:1883 -it salenss/mosquitto
```
## Testing mosquitto
## RUN client mosquitto docker

Open terminal execute client1 and subscribe <tag-subscribe>
```sh
$ docker run --name client1 -p 1884:1883 -it salenss/mosquitto /bin/sh
$ mosquitto_sub -h <ip-broker> -t <tag-subscribe>
```

In new terminal execute client2
```sh
$ docker run --name client2 -p 1885:1883 -it salenss/mosquitto /bin/sh
$ mosquitto_pub -h <ip-broker> -t <tag-subscribe> -m "hello-world"
```

Message publish from client2 to client1

## Example
```
$ docker run --name client1 -p 1884:1883 -it salenss/mosquitto /bin/sh
$ mosquitto_sub -h 172.0.2.0 -t message
```
Open new terminal
```
$ docker run --name client2 -p 1885:1883 -it salenss/mosquitto /bin/sh
$ mosquitto_pub -h 172.0.2.0 -t message -m "hello-world"
```
Check terminal client1

## Notes
- Get <ip-broker> with:

```sh
$ docker inspect -f "{{ .NetworkSettings.IPAddress }}" mosquitto-broker
```
- <tag-subscribe> any word
