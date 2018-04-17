# How to install a previous version of meteor JS?
curl "https://install.meteor.com/?release=1.1.0.2" | sh

# Meteor : Exited with code: 1
Meteor unfortunately upgraded itself and now my projects have this exited with code 1 error. Well, information provided in the link below should help recover from the error.
https://juststartworking.com/meteor-exited-with-code-1/

# Upgrading Meteor app from 1.2 to 1.3
https://github.com/meteor/meteor/wiki/Breaking-changes-in-Meteor-1.2


# Mongodb does not work in vagrant shared directory
move project's .meteor/local/db somewhere in the vm and make a symlink
https://lookonmyworks.co.uk/2013/06/18/running-meteor-in-a-vagrant-virtualbox/

Example:
* Assuming there is a ~/dbs directory inside vm ~
* Create a directory inside ~/dbs for the project - microposts
* move the project's .meteor/local/db to ~/dbs/microposts
* link it moved directory to the project's .meteor/local/db
[Commands Example]:
	$ mkdir -p ~/dbs/microposts
	$ mv ~/Code/projects/microposts/.meteor/local/db ~/dbs/microposts/
	$ ln -s ~/dbs/microposts/db ~/Code/projects/microposts/.meteor/local/db

