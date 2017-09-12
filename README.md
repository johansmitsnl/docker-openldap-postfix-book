# docker-email-autodiscover

[![Docker Pulls](https://img.shields.io/docker/pulls/jsmitsnl/docker-openldap-postfix-book.svg)](https://hub.docker.com/r/jsmitsnl/docker-openldap-postfix-book/) [![Docker layers](https://images.microbadger.com/badges/image/jsmitsnl/docker-openldap-postfix-book.svg)](https://microbadger.com/images/jsmitsnl/docker-openldap-postfix-book) [![Github Stars](https://img.shields.io/github/stars/johansmitsnl/docker-openldap-postfix-book.svg?label=github%20%E2%98%85)](https://github.com/johansmitsnl/docker-openldap-postfix-book/) [![Github Stars](https://img.shields.io/github/contributors/johansmitsnl/docker-openldap-postfix-book.svg)](https://github.com/johansmitsnl/docker-openldap-postfix-book/) [![Github Forks](https://img.shields.io/github/forks/johansmitsnl/docker-openldap-postfix-book.svg?label=github%20forks)](https://github.com/johansmitsnl/docker-openldap-postfix-book/)

This service is used for images that need basic ldap functionallity but with the postfix-book schema.
The image is compatible with for example the [tvial/docker-mailserver](https://hub.docker.com/r/tvial/docker-mailserver/) image.
Dockerhub autobuilds a new image when the ldap source is updated so we stay up to date when there are changes.

## Usage

#### Get the latest image

    docker pull jsmitsnl/docker-openldap-postfix-book:latest

#### Usage

```xml
version: '2.1'

# Services
services:

  ldap:
    restart: always
    image: jsmitsnl/docker-openldap-postfix-book:latest
    hostname: ldap
    domainname: domain.com
    container_name: ldap
    volumes:
      - ./data:/var/lib/ldap
      - ./slapd.d:/etc/ldap/slapd.d
    environment:
      - LDAP_ORGANISATION=company
      - LDAP_DOMAIN=domain.com
      - LDAP_ADMIN_PASSWORD=password
      - LDAP_LOG_LEVEL=-1
```
