# AWS New Server - module_stderr ansible shared connection to closed
Make sure that your remote machine has python installed if you get the following error while trying to connect to remote machine via ansible:
```
tallydevweb | FAILED! => {
    "changed": false, 
    "module_stderr": "Shared connection to XXX.XXX.XXX.XX closed.\r\n", 
    "module_stdout": "/bin/sh: 1: /usr/bin/python: not found\r\n", 
    "msg": "MODULE FAILURE", 
    "rc": 127
}
```
Just install python `$sudo apt install python`

## Installing LEMP on AWS EC2 instance via ansible
In order to configure your AWS EC2 Instance via ansible you need to configure your ansible hosts file to setup remote hosts (aka inventories)





### Refs.
https://deliciousbrains.com/hosting-wordpress-setup-secure-virtual-server/
https://stackoverflow.com/questions/42123317/how-to-use-a-public-keypair-pem-file-for-ansible-playbooks
https://deliciousbrains.com/automating-server-setup-ansible/

https://www.softwaretestinghelp.com/ansible-tutorial-1/
https://askubuntu.com/questions/929934/how-to-create-multiple-ssh-keys
https://www.softwaretestinghelp.com/ansible-tutorial-1/
https://stackoverflow.com/questions/42123317/how-to-use-a-public-keypair-pem-file-for-ansible-playbooks
