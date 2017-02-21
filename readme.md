# keepdirchanges

This script follow directory changes since last execution.  
It is keep ONLY changes and changed files.  
It uses [rsync](https://rsync.samba.org/) program. See three main line inside the 'keepdirchanges'.  
For use it see script 'keepchanges'.  

### Requirements

Scripts requires [rsync](https://rsync.samba.org/) to run.  
Bash only for 'getopts' function.

### Installation

Simple copy files 'keepdirchanges' and 'keepchanges' in /usr/local/bin.  

### Using

```sh
$ keepchanges work
```
some time later:
```sh
$ keepchanges work
```
You have kept changes.  
Default storage path - "/root/keepchanges".  
And default tracking paths - "/etc" "/usr/local/bin".  

### Restriction

It can't track binary files, because use 'diff' program for tracking.

### Useful advices

I use 'keepchanges work' for current tracking.  
'keepchanges login' in my '~/bashrc' for fix forgotten changes.  
'keepchanges yum' for yum's post-transaction plugin.  
  
For file 'filename' recovery you can edit filename.changes, if you want, and:
```sh
$ patch -R < filename.changes
```

### Changelog

```sh
# head /root/keepchanges/Changelog
2017-02-21 14:24:17.617377707+03:00        yum/etc
Files old/mail.rc and new/mail.rc differ
Files old/mykeeper/packages.list and new/mykeeper/packages.list differ
Files old/smartmontools/smartd.conf and new/smartmontools/smartd.conf differ
Files old/smartmontools/smartd_warning.sh and new/smartmontools/smartd_warning.sh differ
Files old/sysconfig/smartmontools and new/sysconfig/smartmontools differ
************************************************
2017-02-21 14:02:05.988866107+03:00        work/etc
Files old/fstab and new/fstab differ
Files old/lvm/archive/vg_00001-518342034.vg and new/lvm/archive/vg_00001-518342034.vg differ
```
