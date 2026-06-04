## Latest Notes ##

:exclamation: ESXi adapters (vmxnet) don't play well with KDNET!

Setup target (debugee) for debugging:
```
bcdedit /debug on
bcdedit /dbgsettings net hostip:<YOUR_DEBUGGER_IP> port:50000
```

Check if supported adapter is present:
```
kdnet.exe
```




