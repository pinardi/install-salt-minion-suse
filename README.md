**Table of Contents**

* [Installation](#installation)
* [activate] (#activated service salt)
* [edit_configuration] (#edit configuration)
* [restart service] (#restart service)
* [show list key] (#show list key)
* [authorize the listed minions] (#authorize the listed minions)
* [permit all keys with "A" option] (#permit all keys)

## install & download salt di CentOS
yum install https://repo.saltstack.com/yum/redhat/salt-repo-latest-2.el7.noarch.rpm
yum clean expire-cache
yum install salt-minion

## activated 
#start & activated service salt di CentOS

systemctl start salt-minion.service
systemctl enable salt-minion.service

## edit_configuration 
#salt minion
nano /etc/salt/minion

master: "ip of salt server"

## restart service salt master dan minion
systemctl salt-master start
systemctl enable salt-master

systemctl salt-minion start
systemctl enable salt-mionion

## show list key has been connect from minion to master
salt-key -L

# authorize the listed minions
salt-key -A

# permit all keys with "A" option
[root@dlp ~]# salt-key -A 
The following keys are going to be accepted:
Unaccepted Keys:
node01.srv.world
Proceed? [n/Y] y Key for minion node01.srv.world accepted.
[root@dlp ~]# salt-key -L 
Accepted Keys:
node01.srv.world
Denied Keys:
Unaccepted Keys:
Rejected Keys:
