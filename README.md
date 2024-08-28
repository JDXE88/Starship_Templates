# Starship Templates

This repository contains TOML templates that I created. I thought people might find them useful.

## Prerequisites

- **Nerd Font:** Install a Nerd Font (preferably not a mono font, as VS Code may have issues with them).
- **Starship:** Install the Starship package.
  - [Installation Setup](https://github.com/starship/starship)
- **Fonts:** [Download Nerd Fonts](https://www.nerdfonts.com/font-downloads)
- **Icons Cheat Sheet:** [Nerd Fonts Cheat Sheet](https://www.nerdfonts.com/cheat-sheet)

## Templates Preview

Here is a preview of one of the templates:
![image](https://github.com/user-attachments/assets/407cfe3f-909c-4899-9d14-78a416f8e2cf)

![Template Preview](https://github.com/user-attachments/assets/aaf6cfe1-cd3b-46b9-8943-57c172209f1a)

## PowerShell Setup Instructions

If you are using PowerShell, follow these steps:

1. **List Installed Packages:**
   ```powershell
   winget list starship
   ```

2. **Install Starship:**
   ```powershell
   winget install --id Starship.Starship # OR
   scoop install starship
   ```

3. **Set Execution Policy:**
   ```powershell
   Set-ExecutionPolicy RemoteSigned -Scope CurrentUser
   ```

4. **Install Scoop (if not already installed):**
   ```powershell
   irm get.scoop.sh | iex
   ```

5. **Create Configuration Directory and File:**
   ```powershell
   New-Item -ItemType Directory -Force ~/.config
   New-Item -ItemType file ~/.config/starship.toml
   ```

6. **Edit PowerShell Profile:**
   ```powershell
   Notepad.exe $PROFILE
   ```

7. **Add the Following to Your Profile:**
   ```powershell
   $starshipPath = Get-ChildItem -Path $env:ProgramFiles -Recurse -Filter "starship.exe" -ErrorAction SilentlyContinue | Select-Object -First 1 -ExpandProperty FullName
   Invoke-Expression (& $starshipPath init powershell --print-full-init | Out-String)
   Invoke-Expression (&starship init powershell)

   function Configure-Starship {
       cd ~/.config
       code starship.toml
   }
   ```

8. **Save and Close PowerShell.**

9. **Reopen PowerShell.**

10. **Run Configuration Command:**
    ```powershell
    Configure-Starship
    ```

11. **Copy and Paste the TOML Configuration or Rename the File to `starship.toml`.**

   If you can't find the installation path, it is located at:
   ```
   Directory: C:\Users\<username>\.config\starship.toml
   ```

This format organises the instructions clearly and provides a structured approach to setting up your templates and configuring Starship in PowerShell.
