## Gobuster Scan Results

```
┌──(kali㉿kali)-[~]
└─$ gobuster dir --url http://10.10.10.56 -w /usr/share/wordlists/SecLists/Discovery/Web-Content/raft-small-words.txt -o gobuster -t 100
===============================================================
Gobuster v3.1.0
by OJ Reeves (@TheColonial) & Christian Mehlmauer (@firefart)
===============================================================
[+] Url:                     http://10.10.10.56
[+] Method:                  GET
[+] Threads:                 100
[+] Wordlist:                /usr/share/wordlists/SecLists/Discovery/Web-Content/raft-small-words.txt
[+] Negative Status codes:   404
[+] User Agent:              gobuster/3.1.0
[+] Timeout:                 10s
===============================================================
2022/04/18 12:04:53 Starting gobuster in directory enumeration mode
===============================================================
/.html                (Status: 403) [Size: 291]
/.htm                 (Status: 403) [Size: 290]
/.                    (Status: 200) [Size: 137]
/.htaccess            (Status: 403) [Size: 295]
/.htc                 (Status: 403) [Size: 290]
/.html_var_DE         (Status: 403) [Size: 298]
/server-status        (Status: 403) [Size: 299]
/.htpasswd            (Status: 403) [Size: 295]
/.html.               (Status: 403) [Size: 292]
/.html.html           (Status: 403) [Size: 296]
/.htpasswds           (Status: 403) [Size: 296]
/.htm.                (Status: 403) [Size: 291]
/.htmll               (Status: 403) [Size: 292]
/.html.old            (Status: 403) [Size: 295]
/.html.bak            (Status: 403) [Size: 295]
/.ht                  (Status: 403) [Size: 289]
/.htm.htm             (Status: 403) [Size: 294]
/.html1               (Status: 403) [Size: 292]
/.htgroup             (Status: 403) [Size: 294]
/.hta                 (Status: 403) [Size: 290]
/.html.printable      (Status: 403) [Size: 301]
/.html.LCK            (Status: 403) [Size: 295]
/.htm.LCK             (Status: 403) [Size: 294]
/.htmls               (Status: 403) [Size: 292]
/.htaccess.bak        (Status: 403) [Size: 299]
/.html.php            (Status: 403) [Size: 295]
/.htx                 (Status: 403) [Size: 290]
/.htuser              (Status: 403) [Size: 293]
/.htlm                (Status: 403) [Size: 291]
/.html-               (Status: 403) [Size: 292]
/.htm2                (Status: 403) [Size: 291]
                                               
===============================================================
2022/04/18 12:04:59 Finished
===============================================================
```

## Apache Config for DirectorySlash

* by default, apache will append a `/` after a directory if the user enters a url without one
* some boxes will have this turned off by default and therefore some directories may return a 404 error
* we can force gobuster to add a `/` to the end of each directory using the `-f` flag

