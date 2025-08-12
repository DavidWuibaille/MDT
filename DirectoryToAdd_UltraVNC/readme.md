# Add UltraVNC to WinPE (MDT) — Extra Directory

Inject **UltraVNC** into your MDT **WinPE** and auto-start it before the wizard for remote support.

## Repo contents
- `UltraVnc/` – UltraVNC binaries & config (edit `ultravnc.ini` as needed)
- `extra.cmd` – launches UltraVNC in WinPE
- `Unattend.xml` – optional sample (RunSynchronous) if you prefer unattend

## Requirements
- MDT (Deployment Workbench), Windows ADK + WinPE add-on
- Your MDT **Deployment Share** (x64 boot image)

## Quick setup
1. **Download/clone** the folder:  
   `DirectoryToAdd_UltraVNC`
2. In **Deployment Workbench → Deployment Share → Properties → Windows PE**:
   - **Extra directory to add** (x64): browse to `DirectoryToAdd_UltraVNC`
   - **Prestart command** (choose one, based on your layout):
     - If the folder contains a `system32\extra.cmd` subfolder:
       ```
       %SystemRoot%\System32\extra.cmd
       ```
     - If `extra.cmd` is at the root of the extra directory:
       ```
       X:\extra.cmd
       ```
3. **Update Deployment Share** → *Completely regenerate boot images*.
4. Boot from the new **LiteTouchPE_x64.iso/WIM**. UltraVNC starts before the MDT wizard.

## Doc
visite : https://blog.wuibaille.fr/2024/05/adding-tools-to-winpe/