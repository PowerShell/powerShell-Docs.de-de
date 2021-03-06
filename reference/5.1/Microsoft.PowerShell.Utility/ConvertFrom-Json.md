---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/10/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertfrom-json?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertFrom-Json
ms.openlocfilehash: e1bab9250269dadf0d899f9e172e8a4a8387271d
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2020
ms.locfileid: "94388126"
---
# ConvertFrom-Json

## ZUSAMMENFASSUNG
Konvertiert eine JSON-formatierte Zeichenfolge in ein benutzerdefiniertes Objekt.

## SYNTAX

```
ConvertFrom-Json [-InputObject] <String> [<CommonParameters>]
```

## DESCRIPTION

Das `ConvertFrom-Json` Cmdlet konvertiert eine JavaScript Object Notation (JSON) formatierte Zeichenfolge in ein benutzerdefiniertes **pscustomobject** -Objekt, das über eine Eigenschaft für jedes Feld in der JSON-Zeichenfolge verfügt. JSON wird häufig von Websites verwendet, um eine Textdarstellung der Objekte bereitzustellen. Der JSON-Standard unterstützt nicht die Verwendung, die für ein **pscustomobject** unzulässig ist. Wenn die JSON-Zeichenfolge z. b. doppelte Schlüssel enthält, wird nur der letzte Schlüssel von diesem Cmdlet verwendet. Weitere Beispiele finden Sie weiter unten.

Verwenden Sie das-Cmdlet, um eine JSON-Zeichenfolge aus einem beliebigen Objekt zu generieren `ConvertTo-Json` .

Dieses Cmdlet wurde in PowerShell 3,0 eingeführt.

> [!NOTE]
> Dieses Cmdlet unterstützt JSON nicht mit Kommentaren.

## BEISPIELE

### Beispiel 1: Konvertieren eines DateTime-Objekts in ein JSON-Objekt

Dieser Befehl verwendet die `ConvertTo-Json` `ConvertFrom-Json` Cmdlets und, um ein **DateTime** -Objekt aus dem `Get-Date` Cmdlet in ein JSON-Objekt in ein **pscustomobject** -Objekt zu konvertieren.

```powershell
Get-Date | Select-Object -Property * | ConvertTo-Json | ConvertFrom-Json
```

```Output
DisplayHint : 2
DateTime    : Friday, January 13, 2012 8:06:31 PM
Date        : 1/13/2012 8:00:00 AM
Day         : 13
DayOfWeek   : 5
DayOfYear   : 13
Hour        : 20
Kind        : 2
Millisecond : 400
Minute      : 6
Month       : 1
Second      : 31
Ticks       : 634620819914009002
TimeOfDay   : @{Ticks=723914009002; Days=0; Hours=20; Milliseconds=400; Minutes=6; Seconds=31; TotalDays=0.83786343634490734; TotalHours=20.108722472277776; TotalMilliseconds=72391400.900200009; TotalMinutes=1206.5233483366667;TotalSeconds=72391.4009002}
Year        : 2012
```

Im Beispiel wird das- `Select-Object` Cmdlet verwendet, um alle Eigenschaften des **DateTime** -Objekts zu erhalten. Er verwendet das `ConvertTo-Json` Cmdlet, um das **DateTime** -Objekt in eine Zeichenfolge zu konvertieren, die als JSON-Objekt formatiert ist, und das `ConvertFrom-Json` Cmdlet zum Konvertieren der JSON-formatierten Zeichenfolge in ein **pscustomobject** -Objekt.

### Beispiel 2: erhalten von JSON-Zeichen folgen aus einem Webdienst und Konvertieren der Zeichen folgen in PowerShell-Objekte

Dieser Befehl verwendet das `Invoke-WebRequest` Cmdlet, um JSON-Zeichen folgen von einem Webdienst zu erhalten, und verwendet dann das `ConvertFrom-Json` Cmdlet, um JSON-Inhalte in Objekte zu konvertieren, die in PowerShell verwaltet werden können.

```powershell
# Ensures that Invoke-WebRequest uses TLS 1.2
[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12
$j = Invoke-WebRequest 'https://api.github.com/repos/PowerShell/PowerShell/issues' | ConvertFrom-Json
```

Sie können auch das- `Invoke-RestMethod` Cmdlet verwenden, mit dem JSON-Inhalte automatisch in-Objekte konvertiert werden.

### Beispiel 3: Konvertieren einer JSON-Zeichenfolge in ein benutzerdefiniertes Objekt

Dieses Beispiel zeigt, wie Sie mit dem `ConvertFrom-Json` Cmdlet eine JSON-Datei in ein benutzerdefiniertes PowerShell-Objekt konvertieren.

```powershell
Get-Content JsonFile.JSON | ConvertFrom-Json
```

Der Befehl verwendet Get-Content Cmdlet, um die Zeichen folgen in einer JSON-Datei zu erhalten. Anschließend wird der Pipeline Operator verwendet, um die durch Trennzeichen getrennte Zeichenfolge an das- `ConvertFrom-Json` Cmdlet zu senden, das Sie in ein benutzerdefiniertes-Objekt konvertiert.

## PARAMETERS

### -InputObject

Gibt die JSON-Zeichenfolgen an, die in JSON-Objekte konvertiert werden sollen. Geben Sie eine Variable ein, die die Zeichenfolge enthält, oder geben Sie einen Befehl oder Ausdruck ein, der die Zeichenfolge abruft. Sie können eine Zeichenfolge auch über die Pipeline an senden `ConvertFrom-Json` .

Der **InputObject** -Parameter ist erforderlich, sein Wert kann jedoch eine leere Zeichenfolge sein. Wenn das Eingabe Objekt eine leere Zeichenfolge ist, `ConvertFrom-Json` generiert keine Ausgabe. Der **Inputobject** -Wert darf nicht sein `$null` .

```yaml
Type: System.String
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

### System.String

Sie können eine JSON-Zeichenfolge an übergeben `ConvertFrom-Json` .

## AUSGABEN

### PSCustomObject

## HINWEISE

Das `ConvertFrom-Json` Cmdlet wird mithilfe der [JavaScriptSerializer-Klasse](/dotnet/api/system.web.script.serialization.javascriptserializer)implementiert.

## VERWANDTE LINKS

[Eine Einführung in JavaScript Object Notation (JSON) in JavaScript und .net](/previous-versions/dotnet/articles/bb299886(v=msdn.10))

[ConvertTo-Json](ConvertTo-Json.md)

[Invoke-WebRequest](Invoke-WebRequest.md)

[Invoke-RestMethod](Invoke-RestMethod.md)
