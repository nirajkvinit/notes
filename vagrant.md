Ref. https://www.taniarascia.com/what-are-vagrant-and-virtualbox-and-how-do-i-use-them/

vagrant box add ubuntu/trusty64
vagrant init ubuntu/trusty64

vagrant up
vagrant halt
vagrant plugin install vagrant-vbguest
vagrant reload
vagrant ssh


------------------------------------------------------------
Command				Purpose
------------------------------------------------------------
vagrant box add ORG/BUILD	Add a new virtual machine
vagrant init ORG/BUILD		Initialize virtual machine
vagrant up			Start up virtual machine
vagrant reload			Restart virtual machine
vagrant halt			Shut down virtual machine
vagrant ssh			SSH into the virtual machine
