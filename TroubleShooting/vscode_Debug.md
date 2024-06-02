# How to Uninstall and Reinstall VSCode on Windows

## Step 1: Uninstall the Program
1. Search Windows for “Add or remove programs” and open the resulting control panel.
2. In this panel, search for “visual studio” and you’ll find VSCode listed under Microsoft Visual Studio Code.
3. Click the three dots next to the program name and find the option to Uninstall.

## Step 2: Delete Related Directories
To get a truly fresh re-install, you need to also delete a couple of directories that contain VSCode related files and settings.

1. Open PowerShell and run these two commands:

```powershell
rm ~/APPDATA/Roaming/Code
rm ~/.vscode
