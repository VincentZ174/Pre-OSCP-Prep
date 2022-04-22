## Gobuster Scan Results

```
┌──(kali㉿kali)-[~]
└─$ gobuster dir --url http://10.10.170.11 -w /usr/share/wordlists/SecLists/Discovery/Web-Content/raft-small-words.txt -o gobuster -t 100
===============================================================
Gobuster v3.1.0
by OJ Reeves (@TheColonial) & Christian Mehlmauer (@firefart)
===============================================================
[+] Url:                     http://10.10.170.11
[+] Method:                  GET
[+] Threads:                 100
[+] Wordlist:                /usr/share/wordlists/SecLists/Discovery/Web-Content/raft-small-words.txt
[+] Negative Status codes:   404
[+] User Agent:              gobuster/3.1.0
[+] Timeout:                 10s
===============================================================
2022/04/20 03:00:36 Starting gobuster in directory enumeration mode
===============================================================
/images               (Status: 301) [Size: 235] [--> http://10.10.170.11/images/]
/.html                (Status: 403) [Size: 207]                                  
/cache                (Status: 301) [Size: 234] [--> http://10.10.170.11/cache/] 
/includes             (Status: 301) [Size: 237] [--> http://10.10.170.11/includes/]
/modules              (Status: 301) [Size: 236] [--> http://10.10.170.11/modules/] 
/.                    (Status: 200) [Size: 9258]                                   
/media                (Status: 301) [Size: 234] [--> http://10.10.170.11/media/]   
/plugins              (Status: 301) [Size: 236] [--> http://10.10.170.11/plugins/] 
/templates            (Status: 301) [Size: 238] [--> http://10.10.170.11/templates/]
/.htaccess            (Status: 403) [Size: 211]                                     
/language             (Status: 301) [Size: 237] [--> http://10.10.170.11/language/] 
/tmp                  (Status: 301) [Size: 232] [--> http://10.10.170.11/tmp/]      
/bin                  (Status: 301) [Size: 232] [--> http://10.10.170.11/bin/]      
/components           (Status: 301) [Size: 239] [--> http://10.10.170.11/components/]
/administrator        (Status: 301) [Size: 242] [--> http://10.10.170.11/administrator/]
/layouts              (Status: 301) [Size: 236] [--> http://10.10.170.11/layouts/]      
/.htm                 (Status: 403) [Size: 206]                                         
/libraries            (Status: 301) [Size: 238] [--> http://10.10.170.11/libraries/]    
/.htc                 (Status: 403) [Size: 206]                                         
/.html_var_DE         (Status: 403) [Size: 214]                                         
/.htpasswd            (Status: 403) [Size: 211]                                         
/.html.               (Status: 403) [Size: 208]                                         
/.html.html           (Status: 403) [Size: 212]                                         
/.htpasswds           (Status: 403) [Size: 212]                                         
/cli                  (Status: 301) [Size: 232] [--> http://10.10.170.11/cli/]          
/.htm.                (Status: 403) [Size: 207]                                         
/.htmll               (Status: 403) [Size: 208]                                         
/.html.old            (Status: 403) [Size: 211]                                         
/.ht                  (Status: 403) [Size: 205]                                         
/.html.bak            (Status: 403) [Size: 211]                                         
/.htm.htm             (Status: 403) [Size: 210]                                         
/.hta                 (Status: 403) [Size: 206]                                         
/.html1               (Status: 403) [Size: 208]                                         
/.htgroup             (Status: 403) [Size: 210]                                         
/.html.LCK            (Status: 403) [Size: 211]                                         
/.html.printable      (Status: 403) [Size: 217]                                         
/.htm.LCK             (Status: 403) [Size: 210]                                         
/.htaccess.bak        (Status: 403) [Size: 215]                                         
/.htmls               (Status: 403) [Size: 208]                                         
/.html.php            (Status: 403) [Size: 211]                                         
/.htx                 (Status: 403) [Size: 206]                                         
/.htuser              (Status: 403) [Size: 209]                                         
/.html-               (Status: 403) [Size: 208]                                         
/.htlm                (Status: 403) [Size: 207]                                         
/.htm2                (Status: 403) [Size: 207]                                         
                                                                                        
===============================================================
2022/04/20 03:01:23 Finished
===============================================================
```

* filtering out 403 responses

```
/images               (Status: 301) [Size: 235] [--> http://10.10.170.11/images/]
/cache                (Status: 301) [Size: 234] [--> http://10.10.170.11/cache/]
/includes             (Status: 301) [Size: 237] [--> http://10.10.170.11/includes/]
/modules              (Status: 301) [Size: 236] [--> http://10.10.170.11/modules/]
/.                    (Status: 200) [Size: 9258]
/media                (Status: 301) [Size: 234] [--> http://10.10.170.11/media/]
/plugins              (Status: 301) [Size: 236] [--> http://10.10.170.11/plugins/]
/templates            (Status: 301) [Size: 238] [--> http://10.10.170.11/templates/]
/language             (Status: 301) [Size: 237] [--> http://10.10.170.11/language/]
/tmp                  (Status: 301) [Size: 232] [--> http://10.10.170.11/tmp/]
/bin                  (Status: 301) [Size: 232] [--> http://10.10.170.11/bin/]
/components           (Status: 301) [Size: 239] [--> http://10.10.170.11/components/]
/administrator        (Status: 301) [Size: 242] [--> http://10.10.170.11/administrator/]
/layouts              (Status: 301) [Size: 236] [--> http://10.10.170.11/layouts/]
/libraries            (Status: 301) [Size: 238] [--> http://10.10.170.11/libraries/]
/cli                  (Status: 301) [Size: 232] [--> http://10.10.170.11/cli/]
```
