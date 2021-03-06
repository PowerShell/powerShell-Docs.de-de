---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 05/20/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-hotfix?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-HotFix
ms.openlocfilehash: cb0fb1a6d7de033438c3165d44d5b8f8c03ba9a4
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2020
ms.locfileid: "94342993"
---
# Get-HotFix

## ZUSAMMENFASSUNG
Ruft die Hotfixes ab, die auf lokalen Computern oder Remote Computern installiert sind.

## SYNTAX

### Standard (Standard)

```
Get-HotFix [[-Id] <String[]>] [-ComputerName <String[]>] [-Credential <PSCredential>]
[<CommonParameters>]
```

### BESCHREIBUNG

```
Get-HotFix [-Description <String[]>] [-ComputerName <String[]>] [-Credential <PSCredential>]
[<CommonParameters>]
```

## DESCRIPTION

Das- `Get-Hotfix` Cmdlet ruft Hotfixes oder Updates ab, die auf dem lokalen Computer oder den angegebenen Remote Computern installiert sind. Die Updates können Windows Update, Microsoft Update, Windows Server Update Services oder manuell installiert werden.

## BEISPIELE

### Beispiel 1: alle Hotfixes auf dem lokalen Computer

Mit dem- `Get-Hotfix` Cmdlet werden alle auf dem lokalen Computer installierten Hotfixes abgerufen.

```powershell
Get-HotFix
```

```output
Source         Description      HotFixID      InstalledBy          InstalledOn
------         -----------      --------      -----------          -----------
Server01       Update           KB4495590     NT AUTHORITY\SYSTEM  5/16/2019 00:00:00
Server01       Security Update  KB4470788     NT AUTHORITY\SYSTEM  1/22/2019 00:00:00
Server01       Update           KB4480056     NT AUTHORITY\SYSTEM  1/24/2019 00:00:00
```

### Beispiel 2: erhalten von Hotfixes von mehreren Computern, die nach einer Zeichenfolge gefiltert sind

Der `Get-Hotfix` Befehl verwendet Parameter, um Hotfixes auf Remote Computern zu installieren. Die Ergebnisse werden anhand einer angegebenen Beschreibungs Zeichenfolge gefiltert.

```
PS> Get-HotFix -Description Security* -ComputerName Server01, Server02 -Credential Domain01\admin01
```

`Get-Hotfix` filtert die Ausgabe mit dem **Beschreibungs** Parameter und der Zeichen folgen **Sicherheit** , die das Sternchen-Platzhalter Zeichen ( `*` ) enthält. Der **Computername** -Parameter enthält eine durch Trennzeichen getrennte Zeichenfolge von Remote Computernamen. Der **Credential** -Parameter gibt ein Benutzerkonto an, das über die Berechtigung zum Zugreifen auf die Remote Computer und zum Ausführen von Befehlen verfügt.

### Beispiel 3: überprüfen, ob ein Update installiert ist, und Schreiben von Computernamen in eine Datei

Mit den Befehlen in diesem Beispiel wird überprüft, ob ein bestimmtes Update installiert ist. Wenn das Update nicht installiert ist, wird der Computername in eine Textdatei geschrieben.

```
PS> $A = Get-Content -Path ./Servers.txt
PS> $A | ForEach-Object { if (!(Get-HotFix -Id KB957095 -ComputerName $_))
         { Add-Content $_ -Path ./Missing-KB957095.txt }}
```

Die- `$A` Variable enthält Computernamen, die von `Get-Content` aus einer Textdatei abgerufen wurden. Die Objekte in `$A` werden über die Pipeline an gesendet `ForEach-Object` . Eine `if` -Anweisung verwendet das `Get-Hotfix` -Cmdlet mit dem **ID** -Parameter und eine bestimmte ID-Nummer für jeden Computernamen. Wenn auf einem Computer die angegebene HotFixID nicht installiert ist, `Add-Content` schreibt das Cmdlet den Computernamen in eine Datei.

### Beispiel 4: Holen Sie sich den neuesten Hotfix auf dem lokalen Computer

In diesem Beispiel wird der aktuelle Hotfix abgerufen, der auf einem Computer installiert ist.

```powershell
(Get-HotFix | Sort-Object -Property InstalledOn)[-1]
```

