```json
{
    "$schema": "https://aka.ms/terminal-profiles-schema",

    "defaultProfile": "{14ad203f-52cc-4110-90d6-d96e0f41b64d}",

    "profiles":
    [
        {
            "guid": "{61c54bbd-c2c6-5271-96e7-009a87ff44bf}",
            "name": "Windows PowerShell",
            "commandline": "powershell.exe",
            "hidden": false,
            "startingDirectory" : "."
        },
        {
            "guid": "{0caa0dad-35be-5f56-a8ff-afceeeaa6101}",
            "name": "Command Prompt",
            "commandline": "cmd.exe",
            "hidden": false,
            "startingDirectory" : "."
        },
        {
            "guid": "{b453ae62-4e3d-5e58-b989-0a998ec441b8}",
            "hidden": true,
            "name": "Azure Cloud Shell",
            "source": "Windows.Terminal.Azure"
        },
        {
            "acrylicOpacity" : 1,
            "closeOnExit" : true,
            "commandline" : "%PROGRAMFILES%/Git/usr/bin/bash.exe --login",
            "colorScheme": "Campbell",
            "cursorColor" : "#FFFFFF",
            "cursorShape" : "bar",
            "fontFace" : "Consolas",
            "fontSize" : 14,
            "guid" : "{14ad203f-52cc-4110-90d6-d96e0f41b64d}",
            "historySize" : 9001,
            "icon" : "%PROGRAMFILES%/Git/mingw64/share/git/git-for-windows.ico",
            "name" : "Git Bash",
            "padding" : "0, 0, 0, 0",
            "snapOnInput" : true,
            "startingDirectory" : ".",
            "useAcrylic" : true
        },
        {
            "guid": "{58ad8b0c-3ef8-5f4d-bc6f-13e4c00f2530}",
            "hidden": false,
            "name": "Debian",
            "source": "Windows.Terminal.Wsl"
        }
    ],

    "schemes": [

    ],

    "keybindings": []
}
```
