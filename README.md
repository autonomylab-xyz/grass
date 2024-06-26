# Grass
An unofficial Docker Image for [getgrass.io](https://app.getgrass.io/register/?referralCode=33pl75DeDNvyWsA)
Available on [Docker Hub](https://hub.docker.com/r/autonomylabxyz/grass)

New to Docker? [Docker setup instructions](https://docs.docker.com/get-docker/)

## What's Grass?
Grass allows you to earn passive income by sharing your network bandwidth

## How to get started?
1. Register a Grass Account if you don't have one already: [getgrass.io](https://app.getgrass.io/register/?referralCode=33pl75DeDNvyWsA)
2. Create container using one of the options below, replacing the GRASS_USER and GRASS_PASS with your credentials
3. You're good to go! Once started, the docker exposes your current network status and lifetime earnings on port 80


### Docker Run command
```
docker run -d \
    --name Grass \
    -p 8080:80 \
    -e GRASS_USER=myuser@mail.com \
    -e GRASS_PASS=mypass \
    -e ALLOW_DEBUG=False \
    autonomylabxyz/grass:latest
```

Please replace 8080 with the port you want to be able to access the status with, as well as GRASS_USER and GRASS_PASS

### Docker Compose
```
version: "3.0"

services:
  grass:
    image: autonomylabxyz/grass:latest
    container_name: Grass
    ports:
      - 8080:80
    environment:
      - GRASS_USER=myuser@mail.com
      - GRASS_PASS=mypass
      - ALLOW_DEBUG=False
    restart: unless-stopped
```

> For arm devices change :latest to :arm64v8

```
docker-compose up -d
```



### Build local image & run

> For arm devices update the Dockerfile from alpine:3.19
to arm64v8/alpine:3.19 before building

```
docker build -t grass .
```
```
docker run -d \
    --name Grass \
    -p 8080:80 \
    -e GRASS_USER=myuser@mail.com \
    -e GRASS_PASS=mypass \
    -e ALLOW_DEBUG=False \
    grass
```




Please replace 8080 with the port you want to be able to access the status with, as well as GRASS_USER and GRASS_PASS


## License
This program is free software: you can redistribute it and/or modify it under the terms of the GNU General Public License as published by the Free Software Foundation, either version 3 of the License, or (at your option) any later version.

This program is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU General Public License for more details.


