#virtualenv
Use the following command to create a virtual environment ```$ virtualenv <dir_name>```
To use the virtualenv use the command ```$ source <virtualenv_dir_name>/bin/activate```
Ref -
http://python-guide-pt-br.readthedocs.io/en/latest/dev/virtualenvs/

# virtualenv workflow
Working Effectively with Python Virtual Environments (Virtualenv)
https://www.youtube.com/watch?v=8KWVEc6vFgA
Edit ~/.bash_profile to add the following aliases
alias ae='deactivate &> /dev/null; source ./venv/bin/activate'
alias de='deactivate'


use ```os.getcwd()``` to get current working directory.
use ```os.path.dirname(os.path.abspath(__file__))``` to get directory name of the current file


#loading module from files in sibling directory
Here the executing file is in another directory and is sibling of example directory. From example directory module humansize is being imported.
Ref - https://stackoverflow.com/questions/10272879/how-do-i-import-a-python-script-from-a-sibling-directory
  sys.path.append(os.path.abspath('../example'))
  import humansize

#Mutator
Mutable objects (such as lists) have some methods devoted entirely to modifying the internal state of the object.
Such methods are called mutators. Examples are the list methods insert , append , extend , and sort . Because a change of state is all that is desired, a mutator method usually returns no value of interest to the caller. Python never-theless automatically returns the special value None even when a method does not explicitly return a value.
Ref - Fundaments of Python - 5.1.6

# Create Python2 Virtualenv in a project's directory
virtualenv venv
source venv/bin/activate

# Create Python3 virtualenv in a project's directory
python3 -m venv ./venv
source ./venv/bin/activate
--------------------------------------------------------------------

run this setvirtualenvproject while the virtualenv is active and you are in the project directory
workon <project_name> will activate the environment and take you to the project
