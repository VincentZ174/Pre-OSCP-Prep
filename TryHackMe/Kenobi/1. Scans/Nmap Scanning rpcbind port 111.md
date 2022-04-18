## Nmap Scanning rpcbind port 111

nmap -p 111 --script=nfs-ls,nfs-statfs,nfs-showmount 10.10.26.143

```
Starting Nmap 7.92 ( https://nmap.org ) at 2022-04-16 21:25 EDT
Nmap scan report for 10.10.26.143
Host is up (0.091s latency).

PORT    STATE SERVICE
111/tcp open  rpcbind
| nfs-showmount: 
|_  /var *

Nmap done: 1 IP address (1 host up) scanned in 1.08 seconds
```
