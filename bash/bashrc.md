## .BASHRC
.bashrc file is a bash shell configuration file. It gets executed every time a user starts up a fresh terminal session in interactive mode on their linux system.
It contains a set of data that defines all the configurations for a terminal session. THese configurations include setting up or editing things like the environment variables, shell history, completion,command aliases among others.
We use the `find` command to search for the .bashrc in the system 

```
find / -name .bashrc
```
.bashrc file is used to set up a custom environment variables for different users. It can do virtually anything that a user is allowed to. It can also be used to set up custom commandsfor your personal use. 

## .BASH PROFILE
It is another shell script which it's seen as a config file. It is executed everytime a user logs into a system. Each user has their own .bash_profile file which stores all the configurations for the particular user. Whenever we create a new user on our system, Linux will generate a new default .bash_profile file for it. 

## PATH
This variable is responsible for telling bash where to look for programs. PATH is such an environment variable that keeps track of certain directories. The PATH variable stores where executables may be found.

When you want to see what directories are currently registered under PATH, the command `echo $PATH` is used. Each of the directories is separated by a “:” sign.

for example
```bash
echo $PATH 
/usr/local/go/bin:/home/icipe/miniconda3/bin:/home/icipe/miniconda3/condabin:/home/icipe/anaconda3/bin:/home/icipe/bin:/home/icipe/.local/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin:/home/icipe/go/bin:/home/icipe/BEASTv1.10.4/bin/:/home/icipe/BEASTv1.10.4/bin/:/home/icipe/edirect:/home/icipe/edirect
```

### Modifying PATH
#### Adding a file to PATH
One needs to modify the path by opening the .bashrc file with a text editor, then export the file you want to add, save the file then reload bash.

For example
```bash
nano ~/.bashrc
```
The output will look like this;
```
# ~/.bashrc: executed by bash(1) for non-login shells.
# see /usr/share/doc/bash/examples/startup-files (in the package bash-doc)
# for examples

# If not running interactively, don't do anything
case $- in
    *i*) ;;
      *) return;;
esac

# don't put duplicate lines or lines starting with space in the history.
# See bash(1) for more options
...
```
You export the file with the command
```
export PATH="$PATH:/<target_directory>"
```
One can then save the file and tell bash to reload it.


