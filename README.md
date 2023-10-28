# docker-pihole

PiHole using Docker. Based on [this repo](https://github.com/pi-hole/docker-pi-hole/).

## Usage

### Docker Compose

Start the container

```
docker compose up -d
```

SSH into the container

```
docker ps
docker exec -it <container id from command above> bash
```

Change the password

```
pihole -a -p
```

Admin interface is available at either of the following addresses
- [pi.hole/admin](pi.hole/admin)
- [127.0.0.1/admin](127.0.0.1/admin)
- <your machine's IP address>/admin