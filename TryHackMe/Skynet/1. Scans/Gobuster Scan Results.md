## Gobuster Scan Results

```
root@ip-10-10-212-242:~# gobuster dir -u 10.10.113.176 -w /usr/share/wordlists/SecLists/Discovery/Web-Content/raft-small-words.txt -o gobuster -t 100
===============================================================
Gobuster v3.0.1
by OJ Reeves (@TheColonial) & Christian Mehlmauer (@_FireFart_)
===============================================================
[+] Url:            http://10.10.113.176
[+] Threads:        100
[+] Wordlist:       /usr/share/wordlists/SecLists/Discovery/Web-Content/raft-small-words.txt
[+] Status codes:   200,204,301,302,307,401,403
[+] User Agent:     gobuster/3.0.1
[+] Timeout:        10s
===============================================================
2022/04/19 21:55:51 Starting gobuster
===============================================================
/.php (Status: 403)
/.html (Status: 403)
/css (Status: 301)
/. (Status: 200)
/.htaccess (Status: 403)
/admin (Status: 301)
/js (Status: 301)
/.php3 (Status: 403)
/.phtml (Status: 403)
/.htc (Status: 403)
/.php5 (Status: 403)
/.htm (Status: 403)
/.html_var_DE (Status: 403)
/ai (Status: 301)
/.php4 (Status: 403)
/squirrelmail (Status: 301)
/server-status (Status: 403)
/config (Status: 301)
/.htpasswd (Status: 403)
/.html. (Status: 403)
/.html.html (Status: 403)
/.htpasswds (Status: 403)
/.htm. (Status: 403)
/.htmll (Status: 403)
/.phps (Status: 403)
/.html.old (Status: 403)
/.html.bak (Status: 403)
/.ht (Status: 403)
/.htm.htm (Status: 403)
/.htgroup (Status: 403)
/.html1 (Status: 403)
/.hta (Status: 403)
/.html.LCK (Status: 403)
/.html.printable (Status: 403)
/.htm.LCK (Status: 403)
/.htmls (Status: 403)
/.html.php (Status: 403)
/.htaccess.bak (Status: 403)
/.htx (Status: 403)
/.html- (Status: 403)
/.htuser (Status: 403)
/.htlm (Status: 403)
/.htm2 (Status: 403)
===============================================================
2022/04/19 21:55:57 Finished
===============================================================
```

* filter out 403 responses - `cat gobuster | grep -v 403`
```
/css (Status: 301)
/. (Status: 200)
/admin (Status: 301)
/js (Status: 301)
/ai (Status: 301)
/squirrelmail (Status: 301)
/config (Status: 301)
```

* running Gobuster against `/45kra24zxs28v3yd`

```
┌──(kali㉿kali)-[~]
└─$ gobuster dir --url http://10.10.234.119/45kra24zxs28v3yd/ -w /usr/share/wordlists/SecLists/Discovery/Web-Content/raft-small-words.txt -o gobuster -t 100
``` 

* results of scan

```
┌──(kali㉿kali)-[~]
└─$ cat gobuster              
/.php                 (Status: 403) [Size: 278]
/.html                (Status: 403) [Size: 278]
/.                    (Status: 200) [Size: 418]
/.htaccess            (Status: 403) [Size: 278]
/.php3                (Status: 403) [Size: 278]
/.phtml               (Status: 403) [Size: 278]
/administrator        (Status: 301) [Size: 339] [--> http://10.10.234.119/45kra24zxs28v3yd/administrator/]
/.htm                 (Status: 403) [Size: 278]
/.htc                 (Status: 403) [Size: 278]
/.php5                (Status: 403) [Size: 278]
/.html_var_DE         (Status: 403) [Size: 278]
/.php4                (Status: 403) [Size: 278]
/.htpasswd            (Status: 403) [Size: 278]
/.html.               (Status: 403) [Size: 278]
/.html.html           (Status: 403) [Size: 278]
/.htpasswds           (Status: 403) [Size: 278]
/.htm.                (Status: 403) [Size: 278]
/.htmll               (Status: 403) [Size: 278]
/.phps                (Status: 403) [Size: 278]
/.html.old            (Status: 403) [Size: 278]
/.ht                  (Status: 403) [Size: 278]
/.html.bak            (Status: 403) [Size: 278]
/.htm.htm             (Status: 403) [Size: 278]
/.htgroup             (Status: 403) [Size: 278]
/.html1               (Status: 403) [Size: 278]
/.hta                 (Status: 403) [Size: 278]
/.html.printable      (Status: 403) [Size: 278]
/.html.LCK            (Status: 403) [Size: 278]
/.htm.LCK             (Status: 403) [Size: 278]
/.htx                 (Status: 403) [Size: 278]
/.htmls               (Status: 403) [Size: 278]
/.html.php            (Status: 403) [Size: 278]
/.htaccess.bak        (Status: 403) [Size: 278]
/.htlm                (Status: 403) [Size: 278]
/.htm2                (Status: 403) [Size: 278]
/.htuser              (Status: 403) [Size: 278]
/.html-               (Status: 403) [Size: 278]
```

* let's filter out the 403 responses
```
┌──(kali㉿kali)-[~]
└─$ cat gobuster | grep -v 403
/.                    (Status: 200) [Size: 418]
/administrator        (Status: 301) [Size: 339] [--> http://10.10.234.119/45kra24zxs28v3yd/administrator/]
```

