# Ansible role: `system_ansible`

Setup hosts to let Ansible manage them.

⚠️ **This role has been moved into the collection [jpclipffel.system](https://github.com/jpclipffel/ansible_collection.system):**
* GitHub: https://github.com/jpclipffel/ansible_collection.system
* Ansible Galaxy: https://galaxy.ansible.com/jpclipffel/system

---

## Tags

| Tag        | Description                            |
|------------|----------------------------------------|
| `setup`    | Install Ansible configuration on hosts |
| `teardown` | Remove Ansible confguration from hosts |
| `remove`   | Remove Ansible confguration from hosts |

## Variables

See `defaults/main.yml` for the full list of variables.

| Variable                         | Type           | Required | Defaut         | Description                            |
|----------------------------------|----------------|----------|----------------|----------------------------------------|
| `system_ansible_user_name`       | `string`       | No       | `ansible_user` | Ansible user account                   |
| `system_ansible_public_key_file` | `string`, path | No       | -              | Ansible account public key file (path) |
| `system_ansible_public_key`      | `string`       | No       | -              | Ansible account public key content     |

## Templates

| Template     | Description                                    |
|--------------|------------------------------------------------|
| `sudoers.j2` | Sudoers configuration for Ansible user account |

## Tasks

```text
main.yml
|
| -------------- tags: setup, teardown, remove --
|
\__ linux_<distribution>.yml
    |
    \__ services/pip.yml
    |
    \__ services/ssh.yml
    |
    \__ services/sudo.yml
```
