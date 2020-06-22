# express-auth-boilerplate

Built with `typescript`, `express`, `react`, `caddy`, `docker`, `docker-compose`

## How to run

```shell
$ mkdir config
$ ./setup generate-jwt-secret
$ docker-compose up -d
```

## Architecture

- [note-server](/server): typescript, express, mongodb, dockerized
- [note-client](/client): typescript, react, dockerized
- [note-proxy](/proxy): caddy, dockerized

```
nginx -> caddy:7000 -> /api server:7001
                    -> /    client:7002
```

## [setup.sh](/setup.sh)

```shell
$ ./setup.sh
Usage: ./setup.sh <subcommands> [args]

SUBCOMMANDS:

  user:
    ./setup.sh user add <id> <password>
    ./setup.sh user update <id> <password>
    ./setup.sh user remove <id>
    ./setup.sh user list

  debug:
    ./setup.sh debug hash <text>

  etc:
    ./setup.sh generate-jwt-secret
```

### Requirements

- [openssl](https://www.openssl.org/)
- [jq](https://stedolan.github.io/jq/)
