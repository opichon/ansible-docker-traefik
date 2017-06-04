# Ansible Role: Install common services as Docker containers

An Ansible role to install common services as Docker containers.

The list of services installed is opinionated and include the following:

* [traefik](https://github.com/containous/traefik) reverse proxy ([traefik/traefik](https://hub.docker.com/_/traefik/))
* [mailhog](https://github.com/mailhog/MailHog) mail server ([mailhog/mailhog](https://hub.docker.com/r/mailhog/mailhog/))
* [janitor](https://github.com/meltwater/docker-cleanup) docker cleanup ([meltwater/docker-cleanup](https://hub.docker.com/r/meltwater/docker-cleanup/))
* [phantomjs](http://phantomjs.org/) server ([wernight/phantomjs](https://hub.docker.com/r/wernight/phantomjs/))

## Requirements

This role requires Ansible 1.2 or higher.

## Role variables

Ansible variables are listed below with their default values.

```
traefik_docker_domain
traefik_group: root
traefik_dir: /etc/traefik
traefik_network: traefik
traefik_user: root

traefik_janitor: yes
traefik_mailhog: yes
traefik_phantomjs: yes

acme_email: "me@google.com"
acme_domains:
  - domain: mydomain.com
    sans:
      - www.mydomain.com
```

## Example playbook

```
---
- hosts: webservers
  roles:
  	- opichon.docker-services
```

## License

MIT

