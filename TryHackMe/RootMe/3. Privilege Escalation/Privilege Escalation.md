## Privilege Escalation

* we get a pretty good hint here about finding files with suid flag set
* we can find all files with suid by doing `find / -perm /4000`
* we end up with a pretty big list but one item stands out - `/usr/bin/python`
* After a bit of googling, I find out that you can escalate privileges by running `python -c 'import os; os.execl("/bin/sh", "sh", "-p")'`
* `sh -p` allows for you to keep root privileges in shell even after python finishes executing
* After getting root we can finally get the flag
* root.txt: `THM{pr1v1l3g3_3sc4l4t10n}`