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

### Verification

Check if you can establish a connection to the DNS server

```
nc -zv <your machine's IP address> 53
```

Check if you can perform a DNS query

```
host <your machine's IP address>
```

or

```
dig <your machine's IP address>
```

or

```
dig google.com @<your machine's IP address> -p 53
``
