## Running Processes

* `sc query`
```
SERVICE_NAME: WindowsScheduler
DISPLAY_NAME: System Scheduler Service
        TYPE               : 10  WIN32_OWN_PROCESS  
        STATE              : 4  RUNNING 
                                (STOPPABLE, PAUSABLE, ACCEPTS_SHUTDOWN)
        WIN32_EXIT_CODE    : 0  (0x0)
        SERVICE_EXIT_CODE  : 0  (0x0)
        CHECKPOINT         : 0x0
        WAIT_HINT          : 0x0
```

* this process stands out, let's get some more detail

## Windows Scheduler

* `sc qc WindowsScheduler`
```
SERVICE_NAME: WindowsScheduler 
        TYPE               : 10  WIN32_OWN_PROCESS  
        STATE              : 4  RUNNING 
                                (STOPPABLE, PAUSABLE, ACCEPTS_SHUTDOWN)
        WIN32_EXIT_CODE    : 0  (0x0)
        SERVICE_EXIT_CODE  : 0  (0x0)
        CHECKPOINT         : 0x0
        WAIT_HINT          : 0x0
```

* `sc query WindowsScheduler`

```
SERVICE_NAME: WindowsScheduler 
        TYPE               : 10  WIN32_OWN_PROCESS  
        STATE              : 4  RUNNING 
                                (STOPPABLE, PAUSABLE, ACCEPTS_SHUTDOWN)
        WIN32_EXIT_CODE    : 0  (0x0)
        SERVICE_EXIT_CODE  : 0  (0x0)
        CHECKPOINT         : 0x0
        WAIT_HINT          : 0x0
```

