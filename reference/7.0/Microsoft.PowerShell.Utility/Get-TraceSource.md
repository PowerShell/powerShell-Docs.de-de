---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-tracesource?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-TraceSource
ms.openlocfilehash: 024fa690ff9ddd4eae2d7fd6203e83f56fef6cd7
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93210748"
---
# Get-TraceSource

## ZUSAMMENFASSUNG
Ruft PowerShell-Komponenten ab, die für die Ablauf Verfolgung instrumentiert werden.

## SYNTAX

```
Get-TraceSource [[-Name] <String[]>] [<CommonParameters>]
```

## DESCRIPTION

Das Cmdlet " **Get-TraceSource** " Ruft die Ablauf Verfolgungs Quellen für PowerShell-Komponenten ab, die derzeit verwendet werden.
Sie können die Daten verwenden, um zu bestimmen, welche PowerShell-Komponenten Sie verfolgen können.
Bei der Ablaufverfolgung generiert die Komponente detaillierte Meldungen zu den einzelnen Schritten der internen Verarbeitung.
Entwickler verwenden die Ablaufverfolgungsdaten zur Überwachung des Datenflusses, der Programmausführung und von Fehlern.

Die Cmdlets für die Ablauf Verfolgung wurden für PowerShell-Entwickler entwickelt, sind aber für alle Benutzer verfügbar.

## BEISPIELE

### Beispiel 1: erhalten von Ablauf Verfolgungs Quellen nach Namen

```
PS C:\> Get-TraceSource -Name "*provider*"
```

Mit diesem Befehl werden alle Ablauf Verfolgungs Quellen abgerufen, deren Namen den Anbieter enthalten.

### Beispiel 2: alle Ablauf Verfolgungs Quellen

```
PS C:\> Get-TraceSource
```

Dieser Befehl ruft alle PowerShell-Komponenten ab, die verfolgt werden können.

## PARAMETERS

### -Name

Gibt die abzurufverfolgungs Quellen an.
Platzhalter sind zulässig.
Der Parameter Name *Name* ist optional.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### System.String

Sie können eine Zeichenfolge, die den Namen einer Ablauf Verfolgungs Quelle enthält, über die Pipeline an **Get-TraceSource** übergeben.

## AUSGABEN

### System. Management. Automation. pstracesource

**Get-TraceSource** gibt Objekte zurück, die die Ablauf Verfolgungs Quellen darstellen.

## HINWEISE

## VERWANDTE LINKS

[Set-TraceSource](Set-TraceSource.md)

[Trace-Command](Trace-Command.md)
