# Ansible 

## Sample playbook for referance.
 01_hello_wolrd - Simple print hello world\
 02_install_telnet - Simple telnet package installation using `YUM` repo \
 03_install_httpd - Apache tomcat instllation and upload webpage and update the `Webpage `content.\
 04_restart_httpd - Apache tomcat enable `service`, Security Configuretion. \
 05_copy_facts -  Add page into `Webserver` node, Add User into `Test` node using `TAG` and `Handler`. \


## my ansible  host details 
  ```
# tail /etc/ansible/hosts
192.168.225.200

[master]
192.168.225.180

[webserver]
192.168.225.190

[test]
192.168.225.200

  ```



## Aurther
  Bandhala Raja S