# Ansible tutorial: Web Server installation

Now we're going to install apache web server on one of the noed

```bash
    Ansible host configuration please refer  below the artical.
    ### Development in Progress ####...
```

## Web server

Many webservers are available in Internet. But in linux most of time TomCat apache or basic apache web server are we are using now a day.  


### Repo
```bash
[root@dc-node1 ~]# ls -l /etc/yum.repos.d/ | grep epel
-rw-r--r--. 1 root root  951 Oct  2  2017 epel.repo
-rw-r--r--. 1 root root 1050 Oct  2  2017 epel-testing.repo
[root@dc-node1 ~]# cat /etc/yum.repos.d/epel.repo
[epel]
name=Extra Packages for Enterprise Linux 7 - $basearch
#baseurl=http://download.fedoraproject.org/pub/epel/7/$basearch
metalink=https://mirrors.fedoraproject.org/metalink?repo=epel-7&arch=$basearch
failovermethod=priority
enabled=1
gpgcheck=1
gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-EPEL-7

[epel-debuginfo]
name=Extra Packages for Enterprise Linux 7 - $basearch - Debug
#baseurl=http://download.fedoraproject.org/pub/epel/7/$basearch/debug
metalink=https://mirrors.fedoraproject.org/metalink?repo=epel-debug-7&arch=$basearch
failovermethod=priority
enabled=0
gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-EPEL-7
gpgcheck=1

[epel-source]
name=Extra Packages for Enterprise Linux 7 - $basearch - Source
#baseurl=http://download.fedoraproject.org/pub/epel/7/SRPMS
metalink=https://mirrors.fedoraproject.org/metalink?repo=epel-source-7&arch=$basearch
failovermethod=priority
enabled=0
gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-EPEL-7
gpgcheck=1
[root@dc-node1 ~]#
```

### Ansible modul & sample code - Install WebServer
 
This function can install httpd (appache) package on the node through YUM - repo.

```bash
   - name: Install httpd 
     yum: 
      name: httpd
      state: installed
   - name: Enable the serive
     service:
      name: httpd
      enabled: yes
```

### Ansible modul & sample code - Create virtual directory
 
This function can install httpd (appache) package on the node through YUM - repo.

```bash
     - name: create a directory
     file:
      path: /var/www/html/test_web
      state: directory
```


### Ansible modul & sample code - Copy/Download index.html file from Git
 
get_url module used to download the file from URL based area. 
Here i used mode key to change the permission of the file.

```bash
   get_url:
       url: https://github.com/DevOpsBandhala/Tutorials/blob/main/03_install_httpd/index.html
       mode: 0644
```

### Ansible modul & sample code - Edit and replace index.html

lineinfile  - module can use for change the line on the file. \
    1. ` path ` is keyword to define the path of the sourcefile.\
    2. ` regexp ` is one the keyword to find the word in the file.\
    3. ` line ` here we need to put the replace charater details.

```bash
   - name: Replacing the text in the HTML file
     lineinfile:
       path: /var/www/html/test_web/index.html
       regexp: "paragraph"
       line: "This is a {{ ansible_hostname }}"
       mode: 0644
```
#### Aurther
  Bandhala Raja S