**Table of Contents**

* [Installation](#installation)
* [activate service salt](#activated)
* [edit configuration](#edit)
* [restart service salt master dan minion](#restart)
* [show key](#show)
* [authorize the listed minions](#authorize the listed minions)
* [permit all keys with "A" option](#permit all keys)

# Installation
## install & download salt di CentOS
```bash
yum install https://repo.saltstack.com/yum/redhat/salt-repo-latest-2.el7.noarch.rpm
yum clean expire-cache
yum install salt-minion
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
systemctl salt-master start
systemctl enable salt-master

systemctl salt-minion start
systemctl enable salt-mionion
```

## show list key has been connect from minion to master
```bash
salt-key -L
```

## authorize the listed minions
```bash
salt-key -A
```
## permit all keys with "A" option

```bash
salt-key -A 
The following keys are going to be accepted:
Unaccepted Keys:
node01.srv.world
Proceed? [n/Y] y Key for minion node01.srv.world accepted.

salt-key -L 
Accepted Keys:
node01.srv.world
Denied Keys:
Unaccepted Keys:
Rejected Keys:
```
