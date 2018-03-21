# Git CLI Authentication Guide for Windows
Users have come across the issue where trying to access repositories on GitHub via command line fails with errors:
- Failed to authenticate
- Prompted to enter password when performing actions

## Solution
The developer will need to Download [Git credential manager for windows](https://github.com/Microsoft/Git-Credential-Manager-for-Windows)

To use the GCM, you can download the [latest installer](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest). To install, double-click Setup.exe and follow the instructions presented.

When prompted to select your terminal emulator for Git Bash you should choose the Windows' default console window, or make sure GCM is [configured to use modal dialogs](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/blob/master/Docs/Configuration.md#modalprompt). GCM cannot prompt you for credentials, at the console, in a MinTTY setup.

Doing this should allow you to seamlessly use the command line to clone, push, etc...