```
┌──(kali㉿kali)-[~]
└─$ gobuster dir --url http://10.10.10.56/ -w /usr/share/wordlists/SecLists/Discovery/Web-Content/raft-small-words.txt -o gobuster -t 100 -f    
===============================================================
Gobuster v3.1.0
by OJ Reeves (@TheColonial) & Christian Mehlmauer (@firefart)
===============================================================
[+] Url:                     http://10.10.10.56/
[+] Method:                  GET
[+] Threads:                 100
[+] Wordlist:                /usr/share/wordlists/SecLists/Discovery/Web-Content/raft-small-words.txt
[+] Negative Status codes:   404
[+] User Agent:              gobuster/3.1.0
[+] Add Slash:               true
[+] Timeout:                 10s
===============================================================
2022/04/18 12:42:47 Starting gobuster in directory enumeration mode
===============================================================
/cgi-bin/             (Status: 403) [Size: 294]
/.html/               (Status: 403) [Size: 292]
/.htm/                (Status: 403) [Size: 291]
/./                   (Status: 200) [Size: 137]
/icons/               (Status: 403) [Size: 292]
/.htaccess/           (Status: 403) [Size: 296]
/.htc/                (Status: 403) [Size: 291]
/.html_var_DE/        (Status: 403) [Size: 299]
/server-status/       (Status: 403) [Size: 300]
/.htpasswd/           (Status: 403) [Size: 296]
/.html./              (Status: 403) [Size: 293]
/.html.html/          (Status: 403) [Size: 297]
/.htpasswds/          (Status: 403) [Size: 297]
/.htm./               (Status: 403) [Size: 292]
/.htmll/              (Status: 403) [Size: 293]
/.html.old/           (Status: 403) [Size: 296]
/.html.bak/           (Status: 403) [Size: 296]
/.ht/                 (Status: 403) [Size: 290]
/.htm.htm/            (Status: 403) [Size: 295]
/.hta/                (Status: 403) [Size: 291]
/.html1/              (Status: 403) [Size: 293]
/.htgroup/            (Status: 403) [Size: 295]
/.html.printable/     (Status: 403) [Size: 302]
/.html.LCK/           (Status: 403) [Size: 296]
/.htm.LCK/            (Status: 403) [Size: 295]
/.htx/                (Status: 403) [Size: 291]
/.html.php/           (Status: 403) [Size: 296]
/.htmls/              (Status: 403) [Size: 293]
/.htaccess.bak/       (Status: 403) [Size: 300]
/.html-/              (Status: 403) [Size: 293]
/.htuser/             (Status: 403) [Size: 294]
/.htm2/               (Status: 403) [Size: 292]
/.htlm/               (Status: 403) [Size: 292]
                                               
===============================================================
2022/04/18 12:42:54 Finished
===============================================================
```

## Looking for files under /cgi-bin/

