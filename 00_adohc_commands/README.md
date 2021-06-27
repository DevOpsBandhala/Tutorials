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
  * Here ` test ` is the group name (Ansible Inverntory group), and it own only local host , if you have more server add the server IP under the Inventory group.

  *  Below the command is test server able to ping from ansible server.

```
# ansible test -m ping

127.0.0.1 | SUCCESS => {
    "ansible_facts": {
        "discovered_interpreter_python": "/usr/bin/python"
    },
    "changed": false,
    "ping": "pong"
}
```

 * You can run Adhoc command againest single serve too instated of group. try with below command.

 ```
# ansible 127.0.0.1 -m ping

 ```


### Run shell command in ansible

  * Adhoch command to get server's free memory information.
```
# ansible test -a "free -m"
127.0.0.1 | CHANGED | rc=0 >>
              total        used        free      shared  buff/cache   available
Mem:           3789        1135        2199          42         453        2380
Swap:          2047           0        2047
```

   * Adhoch command to get server's date information.

```
# ansible test -a "date"

192.168.225.175 | CHANGED | rc=0 >>  ( I added one more server into ansible inventory file '/etc/ansible/hosts/')
Sun Jun 27 22:31:26 IST 2021

127.0.0.1 | CHANGED | rc=0 >>
Sun Jun 27 13:01:29 EDT 2021

```

  * So now you got idea to run Linux command in ansible Adhoc .
