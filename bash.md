# bash
* `ll` command is used to list content of current dir even hidden, instead of using `ls` which is an alias for `ls -alF`
* we can create new commands as follows: `$ alias ll='ls –l'`

* $ lsb_release -a 	# will tell distribution info for Ubuntu

* `>` with `echo` will overwrite the content of a file. Whereas `>>` will append to the file.
`at` command is useful to schedule a task or command at some future date/time


# How to use autoexpect to pipe a password into a command:
ref. https://stackoverflow.com/questions/4857702/how-to-provide-password-to-a-command-that-prompts-for-one-in-bash

These steps are illustrated with an Ubuntu 12.10 desktop. The exact commands for your distribution may be slightly different.

This is dangerous because you risk exposing whatever password you use to anyone who can read the autoexpect script file.

DO NOT expose your root password or power user passwords by piping them through expect like this. Root kits WILL find this in an instant and your box is owned.

EXPECT spawns a process, reads text that comes in then sends text predefined in the script file.

Make sure you have expect and autoexpect installed:
`sudo apt-get install expect`
`sudo apt-get install expect-dev`

Read up on it:
`man expect`
`man autoexpect`

Go to your home directory:
`cd /home/el`

User el cannot chown a file to root and must enter a password:
```touch testfile.txt
sudo chown root:root testfile.txt 
   [enter password to authorize the changing of the owner]
```
This is the password entry we want to automate. Restart the terminal to ensure that sudo asks us for the password again. Go to `/home/el` again and do this:
`touch myfile.txt`

```autoexpect -f my_test_expect.exp sudo chown root:root myfile.txt

    [enter password which authorizes the chown to root]

autoexpect done, file is my_test_expect.exp```

You have created `my_test_expect.exp` file. Your super secret password is stored plaintext in this file. This should make you VERY uncomfortable. Mitigate some discomfort by restricting permissions and ownership as much as possible:
```sudo chown el my_test_expect.exp     //make el the owner.
sudo chmod 700 my_test_expect.exp    //make file only readable by el.```

You see these sorts of commands at the bottom of my_test_expect.exp:
```set timeout -1
spawn sudo chown root:root myfile.txt
match_max 100000
expect -exact "\[sudo\] password for el: "
send -- "YourPasswordStoredInPlaintext\r"
expect eof```

You will need to verify that the above expect commands are appropriate. If the autoexpect script is being overly sensitive or not sensitive enough then it will hang. In this case it's acceptable because the expect is waiting for text that will always arrive.
Run the expect script as user el:
```expect my_test_expect.exp 
spawn sudo chown root:root myfile.txt
[sudo] password for el: ```
The password contained in my_test_expect.exp was piped into a chown to root by user el. To see if the password was accepted, look at myfile.txt:
```ls -l
-rw-r--r--  1 root root          0 Dec  2 14:48 myfile.txt```
It worked because it is root, and el never entered a password. If you expose your root, sudo, or power user password with this script, then acquiring root on your box will be easy. Such is the penalty for a security system that lets everybody in no questions asked.
