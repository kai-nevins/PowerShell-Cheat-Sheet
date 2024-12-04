# PowerShell-Cheat-Sheet
`The following document was created for educational use only.`

## Introduction

According to Microsoft, the Powershell program is a command shell, scripting language, and automation platform included in most forms of Microsoft Windows. While not the first language that people think of when discussing scripting, it is nontheless useful when done properly. The program is open-source, and can access other data stores with ease.

This is a document recapping each command learned in the Powershell (COSC-2101-07) course taught at Durham College. Every command listed will be in chronological order, starting from Week 3's lesson. Please note that everything covered in this document is a representation of personal experience, and should not be used as a main reference point; Microsoft itself offers much more detailed explanations for all commands provided.

===================

## Commands

The following is a list of all commands researched and used for the course. Please remember that this is not a perfect encapsulation of everything that the commands can do.

### Import-CSV
### ConvertTo-CSV
### Export-CSV
### Import-CliXML
Creates a table from items in a CSV file.

```bash
Import-Csv -Path .\Examples.csv
```

### Export-CliXML
### Get-Content
Gets the content of the item and the specified location.

```bash
PS C:\> Get-Content -Path .\Example.txt
```

### ConvertTo-HTML
### Out-File

## Week 3 - Pipeline
Running multiple commands in a "pipeline" ( | ) causes the output of each command to be passed to the next, running each in sequence. It's important to know that any commands placed in parenthesis runs first, and can contain their own pipelines.
