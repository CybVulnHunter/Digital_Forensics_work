# Windows Forensics and Incident Response using PowerShell

## Table of Contents
- [Introduction](#introduction)
- [Prerequisites](#prerequisites)
- [Lab Setup and Tools](#lab-setup-and-tools)
- [Exercises](#exercises)
  - [Exercise 1: Investigating User Accounts](#exercise-1-investigating-user-accounts)
  - [Exercise 2: Checking Running Processes](#exercise-2-checking-running-processes)
  - [Exercise 3: Investigating Services](#exercise-3-investigating-services)
  - [Exercise 4: Checking Scheduled Tasks](#exercise-4-checking-scheduled-tasks)
  - [Exercise 5: Investigating Registry Entries](#exercise-5-investigating-registry-entries)
  - [Exercise 6: Checking Active Internet Connections](#exercise-6-checking-active-internet-connections)
  - [Exercise 7: Investigating File Shares](#exercise-7-investigating-file-shares)
  - [Exercise 8: Investigating Files](#exercise-8-investigating-files)
  - [Exercise 9: Checking Firewall Settings](#exercise-9-checking-firewall-settings)
  - [Exercise 10: Investigating Network Sessions](#exercise-10-investigating-network-sessions)
  - [Exercise 11: Analyzing Log Entries](#exercise-11-analyzing-log-entries)
- [Conclusion](#conclusion)

## Introduction

Windows PowerShell is a powerful tool for performing forensic analysis and incident response on Windows systems. This advanced-level lab will guide you through various forensic and incident response tasks using PowerShell. You will learn to investigate user accounts, processes, services, scheduled tasks, registry entries, internet connections, file shares, files, firewall settings, sessions, and log entries.

## Prerequisites

- **Advanced knowledge of Windows operating systems**
- **Familiarity with forensic principles and techniques**
- **Understanding of PowerShell scripting**
- **Basic knowledge of network and system security concepts**
- **PowerShell version 5.1 or later** (recommended)
- **Administrator access** on the Windows system

## Lab Setup and Tools

- A Windows computer or virtual machine
- [PowerShell](https://docs.microsoft.com/en-us/powershell/scripting/install/installing-powershell) installed
- Administrator access on the Windows system

## Exercises

### Exercise 1: Investigating User Accounts

**Objective**: Use PowerShell to list and investigate user accounts on the system.

```powershell
Get-LocalUser
```

```powershell
Get-LocalGroupMember Administrators
```

```powershell
Get-LocalUser -Name "username" | Format-List *
```

**Expected Output**: Information about all user accounts and members of the Administrators group.

### Exercise 2: Checking Running Processes

**Objective**: Use PowerShell to list and analyze running processes on the system.

```powershell
Get-Process | Format-Table -AutoSize
```

```powershell
Get-Process -Id PID | Format-List *
```

```powershell
Get-WmiObject Win32_Process | Select-Object Name, ProcessId, ParentProcessId | Format-Table -AutoSize
```

**Expected Output**: Information about running processes, including details and parent process IDs.

### Exercise 3: Investigating Services

**Objective**: Use PowerShell to list and analyze services running on the system.

```powershell
Get-Service | Format-Table -AutoSize
```

```powershell
Get-Service -Name "servicename" | Format-List *
```

```powershell
Get-WmiObject Win32_Service | Select-Object Name, DisplayName, ProcessId | Format-Table -AutoSize
```

**Expected Output**: Information about all services and details of specific services.

---

## Exercise 4: Checking Scheduled Tasks

**Objective**: Identify scheduled tasks that may indicate malicious activity.

```powershell
Get-ScheduledTask | Select-Object TaskName, TaskPath, State | Format-Table -AutoSize
```

```powershell
Get-ScheduledTaskInfo -TaskName "TaskName"
```

**Expected Output**: A list of scheduled tasks and their execution status.

---

## Exercise 5: Investigating Registry Entries

**Objective**: Analyze registry keys for suspicious modifications.

```powershell
Get-ItemProperty -Path "HKLM:\Software\Microsoft\Windows\CurrentVersion\Run"
```

```powershell
Get-ItemProperty -Path "HKCU:\Software\Microsoft\Windows\CurrentVersion\Run"
```

**Expected Output**: Registry keys listing programs set to run at startup.

---

## Exercise 6: Checking Active Internet Connections

**Objective**: Identify open network connections to detect suspicious activity.

```powershell
Get-NetTCPConnection | Format-Table -AutoSize
```

```powershell
netstat -ano | findstr "ESTABLISHED"
```

**Expected Output**: A list of active network connections and their status.

---

## Exercise 7: Investigating File Shares

**Objective**: Identify shared folders and their permissions.

```powershell
Get-SmbShare | Format-Table -AutoSize
```

```powershell
Get-SmbShareAccess -Name "ShareName"
```

**Expected Output**: A list of shared folders and access permissions.

---

## Exercise 8: Investigating Files

**Objective**: Identify recently modified or suspicious files.

```powershell
Get-ChildItem -Path "C:\Users\Public\Documents" -Recurse | Sort-Object LastWriteTime -Descending | Select-Object -First 10
```

```powershell
Get-ChildItem -Path "C:\Windows\System32" -Filter "*.exe" | Select-Object Name, LastWriteTime
```

**Expected Output**: Recently modified files in specific directories.

---

## Exercise 9: Checking Firewall Settings

**Objective**: Identify open ports and firewall rules.

```powershell
Get-NetFirewallRule | Select-Object DisplayName, Direction, Action | Format-Table -AutoSize
```

```powershell
Get-NetFirewallPortFilter | Format-Table -AutoSize
```

**Expected Output**: A list of firewall rules and their status.

---

## Exercise 10: Investigating Network Sessions

**Objective**: Identify active user sessions on the system.

```powershell
Get-NetSession | Format-Table -AutoSize
```

```powershell
qwinsta
```

**Expected Output**: A list of active user sessions.

---

## Exercise 11: Analyzing Log Entries

**Objective**: Extract logs to identify security incidents.

```powershell
Get-EventLog -LogName Security -Newest 10 | Format-Table -AutoSize
```

```powershell
Get-WinEvent -LogName Microsoft-Windows-Security-Auditing | Select-Object TimeCreated, Id, Message -First 10
```

**Expected Output**: Recent security event logs relevant to forensic analysis.



## Conclusion

By completing these exercises, you have gained advanced skills in using PowerShell for Windows forensics and incident response. You have learned to investigate user accounts, processes, services, scheduled tasks, registry entries, internet connections, file shares, files, firewall settings, sessions, and log entries. These skills are essential for conducting comprehensive forensic investigations and responding to security incidents effectively.

For further learning, consider exploring **PowerShell modules** like `PowerForensics` or `PSReadline` for enhanced forensic capabilities.



