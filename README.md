# PowerShell-Cheat-Sheet
`The following document was created for educational use only.`

## Introduction

According to Microsoft, the Powershell program is a command shell, scripting language, and automation platform included in most forms of Microsoft Windows. While not the first language that people think of when discussing scripting, it is nontheless useful when done properly. The program is open-source, and can access other data stores with ease.

This is a document recapping each command learned in the Powershell (COSC-2101-07) course taught at Durham College. Every command listed will be in chronological order, starting from Week 3's lesson. Please note that everything covered in this document is a representation of personal experience, and should not be used as a main reference point; Microsoft itself offers much more detailed explanations for all commands provided.

===================

## Commands

The following is a list of all commands researched and used for the course. Please remember that this is not a perfect encapsulation of everything that the commands can do.

### Get-Content
Gets the content of the item and the specified location.

```bash
[-ReadCount]
[-TotalCount]
[-Tail]
[-Path]
[-Filter]
[-Include]
[-Exclude]
[-Force]
[-Credential]
```

```bash
C:\> Get-Content -Path .\Example.txt
```

### Get-Process
Gets the processes that are running on the local computer.

```bash
[-Name]
[-Module]
[-FileVersionInfo]
```

```bash
C:\> Get-Process -Name Example
```

### Import-CSV
Creates a table from items in a CSV file.

```bash
[-Delimiter]
[-Path]
[-Header]
[-Encoding]
```

```bash
C:\> Import-Csv -Path .\Examples.csv
```

### Export-CSV
Converts objects into a series of CSV strings and saves them to a file.

```bash
[-InputObject]
[-Path]
[-Force]
[-NoClobber]
[-Delimiter]
[-IncludeTypeInformation]
[-NoTypeInformation]
[-WhatIf]
[-Confirm]
```

```bash
C:\> Get-Process -Name Example | Export-Csv -Path .\Example.csv
```

### Out-File
Sends output to a file.

```bash
[-FilePath]
[-Encoding]
[-Append]
[-Force]
[-InputObject]
[-WhatIf]
[-Confirm]
```

```bash
C:\> Get-Process | Out-File -FilePath .\Example.txt
```

### Get-Service
Gets the services on the computer.

```bash
[-Name]
[-DependentServices]
[-RequiredServices]
[-Include]
[-Exclude]
```

```bash
C:\> Get-Service
```

### ConvertTo-CSV
Converts .NET objects into CSV strings.

```bash
[-InputObject]
[-Delimiter]
[-IncludeTypeInformation]
[-NoTypeInformation]
[-NoHeader]
```

```bash
C:\> Get-Process | ConvertTo-Csv -NoTypeInformation
```

### ConvertTo-HTML
Converts .NET objects into HTML that can be displayed in a web browser.

```bash
[-InputObject]
[-Property]
[-Body]
[-Head]
[-Title]
[-As]
[-Meta]
```

```bash
C:\> ConvertTo-Html -InputObject (Example)
```

### Stop-Process
Stops one or more running processes.

```bash
[-Id]
[-PassThru]
[-Force]
[-WhatIf]
[-Confirm]
```

```bash
C:\> Stop-Process -Name "Example"
```

### Import-CliXML, Export-CliXML
Imports a CLIXML file and creates corresponding objects in Powershell.

```bash
[-Path]
[-IncludeTotalCount]
[-Skip]
[-First]
```

Exports an XML-based representation of an object or objects and stores it in a file.

```bash
[-Depth]
[-Path]
[-InputObject]
[-Force]
[-WhatIf]
[-Confirm]
```

```bash
C:\> Get-Process | Export-Clixml -Path .\Example.xml
C:\> Import-Clixml -Path .\Example.xml
```

### Get-ADComputer
Gets one or more Active Directory computers.

```bash
[-AuthType]
[-Credential]
[-Filter]
[-Properties]
[-ResultPageSize]
[-SearchBase]
[-SearchScope]
[-Server]
```

```bash
C:\> Get-ADComputer -Identity "Example" -Properties *
```

### Select-Object
Select objects or object properties.

