.. toctree::
   :maxdepth: 2

   index
   installation
   configure

# Installation

It is relativly easy to setup skarf with docker.

## With Docker 🐳

Install Docker: [Get Docker](https://docs.docker.com/get-docker/)

### Docker Compose

`docker-compose.yml`

```yaml
version: '3.3'
services:
    app:
        container_name: skarf
        ports:
            - '8080:80' # To expose skarf onto the host machine (remove this if you are using a reverse proxy such as traefik)
        volumes:
            - './static:/app/static' # To store data in the [website]/static/ url
            - './config:/app/config' # To store the config.yml config
        image: 'ghcr.io/woooferz/skarf:master'
```

Then run `docker-compose up` and CTRL+C to get out of it and configure it. Help: [Configure Skarf](./configure.md)

### Docker CLI (Untested) (Not Recommended)

Run this command:

```sh
docker run --name skarf -p 8080:80 -v /path/to/static:/app/static -v /path/to/config:/app/config ghcr.io/woooferz/skarf:master
```

To get out you probably need to do `docker stop skarf` from another shell and then you can configure it.  Help: [Configure Skarf](./configure.md)
