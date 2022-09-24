Create a nat network -> PREFERENCES -> NET NAT 10.0.0.0/16

LOCALSERVER-> BRIDGE ADAPTER
BASTION -> BRIDGE,NAT  192.168.1.6, 10.0.3.15/24
CLOUD_SERVER -> NAT 10.0.2.15/16vi


GIVE THE PROPER NAMES TO THE SERVER AND GET THE IPS
LOCALSERVER -> BASTION -> CLOUD_SERVER
generate keys on master, scp-copy-id from master to bastion
COPY VIA SCP THE KEYS FROM MASTER TO BASTION

TEST THE CONECTIVITY FROM MASTER TO BASTION

COPY VIA SCP THE KEYS FROM  BASTION TO CLOUD_SERVER
eval $(ssh-agent -s)

TEST COMMAND:

cp ssh_config ~/.ssh/config
ssh target-host -> pt a testa
pt a testa ssh -t -i /home/george/.ssh/id_rsa  centos@192.168.1.6 ssh -i /home/centos/.ssh/id_rsa centos@10.0.2.15
Cum se poate rula ?



V1)

george@LOCALSERVER:~/PROXYJUMPSSH$ ANSIBLE_SSH_ARGS="-F ssh_config" ansible-playbook play.yml 










