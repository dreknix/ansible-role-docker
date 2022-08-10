# Ansible Role - Docker

Ansible role for docker and docker-compose (based on
[geerlingguy/ansible-role-docker](
https://github.com/geerlingguy/ansible-role-docker)).

## Install role via `roles/requirements.yml`

### Read-Only copy

Configure the role as read-only copy:

```yml
---
# Docker/Docker-Compose
- src: https://github.com/dreknix/ansible-role-docker.git
  scm: git
  version: main
  name: docker
...
```

Install the role:

```console
$ ansible-galaxy role install --force -r roles/requirements.yml
```

### Working copy

Configure the role as a working copy:

```yml
---
# Docker/Docker-Compose
- src: git@github.com:dreknix/ansible-role-docker.git
  scm: git
  version: main
  name: docker
...
```

Install the working copy:

```console
$ ansible-galaxy role install --force --keep-scm-meta -r roles/requirements.yml
```

## Configure through Ansible Variables

See [`defaults/main.yml`](
https://github.com/dreknix/ansible-role-docker/blob/main/defaults/main.yml)

## Using in a Playbook

```yaml
---
- name: Install Docker/Docker-Compose
  hosts:
    - docker
  roles:
    - role: docker
      tags:
        - docker
...
```

## License

[MIT](https://github.com/dreknix/ansible-role-docker/blob/main/LICENSE)
