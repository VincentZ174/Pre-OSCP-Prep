## Nmap Scan Results

```
root@ip-10-10-97-132:~# nmap 10.10.234.227 -sC -sV

Starting Nmap 7.60 ( https://nmap.org ) at 2022-04-18 18:17 BST
Nmap scan report for ip-10-10-234-227.eu-west-1.compute.internal (10.10.234.227)
Host is up (0.00079s latency).
Not shown: 998 filtered ports
PORT     STATE SERVICE VERSION
80/tcp   open  http    Microsoft HTTPAPI httpd 2.0 (SSDP/UPnP)
| http-methods: 
|_  Potentially risky methods: TRACE
| http-robots.txt: 6 disallowed entries 
| /Account/*.* /search /search.aspx /error404.aspx 
|_/archive /archive.aspx
|_http-server-header: Microsoft-IIS/8.5
|_http-title: hackpark | hackpark amusements
3389/tcp open  ssl     Microsoft SChannel TLS
| fingerprint-strings: 
|   TLSSessionReq: 
|     v\xb2
|     hackpark0
|     220417171542Z
|     221017171542Z0
|     hackpark0
|     Ews,
|     LD@`M
|     ?Xd$puQ
|     $0"0
|     \xbf
|     O-d&'
|_    "u\xd4
| ssl-cert: Subject: commonName=hackpark
| Not valid before: 2022-04-17T17:15:42
|_Not valid after:  2022-10-17T17:15:42
|_ssl-date: 2022-04-18T17:17:54+00:00; 0s from scanner time.
1 service unrecognized despite returning data. If you know the service/version, please submit the following fingerprint at https://nmap.org/cgi-bin/submit.cgi?new-service :
SF-Port3389-TCP:V=7.60%I=7%D=4/18%Time=625D9D38%P=x86_64-pc-linux-gnu%r(TL
SF:SSessionReq,33C,"\x16\x03\x03\x037\x02\0\0M\x03\x03b\]\x9d3\xf2\x8d\xde
SF:h\xeb\xd1\?r\xe2\x9a1\xaa2\x888\xd6\x15\xd4\x8c\x1b\x07<D\x88-@\x1a\xfe
SF:\x20\x8d\x01\0\0\xa2\xa8\x91\x0eu\xe2\x99%\x03\xa7\x01\xab\x93\t\x1e\xc
SF:b@\n\xac\xcc\xdf\xd2tS\xcca\xe0\x9e\0/\0\0\x05\xff\x01\0\x01\0\x0b\0\x0
SF:2\xde\0\x02\xdb\0\x02\xd80\x82\x02\xd40\x82\x01\xbc\xa0\x03\x02\x01\x02
SF:\x02\x104\x8a\xf6\xbcv\\\xb2\x8aJ\xc8A\x12\xcc\xf3p\xfc0\r\x06\t\*\x86H
SF:\x86\xf7\r\x01\x01\x05\x05\x000\x131\x110\x0f\x06\x03U\x04\x03\x13\x08h
SF:ackpark0\x1e\x17\r220417171542Z\x17\r221017171542Z0\x131\x110\x0f\x06\x
SF:03U\x04\x03\x13\x08hackpark0\x82\x01\"0\r\x06\t\*\x86H\x86\xf7\r\x01\x0
SF:1\x01\x05\0\x03\x82\x01\x0f\x000\x82\x01\n\x02\x82\x01\x01\0\xa5\x10\xb
SF:fZ@\xd9\xd7U\xc3\xae\nP\xa7\x9c\xebc\xae\xb2#\xfb\x9c9\xdeEws,\xec\xaba
SF:\x1cJ\xadzh\xb1\[\xf3\x8fD\x07\xee\xd2C\xcd\xbb\x8f\xe3\xb7\xd4F\x81\x8
SF:d\xd1\x10\x82\xa4\xad\xc6Z\x87\x8a\xe1V\xb8\xff\xa7a\xf2\xcfk\xe1=\x80q
SF:a\xab\x18&\xa4\xfb\xc9\x1b\xba\xf1!\xc0\xc7LD@`M\xd6\"\x16\x10I\xc12\xa
SF:b<\xe8c\xdf\xa4\xaa\xb4=\n\xad\xb3\x1e\x87s\xc7\?\x86N\x8fD\xa8\x1a\xd1
SF:I\xc0c\xa8\x9d\x17\x1cR\xe0\xad}\xd3G\xda\xf3\xc9\+\xa6OI\x18\x9c\x99\x
SF:efPd\x17\xd1\xa2\xb0\xcb\)\xf9\xccvB\xf0\x06\n8\xafo\x99\xc5\x9e\x997Q\
SF:x90\xf6vY\x08\xa0I\xe4u\0\xb3<\t\xc4F\xed\x8f\x917\xe0b\x0f:\x8d\x8b7\x
SF:be\xe3Q\xd0Mm\xec\x08R\xf7\xd1\x12mD\x10V\xb3\[\xfc\xfa9\x91\?Xd\$puQ\x
SF:ca\xcb\xfar\xa1\xf8\x03t1\xb2\xb9\]\x95!\xd0BO\x06H\ta\xb0\xef\x1b\xe3\
SF:xe3\xa7z\x89\x02\x03\x01\0\x01\xa3\$0\"0\x13\x06\x03U\x1d%\x04\x0c0\n\x
SF:06\x08\+\x06\x01\x05\x05\x07\x03\x010\x0b\x06\x03U\x1d\x0f\x04\x04\x03\
SF:x02\x0400\r\x06\t\*\x86H\x86\xf7\r\x01\x01\x05\x05\0\x03\x82\x01\x01\0_
SF:\xe0\x95o\x89\xb8\xb7\x17\\\xbf\xf3X\x93X\xe1\x14\xdah\"\xd4\xeeKUs\xd8
SF:\x90:p\xacK\x88\x128\xcax\x04\xa5\xe0\x155=\xa4\xfb\x90\xf5\xab\x897\x9
SF:aV\xc2a\xae\x8f!\x17\x20\xedU\x02\xa3L\x97\x9c\xf2\xc8\x16\xe4cQ\xb28\x
SF:80\x8f6\x1aG\x1a\xb5\x05%\x04\xef\(\x1e;\x13\xe9\xcd\xd5i\xad\^o\xb6\xa
SF:2Lk\xd7\xbdh\xb8\xde\xa2\x03\xe8\xd3\x9c\x12\x1b\x9d\x03O-d&'\xc34\xa4u
SF:\x87\x80\x99\xa7\)W9\xc5\x96\xae\x98\xcbu\x99\xf3\xe9\xf10\xad\xe28\xd5
SF:\x93\r\?\xa6;\\R\xae\xb9\$\]\x99\xd9\x1c\x11>s\x96\xd0\xe3&\x7f\xed\x83
SF:\xa78\xfc\xdff<l\x10\x8c\x8cH\x95\x8cjvs\xb9\x20\x963\x0ba\x08\)\rv\xd2
SF:\]\xf7N\x9a\xc4\x01\xd1\xeb\[Eo\x90\x87\x95\xae\x9a\xdf\[\x98\x86h\x86\
SF:x15\xe6\x98\xdake\x93\xfb\xa1\xc4\xcc\"u\\\xd4\xd29\xdf\xe5\x87=\xf3\xc
SF:b6\x04\xb6\x13m\xbb\xd5\xb5\x9fe\xe2\x05M\xd5\xd8Y\x1e\x0e\0\0\0");
MAC Address: 02:97:62:F8:3C:29 (Unknown)
Service Info: OS: Windows; CPE: cpe:/o:microsoft:windows

Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 41.44 seconds
```
