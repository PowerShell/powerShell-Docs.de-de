---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
Locale: en-US
Module Name: PackageManagement
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/packagemanagement/get-packageprovider?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PackageProvider
ms.openlocfilehash: fd8325f1a68755ee1b5c05719a04e71b22a7e9fd
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/19/2020
ms.locfileid: "99596152"
---
# Get-PackageProvider

## ZUSAMMENFASSUNG
Gibt eine Liste von Paket Anbietern zurück, die mit Paketverwaltung verbunden sind.

## SYNTAX

```
Get-PackageProvider [[-Name] <String[]>] [-ListAvailable] [-Force] [-ForceBootstrap] [<CommonParameters>]
```

## DESCRIPTION

Das **Get-packageprovider** -Cmdlet gibt eine Liste von Paket Anbietern zurück, die mit Paketverwaltung verbunden sind.
Beispiele für diese Anbieter sind psmodule, nuget und Chocolatey.
Sie können die Ergebnisse auf der Grundlage eines oder mehrerer Anbieter Namen filtern.

## BEISPIELE

### Beispiel 1: alle zurzeit geladenen Paketanbieter

```
PS C:\> Get-PackageProvider
```

Mit diesem Befehl wird eine Liste aller Paketanbieter abgerufen, die zurzeit auf dem lokalen Computer geladen sind.

### Beispiel 2: alle verfügbaren Paketanbieter erhalten

```
PS C:\> Get-PackageProvider -ListAvailable
```

Mit diesem Befehl wird eine Liste aller Paketanbieter abgerufen, die auf dem lokalen Computer verfügbar sind.

### Beispiel 3: Dynamisches erhalten eines Paket Anbieters

```
PS C:\> Get-PackageProvider -Name "Chocolatey" -ForceBootstrap
```

Mit diesem Befehl wird der Chocolatey-Anbieter automatisch installiert, wenn auf dem Computer der Chocolatey-Anbieter nicht installiert ist.

## PARAMETERS

### -Force

Gibt an, dass dieses Cmdlet alle anderen Aktionen mit diesem Cmdlet erzwingt, die erzwungen werden können.
In **Get-packageprovider** bedeutet dies, dass der *Force* -Parameter mit dem Parameter " *forcebootstrap* " identisch ist.

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

### -Forcebootstrap

Gibt an, dass dieses Cmdlet Paketverwaltung zum automatischen Installieren des Paket Anbieters erzwingt.

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

### -Listavailable

Ruft alle installierten Anbieter ab.
**Get-packageprovider** Ruft den Anbieter in Pfaden ab, die in der **psmodulepath** -Umgebungsvariablen aufgeführt sind, sowie die Assemblyordner des Paket Anbieters:

**$ENV:P rogramfiles\packagemanagement\providerassemblys * * * * $ENV: localappdata\packagemanagement\providerassemblys**

Ohne diesen Parameter ruft **Get-packageprovider** nur die Anbieter ab, die in der aktuellen Sitzung geladen wurden.

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

### -Name

Gibt einen oder mehrere Anbieter Namen oder partielle Anbieter Namen an.
Trennen Sie mehrere Anbieter Namen durch Kommas.
Gültige Werte für diesen Parameter sind Namen von Anbietern, die Sie mit Paketen installiert haben. Packagemanagement wird mit einer Reihe von Standard Anbietern ausgeliefert, einschließlich der **psmodule** -und **MSI** -Anbieter.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

## AUSGABEN

### Packageprovider []

## HINWEISE

> [!IMPORTANT]
> Ab April 2020 unterstützt der PowerShell-Katalog die TLS-Versionen (Transport Layer Security) 1.0 und 1.1 nicht mehr. Wenn Sie nicht TLS 1.2 oder höher verwenden, erhalten Sie beim Versuch des Zugriffs auf den PowerShell-Katalog eine Fehlermeldung. Mit dem folgenden Befehl können Sie sicherstellen, dass Sie TLS 1.2 verwenden:
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> Weitere Informationen finden Sie im PowerShell-Blog in der [Ankündigung](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/).

## VERWANDTE LINKS

[about_PackageManagement](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[Get-PackageSource](Get-PackageSource.md)

[Register-PackageSource](Register-PackageSource.md)

[Unregister-PackageSource](Unregister-PackageSource.md)
