## Gobuster Scan Results

```
┌──(kali㉿kali)-[~]
└─$ gobuster dir --url http://10.10.10.68 -w /usr/share/wordlists/SecLists/Discovery/Web-Content/raft-small-words.txt -o gobuster -t 100          
===============================================================
Gobuster v3.1.0
by OJ Reeves (@TheColonial) & Christian Mehlmauer (@firefart)
===============================================================
[+] Url:                     http://10.10.10.68
[+] Method:                  GET
[+] Threads:                 100
[+] Wordlist:                /usr/share/wordlists/SecLists/Discovery/Web-Content/raft-small-words.txt
[+] Negative Status codes:   404
[+] User Agent:              gobuster/3.1.0
[+] Timeout:                 10s
===============================================================
2022/04/18 22:42:41 Starting gobuster in directory enumeration mode
===============================================================
/.html                (Status: 403) [Size: 291]
/.php                 (Status: 403) [Size: 290]
/uploads              (Status: 301) [Size: 312] [--> http://10.10.10.68/uploads/]
/php                  (Status: 301) [Size: 308] [--> http://10.10.10.68/php/]    
/dev                  (Status: 301) [Size: 308] [--> http://10.10.10.68/dev/]    
/.                    (Status: 200) [Size: 7743]                                 
/fonts                (Status: 301) [Size: 310] [--> http://10.10.10.68/fonts/]  
/.htaccess            (Status: 403) [Size: 295]                                  
/images               (Status: 301) [Size: 311] [--> http://10.10.10.68/images/] 
/.php3                (Status: 403) [Size: 291]                                  
/.phtml               (Status: 403) [Size: 292]                                  
/.htm                 (Status: 403) [Size: 290]                                  
/.htc                 (Status: 403) [Size: 290]                                  
/.php5                (Status: 403) [Size: 291]                                  
/.html_var_DE         (Status: 403) [Size: 298]                                  
/css                  (Status: 301) [Size: 308] [--> http://10.10.10.68/css/]    
/.php4                (Status: 403) [Size: 291]                                  
/js                   (Status: 301) [Size: 307] [--> http://10.10.10.68/js/]     
/server-status        (Status: 403) [Size: 299]                                  
/.htpasswd            (Status: 403) [Size: 295]                                  
/.html.               (Status: 403) [Size: 292]                                  
/.html.html           (Status: 403) [Size: 296]                                  
/.htpasswds           (Status: 403) [Size: 296]                                  
/.htm.                (Status: 403) [Size: 291]                                  
/.htmll               (Status: 403) [Size: 292]                                  
/.phps                (Status: 403) [Size: 291]                                  
/.html.old            (Status: 403) [Size: 295]                                  
/.ht                  (Status: 403) [Size: 289]                                  
/.html.bak            (Status: 403) [Size: 295]                                  
/.htm.htm             (Status: 403) [Size: 294]                                  
/.htgroup             (Status: 403) [Size: 294]                                  
/.hta                 (Status: 403) [Size: 290]                                  
/.html1               (Status: 403) [Size: 292]                                  
/.html.LCK            (Status: 403) [Size: 295]                                  
/.html.printable      (Status: 403) [Size: 301]                                  
/.htm.LCK             (Status: 403) [Size: 294]                                  
/.htaccess.bak        (Status: 403) [Size: 299]                                  
/.htmls               (Status: 403) [Size: 292]                                  
/.htx                 (Status: 403) [Size: 290]                                  
/.html.php            (Status: 403) [Size: 295]                                  
/.html-               (Status: 403) [Size: 292]                                  
/.htm2                (Status: 403) [Size: 291]                                  
/.htlm                (Status: 403) [Size: 291]                                  
/.htuser              (Status: 403) [Size: 293]                                  
                                                                                 
===============================================================
2022/04/18 22:42:51 Finished
===============================================================
```
