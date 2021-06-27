# Ansible Ad-Hoc commands

Before going to start Ansible adhoc comamnd we should learn important confiuration file of ansible.
So before going to start  work in ansible clear about the files.

### Important configuration file of Ansble.

```
# tail /etc/ansible/hosts
192.168.225.200

[test]
127.0.0.1

```
### Ping command
  * Here ` test ` is the group name (Ansible Inverntory group), and it own only local host , if you have more server add the server IP under the Inventory group.\

  *  Below the command is test server able to ping from ansible server.

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


### Run shell command in ansible

```
# ansible test -a "free -m"
127.0.0.1 | CHANGED | rc=0 >>
              total        used        free      shared  buff/cache   available
Mem:           3789        1135        2199          42         453        2380
Swap:          2047           0        2047
```