```bash
[-InputObject]
[-Property]
[-ExcludeProperty]
[-ExpandProperty]
[-CaseInsensitive]
[-Last]
[-First]
[-Skip]
[-Wait]

```bash
C:\> Get-Process | Select-Object -Property ProcessName
```

### Get-WmiObject
Gets instances of WMI classes or information about available ones.

```bash
[-Class]
[-Property]
[-Filter]
[-Amended]
[-AsJob]
[-Locale]
[-Authority]
[-ComputerName]
[-Namespace]
```

```bash
Get-WmiObject -Class Example -ComputerName 10.20.30.40
```

### Get-EventLog
Gets the events in a event log, or a list of event logs, on a computer.

```bash
[-LogName]
[-ComputerName]
[-Newest]
[-After]
[-Before]
[-UserName]
[-Index]
[-Source]
```

```bash
Get-EventLog -List
```

### New-NetIPAddress
Creates and configures an IP address.

```bash
[-IPAddress]
[-InterfaceAlias]
[-DefaultGateway]
[-AddressFamily]
[-Type]
[-PrefixLength]
[-PolicyStore]
[-CimSession]
[-AsJob]
[-WhatIf]
[-Confirm]
```

```bash
New-NetIPAddress -InterfaceIndex # -IPAddress 10.20.30.40 -PrefixLength # -DefaultGateway 50.60.70.80
```

### Install-WindowsFeature
Install one or more roles/services/features onto a specified server.

```bash
[-Name]
[-Restart]
[-IncludeAllSubFeature]
[-IncludeManagementTools]
[-Source]
[-ComputerName]
[-Credential]
[-LogPath]
[-WhatIf]
[-Confirm]
```

```bash
Install WindowsFeature -Name Example -ComputerName Example
```

### Install-ADDSForest
Creates a new Active Directory forest.

```bash
[-DomainName]
[-CreateDnsDelegation]
[-DatabasePath]
[-NoDnsOnNetwork]
[-DomainMode]
[-ForestMode]
[-InstallDns]
[-LogPath]
[-Force]
[-WhatIf]
[-Confirm]
```

```bash
Install-ADDSForest -DomainName "Example.com" -InstallDNS
```

### New-ADUser
Creates an Active Directory user.

```bash
[-AccountExpirationDate]
[-AccountPassword]
[-AuthenticationPolicy]
[-Certificates]
[-City]
[-Credential]
[-Department]
[-Description]
[-DisplayName]
[-EmailAddress]
[-Enabled]
[-GivenName]
[-Initials]
[-Name]
[-Organization]
[-OtherName]
[-Path]
[-SamAccountName]
[-Server]
[-State]
[-Surname]
[-Title]
[-WhatIf]
[Confirm]
```

```bash
New-ADUser -Name 'Example'
```

### Get-DnsClientServerAddress
Gets DNS server IP addresses from the TCP/IP properties on an interface.

```bash
[-InterfaceIndex]
[-InterfaceAlias]
[-AddressFamily]
[-CimSession]
[-AsJob]
```

```bash
Get-DnsClientServerAddress
```

### Add-Computer
Add a local computer to a domain or workgroup.

```bash
[-ComputerName]
[-Credential]
[-DomainName]
[-OUPath]
[-Server]
[-Options]
[-Restart]
[-PassThru]
[-NewName]
[-Force]
[-WhatIf]
[-Confirm]
```

```bash
Add-Computer -DomainName Example -Restart
```

### Invoke-Command
Runs commands on local and remote computers.

```bash
[-StrictMode]
[-ScriptBlock]
[-NoNewScope]
[-InputObject]
[-ArgumentList]
```

```bash
Invoke-Command -FilePath C:\example.ps1 -ComputerName Example
```

### Enter-PSSession
Starts an interactive session with a remote computer.

```bash
[-ComputerName]
[-EnableNetworkAccess]
[-Credential]
[-ConfigurationName]
[-Port]
[-UseSSL]
[-ApplicationName]
[-SessionOption]
[-Authentication]
[-CertificateThumbprint]
```

```bash
Enter-PSSession
[host]: >
```

### New-PSSession
Creates a persistent connection to a local or remote computer.

```bash
[-ComputerName]
[-Credential]
[-Name]
[-EnableNetworkAccess]
[-Port]
[-UseSSL]
[-ApplicationName]
[-ThrottleLimit]
[-SessionOption]
[-Authentication]
```

```bash
New-PSSession -ComputerName Example
```

### Import-Module
Adds modules to the current session.

```bash
[-Global]
[-Prefix]
[-Name]
[-Function]
[-Cmdlet]
[-Variable]
[-Alias]
[-Force]
[-PassThru]
[-ArgumentList]
[-NoClobber]
[-Scope]
```

```bash
Import-Module -Name Example
```

### Enable-PSRemoting
Configures the computer to receive remote commands.

```bash
[-Force]
[-SkipNetworkProfileCheck]
[-WhatIf]
[-Confirm]
```

```bash
Enable-PSRemoting
```

### Get-NetAdapter
Gets the basic network adapter properties.

```bash
[-Name]
[-IncludeHidden]
[-CimSession]
[-AsJob]
```

```bash
Get-NetAdapter -Name *
```

### Remove-PSSession
Close one or more Powershell sessions.

```bash
[-Id]
[-WhatIf]
[-Confirm]
```

```bash
Remove-PSSession -Id #
```

### Get-CimClass
Gets a list of CIM classes in a specific namespace.

```bash
[-ClassName]
[-Namespace]
[-ComputerName]
[-MethodName]
[-PropertyName]
[-QualifierName]
```

```bash
Get-CimClass -ClassName Example
```

### Get-CimInstance
Gets the CIM instance of a class from a CIM Server.

```bash
[-ClassName]
[-ComputerName]
[-Namespace]
[-OperationTimeoutSec]
[-Filter]
[-Property]
```

```bash
Get-CimInstance -ClassName Example
```

///

### New-ScheduledTaskAction
Creates a scheduled task action.

```bash
[-Id]
[-Execute]
[-Argument]
[-WorkingDirectory]
[-CimSession]
[-AsJob]
```

```bash
New-ScheduledTaskAction -Execute "Example.exe"
```

### New-ScheduledTaskTrigger
Creates a scheduled task trigger object.

```bash
[-RandomDelay]
[-At (Date/Time)]
[-Daily]
[-Once]
[-RepetitionDuration]
[-RepetitionInterval]
[-CimSession]
[-ThrottleLimit]
[-AsJob]
```

```bash
New-ScheduledTaskTrigger -Once -At (time)
```

### New-ScheduledTaskPrincipal
Creates an object that contains a scheduled task principal.

```bash
[-Id]
[-RunLevel]
[-UserId]
[-LogonType]
[-CimSession]
[-ThrottleLimit]
[-AsJob]
```

```bash
New-ScheduledTaskPrincipal -UserId "Example" -LogonType ServiceAccount
```

### New-ScheduledTaskSettingsSet
Creates a new scheduled task settings object.

```bash
[-Compatibility]
[-Disable]
[-Hidden]
[-IdleWaitTimeout]
[-NetworkId]
[-NetworkName]
[-MaintenancePeriod]
[-StartWhenAvailable]
```

```bash
Register-ScheduledTask Example -Action ActionExample New-ScheduledTaskSettingsSet
```

### New-ScheduledTask
Creates a new scheduled task instance.

```bash
[-Action]
[-Description]
[-Principal]
[-Settings]
[-Trigger]
[-CimSession]
[-AsJob]
```

```bash
New-ScheduledTask -Action Example -Principal -Example -Trigger Example -Settings Example
```

### Register-ScheduledTask
Registers a scheduled task definition on a computer.

```bash
[-Force]
[-Password]
[-User]
[-TaskName]
[-Action]
[-Description]
[-Settings]
[-Trigger]
[-RunLevel]
[-CimSession]
[-AsJob]
```

```bash
Register-ScheduledTask -TaskName "Example" -Trigger (time)
```

=========

## Week 3 - Pipeline
Running multiple commands in a "pipeline" ( | ) causes the output of each command to be passed to the next, running each in sequence. It's important to know that any commands placed in parenthesis runs first, and can contain their own pipelines.

Commands Featured: 
`
[Import-CSV]
[ConvertTo-CSV]
[Export-CSV]
[Import-CliXML]
[Export-CliXML]
[Get-Content]
[ConvertTo-HTML]
[Out-File]
[Get-Service]
[Stop-Service]
`

## Week 4 - Pipeline, Cont.
When working with different commands, it's important to look into the syntax of each, to make sure things won't break on a user when trying to run it.

Commands Featured: 
`
[Get-ADComputer]
[Get-Service]
[Select-Object]
[Get-WmiObject]
[Get-Process]
[Import-CSV]
[Get-EventLog]
`

## Lab 1 - Installing And Setting Up Server Core

Commands Featured: 
`
[New-NetIPAddress]
[Install-WindowsFeature]
[Install-ADDSForest]
[New-ADUser]
[Get-DnsClientServerAddress]
[Add-Computer]
`

## Week 5 - Remoting

Commands Featured: 
`
[Invoke-Command]
[Enter-PSSession]
[New-PSSession]
[Import-Module]
[Enable-PSRemoting]
[Get-EventLog]
[Get-Module]
[Get-NetAdapter]
[Remove-PSSession]
`

## Week 6 - Windows Management Instrumentation
WMI is an external interface made to organize the management data in a typical Windows computer. If done correctly, PowerShell can access and use this information to its advantage.

Commands Featured: 
`
[Get-CimClass]
[Select-Object]
[Get-CimInstance]
[Get-WmiObject]
`

## Week 9 - The Task Scheduler
The Task Scheduler allows a user to run scripts or programs on schedules without intervention from the user or administrator. It's easy to do so through the GUI, but it can also be done with Powershell.


Commands Featured: 
`
[New-ScheduledTaskAction]
[New-ScheduledTaskTrigger]
[New-ScheduledTaskPrincipal]
[New-ScheduledTaskSettingsSet]
[New-ScheduledTask]
[Register-ScheduledTask]
`

## Lab 4 - Importing Users and OUs into Domains

Commands Featured: 
`
[Set-ExecutionPolicy]
[Import-Module]
[Import-Csv]
[ConvertTo-SecureString]
[New-ADUser]
[New-ADOrganizationalUnit]
[Get-ADUser]
[Move-ADObject]
[New-ADGroup]
[Set-ADAccountPassword]
[Disable-ADAccount]
[Enable-ADAccount]
[Unlock-ADAccount]
[Remove-ADUser]
[Add-ADGroupMember]
[Get-ADGroupMember]
`
