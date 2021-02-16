sleif.redis_docker
============

This role runs redis in a Docker container.

Requirements
------------

Use it on a machine setup with ansible role sleif.docker.

Role Variables
--------------

- REDIS_CONTAINER_NAME
- DOCKER_NETWORK_NAME (can be defined in sleif.docker)

Dependencies
------------

Needs geerlingguy.docker to make sure Docker is available.
Needs sleif.docker to make sure Docker is configured as needed.

Example Playbook
----------------

    - hosts: "server"
      user: root
      vars:
        DOCKER_NETWORK_NAME: 'custom_docker_network'
      roles:
        - { role: sleif.redis_docker, tags: "redis_docker",
                                      REDIS_CONTAINER_NAME: "redis_for_cusom_service" }

License
-------

MIT

Author Information
------------------

Created in 2021 by Sebastian Berthold
