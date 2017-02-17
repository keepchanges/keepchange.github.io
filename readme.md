# keepdirchanges

This script follow directory changes since last execution. It is keep ONLY changes and changed files.
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
Default storage path - "/root/confkeep".
And default tracking paths - "/etc" "/usr/local/bin".

### Restriction

It can't track binary files, because use 'diff' program for tracking.

### Useful advice

I use 'keepchanges work' for current tracking.
'keepchanges login' in my '~/bashrc' for fix forgotten changes.
'keepchanges yum' for yum's post-transaction plugin.
