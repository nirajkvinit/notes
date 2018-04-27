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