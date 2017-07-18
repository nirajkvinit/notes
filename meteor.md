# How to install a previous version of meteor JS?
curl "https://install.meteor.com/?release=1.1.0.2" | sh

# Mongodb does not work in vagrant shared folder
move project's .meteor/local/db somewhere in the vm and make a symlink
https://lookonmyworks.co.uk/2013/06/18/running-meteor-in-a-vagrant-virtualbox/
