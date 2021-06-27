# Ansible Ad-Hoc commands

## Important configuration file of Ansble.

```
# tail /etc/ansible/hosts
192.168.225.200

[test]
127.0.0.1

```
## Ping command

```
#ansible test -m ping

127.0.0.1 | SUCCESS => {
    "ansible_facts": {
        "discovered_interpreter_python": "/usr/bin/python"
    },
    "changed": false,
    "ping": "pong"
}
```