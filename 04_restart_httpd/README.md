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

[root@dc-node1 04_restart_httpd]# ansible-playbook 04_restart_httpd.yml

PLAY [Restart apache webserver and change the configuration.] *******************************************************************************

TASK [Gathering Facts] **********************************************************************************************************************
ok: [192.168.225.190]

TASK [Change the permission in httpd.conf] **************************************************************************************************
changed: [192.168.225.190]

TASK [Enable the serive] ********************************************************************************************************************
ok: [192.168.225.190]

RUNNING HANDLER [restart httpd] *************************************************************************************************************
changed: [192.168.225.190]

PLAY RECAP **********************************************************************************************************************************
192.168.225.190            : ok=4    changed=2    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0


```
##### Aurther
  Bandhala Raja S