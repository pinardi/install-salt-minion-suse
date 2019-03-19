#login sebagai root
su

##install & download salt di CentOS
yum install https://repo.saltstack.com/yum/redhat/salt-repo-latest-2.el7.noarch.rpm
yum clean expire-cache
yum install salt-minion

##start & activated service salt di CentOS
systemctl start salt-minion.service
systemctl enable salt-minion.service

##edit configuration salt minion dengan mengisi ip master
nano /etc/salt/minion

master: "ip of salt server"

##restart servicew salt master dan minion
systemctl salt-master start
systemctl enable salt-master

systemctl salt-minion start
systemctl enable salt-mionion

##show list key has been connect from minion to master
salt-key -L

#authorize the listed minions - app1
salt-key -A

#permit all keys with "A" option
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
#verify working
[root@dlp ~]# salt "*" test.ping 
node01.srv.world:
    True
