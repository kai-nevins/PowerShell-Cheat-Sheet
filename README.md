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
C:\> Get-Content -Path .\Example.txt
```

### Import-CSV
Creates a table from items in a CSV file.

```bash
C:\> Import-Csv -Path .\Examples.csv
```

### Get-Process
Gets the processes that are running on the local computer.

```bash
C:\> Get-Process -Name Example
```

### Export-CSV
Converts objects into a series of CSV strings and saves them to a file.

```bash
C:\> Get-Process -Name Example | Export-Csv -Path .\Example.csv
```

### Out-File
Sends output to a file.

```bash
C:\> Get-Process | Out-File -FilePath .\Example.txt
```

### Get-Service
Gets the services on the computer.

```bash
C:\> Get-Service
```

### ConvertTo-CSV
Converts .NET objects into CSV strings.

```bash
C:\> Get-Process | ConvertTo-Csv -NoTypeInformation
```

### ConvertTo-HTML
Converts .NET objects into HTML that can be displayed in a web browser.

```bash
C:\> ConvertTo-Html -InputObject (Example)
```

### Stop-Process
Stops one or more running processes.

```bash
C:\> Stop-Process -Name "Example"
```

### Import-CliXML, Export-CliXML
Imports a CLIXML file and creates corresponding objects in Powershell.
Exports an XML-based representation of an object or objects and stores it in a file.

```bash
C:\> Get-Process | Export-Clixml -Path .\Example.xml
C:\> Import-Clixml -Path .\Example.xml
```

### Get-ADComputer
Gets one or more Active Directory computers.

```bash
C:\> Get-ADComputer -Identity "Example" -Properties *
```

### Select-Object
Select objects or object properties.

```bash
C:\> Get-Process | Select-Object -Property ProcessName
```

### Get-WmiObject
Gets instances of WMI classes or information about available ones.

### Get-EventLog

=========

## Week 3 - Pipeline
Running multiple commands in a "pipeline" ( | ) causes the output of each command to be passed to the next, running each in sequence. It's important to know that any commands placed in parenthesis runs first, and can contain their own pipelines.

## Week 4 - Pipeline, Cont.
