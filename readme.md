This script preserve directories copy in a backup store and  
it tracks changes in the directories since the last execution.  
In a special (keeping) store (different from the backup)  
this script preserve only changes.  
It uses the [rsync](https://rsync.samba.org/) program. See the 3 main lines.  

### Requirements

[rsync](https://rsync.samba.org/)  
Bourne shell.  

### Installation

Move 'keepchanges' in the /usr/local/bin/.  
Move 'keepchanges.conf' in the /etc/keepchanges/.  
Edit '/etc/keepchanges/keepchanges.conf'.  

### The default settings:

CONFIG_FILE=/etc/keepchanges/keepchanges.conf  
BACKSTORE=/var/local/keepchanges/store  
KEEPCHANGES=/var/local/keepchanges/configs  
LOGFILES=/var/local/keepchanges/logs  
TRACEABLE="/etc /usr/local/bin"  
EXCLUDEFROM=keepchanges.exclude  
RSYNC_EXE=/usr/bin/rsync  

### Using
```  
keepchanges [-cdrbl path_name] [-ei pattern] [-n|k|s] [-h] [-q] [-v]  
	-c - The config file name, default:  
	     "/etc/keepchanges/keepchanges.conf".  
	All other default setups are in the config file.  
	The command line parameters have the preferences:  
	-d - the directory for keeps changes,  
	-r - the traceable directory, can be plural in that case  
	     should be in quotes with a space as delimeter,  
	     can not have a space in the name,  
	-b - the backup storage for the copies of the traceable directories,  
	     we will be compare the current traceable directories content  
	     with this copies, saved from the previous launch,  
	-l - the log files directory,  
	-e - pattern for excluded files (see man rsync),  
	-i - pattern for included files (see man rsync)  
	     has priority above the '-e' option, for example:  
	     for keep only a 'foo' file use this options (-e '*' -i 'foo'),  
	-n - dry run, perform a trial run with no changes make,  
	-k - keep changes in the keeping store,  
	-s - sync changes in the backup store,  
	-h - help,  
	-q - quiet run, without acknowledgement query for each changed file,  
	-v - be verbose.  

```  
For example:  
```sh
$ keepchanges
```
some time later:
```sh
$ keepchanges -kq
```
You have kept changes.  

### Useful advices

I use 'keepchanges' for tracking the '/etc'.  
It more handy than 'etckeeper' because keeps only changes that I made.  

