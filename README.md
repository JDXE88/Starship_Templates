# Starship_Templates
Just some TOML templates i made thought people would like them. 

# Prerequisites: 
A nerd font install pref not a mono one as VS Code does not like them. 
package starship installed
link to installation setup: https://github.com/starship/starship
fonts: https://www.nerdfonts.com/font-downloads
icons cheetsheet: https://www.nerdfonts.com/cheat-sheet

Here is a list of the templates and what they will look like:

![image](https://github.com/user-attachments/assets/aaf6cfe1-cd3b-46b9-8943-57c172209f1a)

Remeber if you are using powershell to 
1. winget list starship
2. winget install --id Starship.Starship # OR scoop install starship
3. Set-ExecutionPolicy RemoteSigned -Scope CurrentUser
4. irm get.scoop.sh | iex
5. New-Item -ItemType Directory -Force ~/.config;New-Item -ItemType file ~/.config/starship.toml;
6. Notepad.exe $PROFILE
7. Add this to your PROFILE:

$starshipPath = Get-ChildItem -Path $env:ProgramFiles -Recurse -Filter "starship.exe" -ErrorAction SilentlyContinue | Select-Object -First 1 -ExpandProperty FullName
Invoke-Expression (& $starshipPath init powershell --print-full-init | Out-String)
Invoke-Expression (&starship init powershell)
function Configure-Starship {
	cd  ~/.config;code starship.toml
}

7. Save and Close Powershell
8. Reopen Powershell
9. Type "Configure-Starship"
10. Copy and paste in the TOML or rename the file to starship.toml

if you can't find the installation path it is Directory: C:\Users\<username>\.config\starship.toml
