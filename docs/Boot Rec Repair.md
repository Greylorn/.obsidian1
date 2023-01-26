bootrec /FixMbr 
bootrec /FixBoot 
bootrec /ScanOs 
bootrec /RebuildBcd


sfc /scannow
chkdsk /f C:
dism /online /cleanup-image /restorehealth