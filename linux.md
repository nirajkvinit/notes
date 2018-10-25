# Bash Aliases
https://askubuntu.com/questions/582452/location-of-bash-aliases

# Find Linux Files by Name or ExtensionPermalink
Use find from the command line to locate a specific file by name or extension. The following example searches for *.err files in the /home/username/ directory and all sub-directories:

	`find /home/username/ -name "*.err"`

# Convert PPK (Putty private key) to id_rsa (openssh private key)
1. Install puttygen (part of the putty package):
    `sudo apt-get install putty`
2. Convert private.ppk to id_rsa:
	`puttygen private.ppk -O private-openssh -o do_private_key_rsa`

ref: https://techtuts.info/2014/06/convert-ppk-id_rsa-linux/

# Connect to a server via ssh on ubuntu
	`ssh -i do_private_key_rsa <username>@<ip_address> -p <port_number>`


/.bash_aliases
#Reload RC File (bashreload)
	`. ~/.bashrc` or `source ~/.bashrc`

# Extracting .tar.gz files
If your tar file is compressed using a gzip compressor, use this command to uncompress it.
	`$ tar xvzf file.tar.gz`

# compress a directory
	`tar -zcvf archive.tar.gz directory/ `

# Move all files from a directory to another directory
`mv  -v ~/Downloads/* ~/Videos/`

# Human readable total size of a directory
`du -hs /path/to/directory`

# How to create command alias in Ubuntu
Ref. https://askubuntu.com/questions/17536/how-do-i-create-a-permanent-bash-alias

# Rsync - Syncing Remote Folders with local
`$ rsync -azhvP <user>@<host>:<remote directory synced from> <local directory synced to> -e 'ssh -p <custom ssh port number>' `
example:
`$ rsync -azhvP pankaj@159.26.23.95:/home/pankaj/dump/ . -e 'ssh -p 1234'`

#Access remote database from command line
`$ mysql -u {username} -p{password} -h {remote server ip} {DB name}`

# Back up MySQL Database
`$ mysqldump --opt -u [uname] -p [dbname] > [backupfile.sql]`

#Restore MySQL Database
`$ mysql -u [uname] -p [db_to_restore] < [backupfile.sql]` Ref. http://webcheatsheet.com/sql/mysql_backup_restore.php

# Use swaks for test emails
`swaks --to user@example.com`

# Run a command in background and disown it so that it can run even when you close your terminal
`$<command_to_run> &`
`$disown`

# Extract from multipart zip file
first, combine the split archive to a single archive: `zip -s 0 split-foo.zip --out unsplit-foo.zip`
Then, extract the single archive using unzip: `unzip unsplit-foo.zip`

# Extract a rar file
1. Install unrar - `sudo apt-get install unrar`
2. Extract rar file - `unrar x -r <path>/myfile.rar`

# UFW block IP Addresses
sudo ufw deny from 91.200.12.0/24
Ref - 
	1. https://serverfault.com/questions/592061/block-range-of-ip-addresses
	2. https://scottlinux.com/2013/08/30/block-geo-region-list-of-ips-with-ufw-in-linux/
-----------------------------
# AWS CLI s3 commands



