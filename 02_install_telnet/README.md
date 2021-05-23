# Ansible tutorial: Package installation

Now we're going to install basic package on listed notes.

## YUM repo

Most of ' LINUX ' pacakge installation done through YUM repo.

### Ansible modul & sample code 

This module lets you execute a shell command on the remote host:

```bash
      yum:
       name: telnet*
       state: installed
```

#### Sample Output

```bash
[root@dc-node1 02_install_telnet]# ansible-playbook 02_install_telnet.yml

PLAY [Install TELNET package from YUM Repo] **************************************************************************************************************************************

TASK [Gathering Facts] ***********************************************************************************************************************************************************
ok: [192.168.XXX.XXX]
ok: [192.168.XXX.XXX]
ok: [192.168.XXX.XXX]

TASK [Installation play] *********************************************************************************************************************************************************
ok: [192.168.XXX.XXX]
ok: [192.168.XXX.XXX]
ok: [192.168.XXX.XXX]

PLAY RECAP ***********************************************************************************************************************************************************************
192.168.XXX.XXX            : ok=2    changed=0    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
192.168.XXX.XXX            : ok=2    changed=0    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
192.168.XXX.XXX            : ok=2    changed=0    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0

```
##### Aurther
  Bandhala Raja S