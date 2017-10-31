# nginx-reverse-proxy

This is jwilders nginx-proxy that is setup with a network so it can be easily cloned and used with newer versions of docker.

## How to use:
Put this at the bottom of all other dev docker-compose files (the apps you want to used with this reverse proxy).  This is needed so nginx-proxy can be used across compose files.
```
networks:
  default:
    external:
      name: nginx-proxy
```

Run this on your local machine.  Needs to be run once per docker SERVER: `docker network create nginx-proxy`

## Example of this in the wild
https://github.com/oncalladvisors/octobercms-nginx-docker/blob/master/docker-compose-dev.yml