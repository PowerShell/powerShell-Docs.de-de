---
external help file: PSDiagnostics-help.xml
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/27/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/set-logproperties?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-LogProperties
ms.openlocfilehash: e5d66d628f2240c86c8b94b846b0397d517adf43
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93211695"
---
# Set-LogProperties

## ZUSAMMENFASSUNG
Ändert die Eigenschaften eines Windows-Ereignis Protokolls.

## SYNTAX

```
Set-LogProperties [-LogDetails] <LogDetails> [-Force] [<CommonParameters>]
```

## DESCRIPTION

Dieses Cmdlet ändert die Konfigurationseinstellungen eines Windows-Ereignis Protokolls. Dieses Cmdlet wird von den `Enable-PSTrace` -und- `Disable-PSTrace` Cmdlets verwendet.

Sie müssen dieses Cmdlet aus einer PowerShell-Sitzung mit erhöhten Rechten ausführen.

## BEISPIELE

### Beispiel 1: Ändern der Beibehaltungs Einstellung des Windows PowerShell-Ereignis Protokolls

```powershell
$logDetails = Get-LogProperties 'Windows PowerShell'
$logDetails.Retention = $True
Set-LogProperties -LogDetails $logDetails
Get-LogProperties 'Windows PowerShell'
```

```Output
Name       : Windows PowerShell
Enabled    : True
Type       : Admin
Retention  : True
AutoBackup : False
MaxLogSize : 15728640
```

## PARAMETERS

### -Force

Wird verwendet, um die Änderung ohne Eingabeaufforderung zu erzwingen.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Logdetails

Die aktualisierten Konfigurationseinstellungen, die dem Ereignisprotokoll zugewiesen werden sollen.

```yaml
Type: Microsoft.PowerShell.Diagnostics.LogDetails
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### Microsoft. PowerShell. Diagnostics. Logdetails

Sie müssen ein vollständig konfiguriertes **Logdetails** -Objekt an das `Set-LogProperties` Cmdlet übergeben.
Wenn Sie eine Einstellung ändern möchten, sollten Sie daher zum `Get-LogProperties` Abrufen der aktuellen Konfiguration verwenden.

## AUSGABEN

### Keine

## HINWEISE

Sie müssen dieses Cmdlet aus einer PowerShell-Sitzung mit erhöhten Rechten ausführen.

## VERWANDTE LINKS

[Get-LogProperties](Get-LogProperties.md)

[Enable-PSTrace](Enable-PSTrace.md)

[Disable-PSTrace](Disable-PSTrace.md)

