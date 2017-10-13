# Mosquitto broker

## mosquitto from alpine

### Build docker image

```sh
#docker build -t salenss/mosquitto .
```
### Run mosquitto broker on docker
```sh
#docker run --name <container-name> -p 1883:1883 -it salenss/mosquitto /bin/sh
```
## Testing mosquitto
### RUN client mosquitto docker
In a terminal window execute client1
```sh
#docker run --name <client1-name> -p 1884:1883 -it salenss/mosquitto /bin/sh
```
In another terminal window execute client2
```sh
#docker run --name <client2-name> -p 1885:1883 -it salenss/mosquitto /bin/sh
```

Inside window client1
```sh
# mosquitto_sub -h <ip-broker> -t <tag-suscribe>
```

Inside window client2
```sh
# mosquitto_sub -h <ip-broker> -t <tag-suscribe> -m "hello-world"
```

Message publish from client2 to client1
## Notes
<ip-broker> check inside a terminal window

```sh
$ docker inspect <container-name>
```
