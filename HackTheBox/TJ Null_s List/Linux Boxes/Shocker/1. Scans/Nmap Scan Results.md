## Nmap Scan Results

## TCP

```
Starting Nmap 7.92 ( https://nmap.org ) at 2022-04-18 11:58 EDT
Nmap scan report for 10.10.10.56
Host is up (0.028s latency).
Not shown: 998 closed tcp ports (reset)
PORT     STATE SERVICE VERSION
80/tcp   open  http    Apache httpd 2.4.18 ((Ubuntu))
|_http-title: Site doesn't have a title (text/html).
|_http-server-header: Apache/2.4.18 (Ubuntu)
2222/tcp open  ssh     OpenSSH 7.2p2 Ubuntu 4ubuntu2.2 (Ubuntu Linux; protocol 2.0)
| ssh-hostkey: 
|   2048 c4:f8:ad:e8:f8:04:77:de:cf:15:0d:63:0a:18:7e:49 (RSA)
|   256 22:8f:b1:97:bf:0f:17:08:fc:7e:2c:8f:e9:77:3a:48 (ECDSA)
|_  256 e6:ac:27:a3:b5:a9:f1:12:3c:34:a5:5d:5b:eb:3d:e9 (ED25519)
No exact OS matches for host (If you know what OS is running on it, see https://nmap.org/submit/ ).
TCP/IP fingerprint:
OS:SCAN(V=7.92%E=4%D=4/18%OT=80%CT=1%CU=36445%PV=Y%DS=2%DC=I%G=Y%TM=625D8AA
OS:F%P=x86_64-pc-linux-gnu)SEQ(SP=103%GCD=1%ISR=10C%TI=Z%CI=I%II=I%TS=8)OPS
OS:(O1=M54BST11NW6%O2=M54BST11NW6%O3=M54BNNT11NW6%O4=M54BST11NW6%O5=M54BST1
OS:1NW6%O6=M54BST11)WIN(W1=7120%W2=7120%W3=7120%W4=7120%W5=7120%W6=7120)ECN
OS:(R=Y%DF=Y%T=40%W=7210%O=M54BNNSNW6%CC=Y%Q=)T1(R=Y%DF=Y%T=40%S=O%A=S+%F=A
OS:S%RD=0%Q=)T2(R=N)T3(R=N)T4(R=Y%DF=Y%T=40%W=0%S=A%A=Z%F=R%O=%RD=0%Q=)T5(R
OS:=Y%DF=Y%T=40%W=0%S=Z%A=S+%F=AR%O=%RD=0%Q=)T6(R=Y%DF=Y%T=40%W=0%S=A%A=Z%F
OS:=R%O=%RD=0%Q=)T7(R=Y%DF=Y%T=40%W=0%S=Z%A=S+%F=AR%O=%RD=0%Q=)U1(R=Y%DF=N%
OS:T=40%IPL=164%UN=0%RIPL=G%RID=G%RIPCK=G%RUCK=G%RUD=G)IE(R=Y%DFI=N%T=40%CD
OS:=S)

Network Distance: 2 hops
Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel

OS and Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 22.91 seconds
```

## UDP 

```
Starting Nmap 7.92 ( https://nmap.org ) at 2022-04-18 12:28 EDT
Stats: 0:00:00 elapsed; 0 hosts completed (1 up), 1 undergoing UDP Scan
UDP Scan Timing: About 81.20% done; ETC: 12:28 (0:00:00 remaining)
Nmap scan report for 10.10.10.56
Host is up (0.012s latency).
Not shown: 993 open|filtered udp ports (no-response)
PORT      STATE  SERVICE
1886/udp  closed leoip
5000/udp  closed upnp
18888/udp closed apc-necmp
22341/udp closed unknown
28369/udp closed unknown
30656/udp closed unknown
43195/udp closed unknown

Nmap done: 1 IP address (1 host up) scanned in 1.81 seconds
```
                                                                    