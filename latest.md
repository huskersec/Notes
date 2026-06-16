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




Ghidriff:

ghidra_diff_engine.py patch:
```
@@ -1618,7 +1618,13 @@
             self.normalize_ghidra_decomp(new_code)
 
             old_code_no_sig = self.remove_code_sig(ematch_1['code'])
+            if (old_code_no_sig == ""):
+                old_code_no_sig = []
+
             new_code_no_sig = self.remove_code_sig(ematch_2['code'])
+            if (new_code_no_sig == ""):
+                new_code_no_sig = []

             self.normalize_ghidra_decomp(old_code_no_sig)
             self.normalize_ghidra_decomp(new_code_no_sig)
```


```
ghidriff.exe .\apr25_vuln_clfs.sys .\may25_patched_clfs.sys
```


```
```


HEVD:

IOCTL decode in windbg:
```
!ioctldecode 0x222003
```




