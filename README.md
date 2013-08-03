# buply

## About

buply is a front end for bup (https://github.com/bup/bup) which is a backup program that uses some of the goodness from git.

See bup manpage for a complete list of features.

buply simplifies running bup with cron or on command line by:

* keeping recurring settings in config files per backup job
* managing batch operations eg. fsck & backup
* executing pre/post scripts
* precondition checking for flawless (I hope!) bup operation 


### Why buply?

I used to use duply to manage my duplicity backups.  Thus buply is an homage to duply (http://duply.net/)


## License

buply is licensed under the GNU GPL v3 or any later version.


## Getting started

buply is configured by environment variables.  buply-demo shows how to set up a simple backup.  Add more complex pre- and post-backup options to this file. 

``` sh
DEBUG=1
```
Turn on debugging.  Unset to turn off debugging.


``` sh
# The directory to back up
SRC_DIR=$HOME/Documents
# The name of the backup in the repo
BACKUP_NAME=Documents
```


``` sh
# Storage directory for the backup, becomes:
#   ${BUP_DIR_BASE} / ${BUP_DIR_GENERAL} - <datestring>
BUP_DIR_BASE=/media/nas/backups-bup
BUP_DIR_GENERAL=backup
```


``` sh
# How often do we want a new full backup?
period="month"
#period="annual"
```
This option allows for ***month*** or ***annual*** currently.


``` sh
# How often to do a fsck?
fsck_period="1 day"
export fsck_period="never"
```
This option allows for ***never*** or some period (like ***1 day***) that is recognised by the date(1) command.


## I want to contribute 
Contact me on [GitHub](https://github.com/resuscv/buply) 

