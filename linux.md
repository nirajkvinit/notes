# Convert PPK (Putty private key) to id_rsa (openssh private key)
1. Install puttygen (part of the putty package):
    `sudo apt-get install putty`
2. Convert private.ppk to id_rsa:
	`puttygen private.ppk -O private-openssh -o do_private_key_rsa`

ref: https://techtuts.info/2014/06/convert-ppk-id_rsa-linux/

# Connect to a server via ssh on ubuntu
	`ssh -i do_private_key_rsa <username>@<ip_address> -p <port_number>`

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

# Back up MySQL Database
`$ mysqldump --opt -u [uname] -p [dbname] > [backupfile.sql]`

#Restore MySQL Database
`$ mysql -u [uname] -p [db_to_restore] < [backupfile.sql]` Ref. http://webcheatsheet.com/sql/mysql_backup_restore.php

# Use swaks for test emails
swaks --to user@example.com

# Extract from multipart zip file
first, combine the split archive to a single archive: `zip -s 0 split-foo.zip --out unsplit-foo.zip`
Then, extract the single archive using unzip: `unzip unsplit-foo.zip`

