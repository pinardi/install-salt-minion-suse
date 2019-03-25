**Table of Contents**

* [Installation](#installation)
* [activate service salt](#activated)
* [edit configuration](#edit)
* [restart service salt minion](#restart)

# Installation
## install & download salt SUSE
```bash
yum install https://repo.saltstack.com/yum/redhat/salt-repo-latest-2.el7.noarch.rpm
apt-get update
apt-get install salt-minion
```
# activated
## start & activated service salt di CentOS
```bash
systemctl start salt-minion.service
systemctl enable salt-minion.service
```

# edit
## salt minion
```bash
nano /etc/salt/minion
master: "ip of salt server"
```
# restart
## restart service salt master dan minion
```bash
systemctl start salt-minion.service
systemctl enable salt-minion.service

systemctl start salt-minion.service
systemctl enable salt-minion.service
```
