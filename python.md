#virtualenv
Use the following command to create a virtual environment ```$ virtualenv <dir_name>```
To use the virtualenv use the command ```$ source <virtualenv_dir_name>/bin/activate```
Ref -
http://python-guide-pt-br.readthedocs.io/en/latest/dev/virtualenvs/


use ```os.getcwd()``` to get current working directory.
use ```os.path.dirname(os.path.abspath(__file__))``` to get directory name of the current file

#loading module from files in sibling directory
Here the executing file is in another directory and is sibling of example directory. From example directory module humansize is being imported. Ref - https://stackoverflow.com/questions/10272879/how-do-i-import-a-python-script-from-a-sibling-directory
```sys.path.append(os.path.abspath('../example'))```
```import humansize```
