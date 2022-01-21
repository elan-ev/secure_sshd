# Ansible Role to harden the sshd configuration

![molecule](https://github.com/elan-ev/secure_sshd/actions/workflows/molecule.yml/badge.svg)

This role changes a existing sshd config to accept only secure authentication methods.

## Example Playbook

Just add the role to your playbook:

```yaml
- hosts: all
  become: true
  roles:
    - role: elan.secure_sshd
```

## Development

For development and testing you can use [molecule](https://molecule.readthedocs.io/en/latest/).
With podman as driver you can install it like this – preferably in a virtual environment (if you use docker, substitute `podman` with `docker`):

```bash
pip install -r .dev_requirements.txt
```

Then you can *create* the test instances, apply the ansible config (*converge*) and *destroy* the test instances with these commands:

```bash
molecule create
molecule converge
molecule destroy
```

If you want to inspect a running test instance use `molecule login --host <instance_name>`, where you replace `<instance_name>` with the desired value.

To test the role run `molecule test`.

## License

[BSD-3-Clause](LICENSE)

## Author Information

[ELAN e.V](https://elan-ev.de/)
