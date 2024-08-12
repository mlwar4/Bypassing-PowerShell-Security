# Bypassing-PowerShell-Security
This is made for educational purposes only I am NOT held responsible for any damages that might occur using this repo.


# Bypassing PowerShell Security

- Using [Invisi-Shell](https://github.com/OmerYa/Invisi-Shell) For bypassing the security controls in PowerShell.

- The tool hooks the .NET assemblies `System.Management.Automation.dll` and `System.Core.dll` to bypass logging

- It uses a CLR profiler api to do preform the hook.

- A common language runtime CLR profiler is a DLL that consists of functions that receive messages from , and send messages to , the CLR by using the profiling API. The profiler DLL is loaded by the CLR at run time

## Using Invisi-Shell

With admin privs

```
RunWithPathAsAdmin.bat
```

non admin privs

```
RunWithRegistryNonAdmin.bat
```

Type exit from the new PowerShell session to complete the cleanup


---

# Bypassing AV signatures for PowerShell


We can always load scripts in memory and avoid detection using AMSI bypass.

to bypass signature based detection of on-disk PowerShell scripts by Windows Defender we can use [AMSITrigger](https://github.com/RythmStick/AMSITrigger) tool to identify the exact part of a script tthat is detected.

We can use [DefenderCheck](https://github.com/t3hbb/DefenderCheck) to identify code and strings from a binary / file that Windows Defender may flag.


Simply provide a path to the script file to scan it :

```
AmsiTrigger_x64.exe -i C:\AD\Tools\Invoke-PowerShellTCP_Detected.ps1
DefenderCheck.exe PowerUp.ps1
```

For full obfuscation of PS scripts check this [https://github.com/danielbohannon/Invoke-Obfuscation] 
