## Inspecting SMB Shares with smbclient

* Connecting to the machine's network share: `smbclient //10.10.26.143/anonymous`
* list the shares using `ls`
```
Enter WORKGROUP\kali's password: 
Try "help" to get a list of possible commands.
smb: \> ls
  .                                   D        0  Wed Sep  4 06:49:09 2019
  ..                                  D        0  Wed Sep  4 06:56:07 2019
  log.txt                             N    12237  Wed Sep  4 06:49:09 2019

                9204224 blocks of size 1024. 6877104 blocks available
```

## Checking contents of log.txt
```
cat log.txt | grep 21 
# Port 21 is the standard FTP port.
Port                            21
```
