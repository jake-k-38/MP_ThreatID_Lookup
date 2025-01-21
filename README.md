# MpThreatCatalog-lookup
PowerShell script optimized to quickly search the catalog for a specified ThreatID by saving it as a CSV file on the local system. 

https://learn.microsoft.com/en-us/powershell/module/defender/get-mpthreatcatalog?view=windowsserver2022-ps

## Table of contents
* [General info](#general-info)
* [Getting started](#getting-started)
* [Usage](#usage)

## General info
While the built-in Get-MpThreatCatalog -ThreatID <id> command is available, it lacks performance, particularly when multiple ThreatIDs need to be researched rapidly. The script offers faster lookups compared to the default Get-MpThreatCatalog -ThreatID <id> command, making it ideal for consecutive ThreatID queries.
	
## Getting started
Users may need to change the default PowerShell execution policy. This can be achieved in a number of different ways:<br />

Open a command prompt and run ```powershell.exe -ExecutionPolicy Unrestricted``` and run scripts from that PowerShell session.<br />
Open a PowerShell prompt and run ```Set-ExecutionPolicy Unrestricted -Scope Process``` and run scripts from the current PowerShell session.<br />
Open an administrative PowerShell prompt and run ```Set-ExecutionPolicy Unrestricted``` and run scripts from any PowerShell session.<br />

## Usage
Simply just run the script ThreatID_Lookup.ps1 to start the script
```
.\ThreatID_Lookup.ps1
```
```
Do you want to export the threat catalog data to CSV? (Yes/No): yes
Exporting data to CSV...
Data has been exported to 'threatCatalog.csv'.
Loading data from 'threatCatalog.csv'...
Loaded 327919 records from 'threatCatalog.csv'.
Data has been loaded into the table called, threatCatalog(structed by ThreatID)...
Enter the ThreatID you want to search for: 2147765896
Searching for ThreatID: 2147765896
Found ThreatID: 2147765896
Name: Trojan:Win32/PswStealer!MSR
Severity: 5
Do you want to search for another ThreatID? (Yes/No):
```
