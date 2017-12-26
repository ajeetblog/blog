---
layout: post
title: PowerShell 5 for Ops (Level 100)
description: "PowerShell 5 for Ops"
modified: 2017-10-22
tags: [PowerShell]
categories: [PowerShell]
author: Ajeet
google_analytics:  UA-101864870-1
google_verify: GKeGILLEWvsJwRfdYMqqoMDZKOBZPWIWpHP9K2uIXHI
production: true
---



```PowerShell
class Person {
    [string]$CN
    [string]$Description
    [datetime]$WhenCreated

    [void]Describe([string]$Description){
        $this.Description = $Description
    }

    person([string]$CN) {
        $this.cn = $CN
    }

    person([string]$CN,[string]$Description,[datetime]$whenCreated) {
        $this.CN = $CN
        $This.Description = $Description
        $This.WhenCreated = $whenCreated
    }
}

```

```PowerShell
class Person {
    [string]$CN
    [string]$Description
    [string]$DisplayName

    [void]Describe([string]$Description){
        $this.Description = $Description
    }
}

class User : Person{
    [string]$Name
    [int]$Mailbox
    
    [void]AddUser([string]$Name,[int]$Mailbox) {
        $This.Name = $Name
        $This.Mailbox = $Mailbox
        $Date = Get-Date
        $This.Describe("User created on $($Date)")
        }
    }

class Computer : User{
    [string]$OperatingSystem
    
    [void]AddUser([string]$Name,[int]$OperatingSystem){
        $This.Name = $Name
        $This.OperatingSystem = $OperatingSystem
        $date = get-date
        $This.Describe("Computer created on $($Date)")
        }
    }



```

```PowerShell
# Contents of Harmless-Command.ps1
function Freak {
    
    Start-Process notepad.exe
    start-sleep 1
    get-process -Name notepad | stop-process
    write-output "Freaky"

    }
Freak

#search event log for script block logging
Get-winevent -filterHashTable @{ProviderName = “Microsoft-Windows-PowerShell”;ID=4104} | where-object {$_.Message -like “*Freaky*”} | select-object -expandproperty Message
```
