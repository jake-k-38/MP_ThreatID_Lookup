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
or
```
.\ThreatID_Lookup.ps1 2147519003 id2 id3
```
```
Do you want to export the threat catalog data to CSV? (Yes/No): no
Using existing 'threatCatalog.csv' for lookup.
Loading data from 'threatCatalog.csv'...
Loaded 327919 records from 'threatCatalog.csv'.
Data has been loaded into the table called 'threatCatalog' (structured by ThreatID)...
Enter a list of ThreatIDs you want to search for (comma-separated): 2147519003, 2147519004, 2147765896
Searching for ThreatID: 2147519003

Found ThreatID: 2147519003
Name: Virus:DOS/EICAR_Test_File
Severity: 5
Category ID: 42

Searching for ThreatID: 2147519004

ThreatID 2147519004 not found in the catalog.

Searching for ThreatID: 2147765896

Found ThreatID: 2147765896
Name: Trojan:Win32/PswStealer!MSR
Severity: 5
Category ID: 8
```

```
.\ThreatID_Lookup.ps1 2147519003 2147812351
Using provided ThreatID(s): 2147519003,2147812351
Using existing 'threatCatalog.csv' for lookup.
Loading data from 'threatCatalog.csv'...
Loaded 327919 records from 'threatCatalog.csv'.
Data has been loaded into the table called 'threatCatalog' (structured by ThreatID)...
Searching for ThreatID: 2147519003

Found ThreatID: 2147519003
Name: Virus:DOS/EICAR_Test_File
Severity: 5
Category ID: 42

Searching for ThreatID: 2147812351

Found ThreatID: 2147812351
Name: Behavior:Win32/DumpLsass.C!attk
Severity: 5
Category ID: 46

Do you want to search for another set of ThreatIDs? (Yes/No): yes
Enter a list of ThreatIDs you want to search for (comma-separated): 224688,2147828166
Searching for ThreatID: 224688

Found ThreatID: 224688
Name: PUA:Win32/EICAR_Test_File
Severity: 1
Category ID: 27

Searching for ThreatID: 2147828166

Found ThreatID: 2147828166
Name: Trojan:Win32/Leonem
Severity: 5
Category ID: 8

Do you want to search for another set of ThreatIDs? (Yes/No): no
Exit loop, Goodbye!
```