`Get-Hotfix` sendet die Objekte in der Pipeline an das `Sort-Object` Cmdlet. `Sort-Object` sortiert Objekte in aufsteigender Reihenfolge und verwendet den **Property** -Parameter zum Auswerten der einzelnen **installedon** -Datumsangaben. Die Array Notation `[-1]` wählt den neuesten installierten Hotfix aus.

## PARAMETERS

### -ComputerName

Gibt einen Remotecomputer an. Geben Sie den NetBIOS-Namen, eine IP-Adresse oder einen voll qualifizierten Domänen Namen (Fully Qualified Domain Name, FQDN) eines Remote Computers ein.

Wenn der **Computername** -Parameter nicht angegeben wird, wird `Get-Hotfix` auf dem lokalen Computer ausgeführt.

Der **Computername** -Parameter beruht nicht auf Windows PowerShell-Remoting. Wenn Ihr Computer nicht für das Ausführen von Remote Befehlen konfiguriert ist, verwenden Sie den **Computername** -Parameter.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: CN, __Server, IPAddress

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Credential

Gibt ein Benutzerkonto an, das über die Berechtigung zum Zugreifen auf den Computer und zum Ausführen von Befehlen verfügt. Der Standardwert ist der aktuelle Benutzer.

Geben Sie einen Benutzernamen ein, z. b. **USER01** oder **Domain01\User01** , oder geben Sie ein **PSCredential** -Objekt ein, das vom `Get-Credential` Cmdlet generiert wurde. Wenn Sie einen Benutzernamen eingeben, werden Sie zur Eingabe des Kennworts aufgefordert.

Anmelde Informationen werden in einem [PSCredential](/dotnet/api/system.management.automation.pscredential) -Objekt gespeichert, und das Kennwort wird als [SecureString](/dotnet/api/system.security.securestring)gespeichert.

> [!NOTE]
> Weitere Informationen zum Schutz von **SecureString** -Daten finden Sie unter [wie sicher ist SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### -Description

`Get-HotFix` verwendet den **Description** -Parameter, um hotfixtypen anzugeben. Platzhalter sind zulässig.

```yaml
Type: System.String[]
Parameter Sets: Description
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Id

Filtert die `Get-HotFix` Ergebnisse für bestimmte HotfixIDs. Platzhalter werden nicht akzeptiert.

```yaml
Type: System.String[]
Parameter Sets: Default
Aliases: HFID

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### String

Sie können einen oder mehrere Computernamen über die Pipeline an Get-Hotfix übergeben.

## AUSGABEN

### System. Management. ManagementObject # root\cimv2\ Win32_QuickFixEngineering

`Get-HotFix` gibt-Objekte zurück, die die Hotfixes auf dem Computer darstellen.

## HINWEISE

Dieses Cmdlet ist nur auf Windows-Plattformen verfügbar.

Die **Win32_QuickFixEngineering** [WMI-Klasse](/windows/desktop/WmiSdk/retrieving-a-class) stellt ein kleines systemweites Update dar, das auf das aktuelle Betriebssystem häufig als Update für die schnelle Korrektur Technik (Quick fixengineering, QFE) bezeichnet wird. Diese Klasse gibt nur die von der komponentenbasierten Wartung (Component based Wartung, CBS) bereitgestellten Updates zurück. Diese Updates sind nicht in der Registrierung aufgeführt. Von der Microsoft Windows Installer (MSI) oder der [Windows Update](https://update.microsoft.com) Site bereitgestellte Updates werden von **Win32_QuickFixEngineering** nicht zurückgegeben. Weitere Informationen finden Sie unter [Win32_QuickFixEngineering-Klasse](/windows/desktop/CIMWin32Prov/win32-quickfixengineering).

Die `Get-HotFix` Ausgabe kann sich je nach Betriebssystem unterscheiden.

## VERWANDTE LINKS

[about_Arrays](../Microsoft.PowerShell.Core/About/about_Arrays.md)

[Add-Content](Add-Content.md)

[Get-ComputerRestorePoint](Get-ComputerRestorePoint.md)

[Get-Credential](../Microsoft.PowerShell.Security/Get-Credential.md)

[Win32_QuickFixEngineering-Klasse](/windows/desktop/CIMWin32Prov/win32-quickfixengineering)
