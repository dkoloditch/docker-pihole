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
```

## Troubleshooting

### Error response from daemon: Ports are not available: exposing port TCP 0.0.0.0:53 -> 0.0.0.0:0: listen tcp 0.0.0.0:53: bind: address already in use

This is an issue related to Mac OS's `mDnsResponder`, which was introduced in
recent versions of the OS. Use the following workaround:

1. Edit ~/Library/Group\ Containers/group.com.docker/settings.json and set
  `"kernelForUDP": false`
2. Restart Docker Desktop

See [this github issue](https://github.com/docker/for-mac/issues/7008#issuecomment-17468457430)
for more details.

## Adlists

https://raw.githubusercontent.com/StevenBlack/hosts/master/hosts

https://raw.githubusercontent.com/PolishFiltersTeam/KADhosts/master/KADhosts.txt

https://raw.githubusercontent.com/FadeMind/hosts.extras/master/add.Spam/hosts

https://raw.githubusercontent.com/anudeepND/blacklist/master/adservers.txt

https://raw.githubusercontent.com/d3ward/toolz/master/src/d3host.txt