# Ansible tutorial: Hello World

Now we're test and print message.

## Print 

In linux command line ` echo ` commad used to print message. 

### Ansible modul & sample code 

This module lets you execute a shell command on the remote host:

```bash
    - name: Print welcome note
      debug:
        msg: "Hello welcome to Bandhala's tutorial"
```


#### Sample Output

```bash
[root@dc-node1 01_hello_wolrd]# ansible-playbook 01_hello_wolrd.yml

PLAY [First script] **************************************************************************************************************************************************************

TASK [Gathering Facts] ***********************************************************************************************************************************************************
ok: [192.168.225.200]
ok: [192.168.225.190]
ok: [192.168.225.180]

TASK [Print welcome notes] *******************************************************************************************************************************************************
ok: [192.168.225.180] => {
    "msg": "Hello Welcome to Bandhala's ansible tutorial."
}
ok: [192.168.225.190] => {
    "msg": "Hello Welcome to Bandhala's ansible tutorial."
}
ok: [192.168.225.200] => {
    "msg": "Hello Welcome to Bandhala's ansible tutorial."
}

PLAY RECAP ***********************************************************************************************************************************************************************
192.168.225.180            : ok=2    changed=0    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
192.168.225.190            : ok=2    changed=0    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
192.168.225.200            : ok=2    changed=0    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0

```

##### Aurther
  Bandhala Raja S
