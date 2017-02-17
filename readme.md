# keepdirchanges

This script follow directory changes since last execution.
It uses rsync program. See 3 main line inside.
For use it see script keepchanges.

### Installation

Scripts requires [rsync](https://rsync.samba.org/) to run.

Simple copy files 'keepdirchanges' and 'keepchanges' in /usr/local/bin.
execute:
```sh
$ keepchanges work
```
some time later:
```sh
$ keepchanges work
```
You have kept changes(default path /root/confkeep).
