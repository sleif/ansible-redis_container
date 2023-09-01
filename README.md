# sleif.redis_container

This role runs Redis in a Podman container.

## Requirements

na

## Role Variables

- redis_container_name

## Dependencies

```sh
ansible-galaxy install sleif.podman --force
ansible-galaxy install sleif.redis_container --force
```

## Example Playbook

```yml
- name: VM app.example.com
  hosts: "app.example.com"
  user: root
  vars:
    podman_networks:
      podman_network_root:
        podman_network_name: 'podman_custom'
        podman_network_subnet: '10.0.0.0/24'
        podman_network_gateway: '10.0.0.1'
        podman_network_iprange: '10.0.0.128/25'
      podman_network_rootless:
        podman_network_name: 'podman_custom'
        podman_network_subnet: '10.0.1.0/24'
        podman_network_gateway: '10.0.1.1'
        podman_network_iprange: '10.0.1.128/25'
    podman_rootless: true
    podman_network_name: "{{ podman_networks.podman_network_rootless.podman_network_name }}"

  roles:
    - {role: sleif.podman, tags: "podman_role",
       podman_operation: "podman_install"}
    - {role: sleif.redis_container, tags: "redis_container, app",
       pod_name: "app"}
```

## License

MIT

## Author Information

Created in 2023 by Sebastian Berthold
