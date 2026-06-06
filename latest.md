## Latest Notes ##

:exclamation: ESXi adapters (vmxnet) don't play well with KDNET!

Setup target (debugee) for debugging:
```
bcdedit /debug on
bcdedit /dbgsettings net hostip:<YOUR_DEBUGGER_IP> port:50000 nodhcp
bcdedit /set "{dbgsettings}" busparams <output from kdnet for adapter>
```

Check if supported adapter is present:
```
kdnet.exe
```

Debugging lsass.exe:
```
!process 0 0 lsass.exe
.process /i /p <EPROCESS address>
g

.reload /user
lm
```




