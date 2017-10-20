# Mosquitto broker

## Mosquitto from alpine

### Run mosquitto broker

```sh
$ docker run --name mosquitto-broker -p 1883:1883 -it salenss/mosquitto
```
## Testing mosquitto
### RUN client mosquitto docker

In a terminal execute client1
```sh
$ docker run --name client1 -p 1884:1883 -it salenss/mosquitto /bin/sh
```

In another terminal execute client2
```sh
$ docker run --name client2 -p 1885:1883 -it salenss/mosquitto /bin/sh
```

Inside window client1
```sh
$ mosquitto_sub -h <ip-broker> -t <tag-suscribe>
```

Inside window client2
```sh
$ mosquitto_sub -h <ip-broker> -t <tag-suscribe> -m "hello-world"
```

Message publish from client2 to client1

## Notes
Check ip-broker, in a terminal window

```sh
$ docker inspect -f "{{ .NetworkSettings.IPAddress }}" mosquitto-broker
```
