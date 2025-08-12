# MDT — Export Drivers / Packages / OS / Apps (VBScript)

Exports MDT content by reading *Control* XML and copying source folders to an export path, preserving group structure.

## Configure
Create `ExportMDT.ini` next to the script:
```ini
TEXT_NOMDP=\\MDTServer\DeploymentShare$   ; MDT root (UNC or local path)
TEXT_NOMREPEXPORT=E:\MDT_Export           ; Export destination
```

## Run
```bat
cscript //nologo ExportMDT.vbs
```

**Notes:** ensure read/write permissions and enough free disk space.  
**Full article:** https://blog.wuibaille.fr/2025/08/mdt-export-drivers-packages-os-apps/
