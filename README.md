# sleif.redis_container

This role runs Redis in a Podman container.

## Requirements

Use it on a machine setup with ansible role sleif.podman.

## Role Variables

- redis_container_name

## Dependencies

na

## Example Playbook

    - hosts: "server"
      user: root
      roles:
        - { role: sleif.redis_container, tags: "redis_container",
                                      redis_container_name: "redis_for_cusom_service" }

## License

MIT

## Author Information

Created in 2021 by Sebastian Berthold