```
┌──(kali㉿kali)-[~/Downloads]
└─$ gobuster dir --url http://10.10.10.56/cgi-bin/ -w /usr/share/wordlists/SecLists/Discovery/Web-Content/raft-small-words.txt -o gobuster -t 100 -x sh, pl
===============================================================
Gobuster v3.1.0
by OJ Reeves (@TheColonial) & Christian Mehlmauer (@firefart)
===============================================================
[+] Url:                     http://10.10.10.56/cgi-bin/
[+] Method:                  GET
[+] Threads:                 100
[+] Wordlist:                /usr/share/wordlists/SecLists/Discovery/Web-Content/raft-small-words.txt
[+] Negative Status codes:   404
[+] User Agent:              gobuster/3.1.0
[+] Extensions:              sh,
[+] Timeout:                 10s
===============================================================
2022/04/18 12:49:51 Starting gobuster in directory enumeration mode
===============================================================
/.html                (Status: 403) [Size: 299]
/.htm.sh              (Status: 403) [Size: 301]
/.htm                 (Status: 403) [Size: 298]
/.html.sh             (Status: 403) [Size: 302]
/.htm.                (Status: 403) [Size: 299]
/.html.               (Status: 403) [Size: 300]
/user.sh              (Status: 200) [Size: 118]
/..                   (Status: 200) [Size: 137]
/.                    (Status: 403) [Size: 294]
/.htaccess            (Status: 403) [Size: 303]
/.htaccess.           (Status: 403) [Size: 304]
/.htaccess.sh         (Status: 403) [Size: 306]
/.htc                 (Status: 403) [Size: 298]
/.htc.sh              (Status: 403) [Size: 301]
/.htc.                (Status: 403) [Size: 299]
/.html_var_DE.sh      (Status: 403) [Size: 309]
/.html_var_DE.        (Status: 403) [Size: 307]
/.html_var_DE         (Status: 403) [Size: 306]
/.htpasswd            (Status: 403) [Size: 303]
/.htpasswd.sh         (Status: 403) [Size: 306]
/.htpasswd.           (Status: 403) [Size: 304]
/.html..sh            (Status: 403) [Size: 303]
/.html..              (Status: 403) [Size: 301]
/.html.               (Status: 403) [Size: 300]
/.html.html           (Status: 403) [Size: 304]
/.html.html.sh        (Status: 403) [Size: 307]
/.html.html.          (Status: 403) [Size: 305]
/.htpasswds           (Status: 403) [Size: 304]
/.htpasswds.sh        (Status: 403) [Size: 307]
/.htpasswds.          (Status: 403) [Size: 305]
/.htm..               (Status: 403) [Size: 300]
/.htm.                (Status: 403) [Size: 299]
/.htm..sh             (Status: 403) [Size: 302]
/.htmll               (Status: 403) [Size: 300]
/.htmll.sh            (Status: 403) [Size: 303]
/.htmll.              (Status: 403) [Size: 301]
/.html.old            (Status: 403) [Size: 303]
/.html.old.           (Status: 403) [Size: 304]
/.html.old.sh         (Status: 403) [Size: 306]
/.ht.                 (Status: 403) [Size: 298]
/.html.bak            (Status: 403) [Size: 303]
/.html.bak.sh         (Status: 403) [Size: 306]
/.ht                  (Status: 403) [Size: 297]
/.html.bak.           (Status: 403) [Size: 304]
/.ht.sh               (Status: 403) [Size: 300]
/.htm.htm.sh          (Status: 403) [Size: 305]
/.htm.htm.            (Status: 403) [Size: 303]
/.htm.htm             (Status: 403) [Size: 302]
/.htgroup.sh          (Status: 403) [Size: 305]
/.hta                 (Status: 403) [Size: 298]
/.html1               (Status: 403) [Size: 300]
/.htgroup.            (Status: 403) [Size: 303]
/.hta.sh              (Status: 403) [Size: 301]
/.html1.sh            (Status: 403) [Size: 303]
/.htgroup             (Status: 403) [Size: 302]
/.hta.                (Status: 403) [Size: 299]
/.html1.              (Status: 403) [Size: 301]
/.html.LCK            (Status: 403) [Size: 303]
/.html.printable.     (Status: 403) [Size: 310]
/.html.printable      (Status: 403) [Size: 309]
/.html.LCK.sh         (Status: 403) [Size: 306]
/.html.printable.sh   (Status: 403) [Size: 312]
/.html.LCK.           (Status: 403) [Size: 304]
/.htm.LCK             (Status: 403) [Size: 302]
/.htm.LCK.sh          (Status: 403) [Size: 305]
/.htm.LCK.            (Status: 403) [Size: 303]
/.htaccess.bak        (Status: 403) [Size: 307]
/.html.php            (Status: 403) [Size: 303]
/.htmls               (Status: 403) [Size: 300]
/.htx.sh              (Status: 403) [Size: 301]
/.htmls.sh            (Status: 403) [Size: 303]
/.htaccess.bak.sh     (Status: 403) [Size: 310]
/.html.php.sh         (Status: 403) [Size: 306]
/.htx.                (Status: 403) [Size: 299]
/.htmls.              (Status: 403) [Size: 301]
/.htaccess.bak.       (Status: 403) [Size: 308]
/.html.php.           (Status: 403) [Size: 304]
/.htx                 (Status: 403) [Size: 298]
/.htuser              (Status: 403) [Size: 301]
/.html-               (Status: 403) [Size: 300]
/.htm2                (Status: 403) [Size: 299]
/.htlm                (Status: 403) [Size: 299]
/.htuser.sh           (Status: 403) [Size: 304]
/.htm2.sh             (Status: 403) [Size: 302]
/.htlm.sh             (Status: 403) [Size: 302]
/.html-.sh            (Status: 403) [Size: 303]
/.htuser.             (Status: 403) [Size: 302]
/.htm2.               (Status: 403) [Size: 300]
/.html-.              (Status: 403) [Size: 301]
/.htlm.               (Status: 403) [Size: 300]
                                               
===============================================================
2022/04/18 12:50:13 Finished
===============================================================
```

