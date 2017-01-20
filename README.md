# Run in project

This is simple script which allows to use composer managed tools like drush, drupal console, phpunit like it would be installed globally.

For me it was very annoying to write relative path to eg. drush when i want to run some command i need to write `../vendor/bin/drush entup`.

# Installation

Copy (or git clone) two files (run_in_project and commands) into .run_in_project in your home directory.

```
mkdir ~/.run_in_project
cd .run_in_project
wget https://raw.githubusercontent.com/quexpl/run_in_project/master/run_in_project
wget https://raw.githubusercontent.com/quexpl/run_in_project/master/commands
```

And append this two lines into you shell cofiguration file (.bash_profile/.bashrc/.zshrc)

```
PATH="$HOME/.run_in_project:$PATH"
source .run_in_project/commands
```

# Configuration
This script is looking in two directories inside project root for executable commands that you want to run (bin and vendor/bin). To add new direcory, you need to edit  `directories="bin vendor/bin"` direcotires assigment in main script.

Another thing you might change is list of aliases defined in commands file. It's just list of aliases that corresponds to specified tools installed with composer inside your projects.

For example if you want to use behat you need to add following line to commands files:
```
alias behat='run_in_project behat'
```
