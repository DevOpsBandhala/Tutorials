# Ansible tutorial: Tag and Handlers 

In this playbook will explore the `tag` in ansible.\
This tag module used fro call mutiple group of inventory in same playbook.

```` bash

tail /etc/ansible/hosts
192.168.XXX.XXX

[master]
192.168.XXX.XXX

[webserver]
192.168.XXX.XXX

[test]
192.168.XXX.XXX


````

In playbook need to declare the hosts like below.

````
hosts: webserver,test

````
## Calling TAG 

when: inventory_hostname in `groups` ['webserver'] --> this condiation will call the inventory.

### Ansible modul & sample code 

````
   - name: Add html file into webserver
     command: touch /var/www/html/test_web/demo.html
     when: inventory_hostname in groups ['webserver']
     tags:
      - webserver
````

##### Aurther
  Bandhala Raja S