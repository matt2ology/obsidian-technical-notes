---
aliases:
note-type: permanent
date-created: 2024-05-28
long-form-date-created: Tuesday, May 28, 2024
week-created: Week 22.2
time-created: 05:04 PM
---

# C++ Development on VS Code

Related :

## Set up your C++ Environment

### Install a C++ compiler on Windows

If you're doing C++ development for Windows, we recommend installing the Microsoft Visual C++ (MSVC) compiler.

To install MSVC, open the VS Code terminal (CTRL + \`) and paste in the following command:

```sh
winget install Microsoft.VisualStudio.2022.BuildTools --force --override "--wait --passive --add Microsoft.VisualStudio.Workload.VCTools --add Microsoft.VisualStudio.Component.VC.Tools.x86.x64 --add Microsoft.VisualStudio.Component.Windows11SDK.22000"
```

> **Note**: You can use the C++ toolset from Visual Studio Build Tools along with Visual Studio Code to compile, build, and verify any C++ codebase as long as you also have a valid Visual Studio license (either Community, Pro, or Enterprise) that you are actively using to develop that C++ codebase.

### Verifying the compiler installation

1. Open the **Developer Command Prompt for VS** by typing 'developer' in the Windows Start menu.
2. Check your MSVC installation by typing `cl` into the Developer Command Prompt for VS. You should see a copyright message with the version and basic usage description.

   > **Note**: To use MSVC from the command line or VS Code, you must run from a **Developer Command Prompt for VS**. An ordinary shell such as PowerShell, Bash, or the Windows command prompt does not have the necessary path environment variables set.

### Other compiler options

If you're targeting Linux from Windows, check out [Using C++ and Windows Subsystem for Linux (WSL) in VS Code](https://code.visualstudio.com/docs/cpp/config-wsl "https://code.visualstudio.com/docs/cpp/config-wsl"). Or, you could [install GCC on Windows with MinGW](https://code.visualstudio.com/docs/cpp/config-mingw "https://code.visualstudio.com/docs/cpp/config-mingw").

## Create a C++ file

```c
#include <iostream>
int main(){
    std::cout << "Hello, world!" << std::endl;
    return Success;
}
```

## Relaunch using the developer command prompt

You are using a windows machine with the MSVC compiler, so you need to start VS Code from the developer command prompt for all environment variables to be set correctly. To relaunch using the developer command prompt:

1. Open the Developer Command Prompt for VS by typing "developer" in the Windows Start menu. Select the Developer Command Prompt for VS, which will automatically navigate to your current open folder.
2. Type "code" into the command prompt and hit enter. This should relaunch VS Code and take you back to this walkthrough.

## Run and debug your C++ file

Open file hit `F5`

### Customize debugging

To customize your debug configuration, select the Explorer in the activity bar
and open a folder that includes your C++ file. Open the C++ file, and select
"Add Debug Configuration" to the right of the play button. The new debug
configuration is saved to your project's launch.json file.

Select a debug configuration > C/C++: g++/exe build and debug active file
