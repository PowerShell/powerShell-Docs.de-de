---
external help file: Microsoft.PowerShell.PSReadLine2.dll-Help.xml
Locale: en-US
Module Name: PSReadLine
ms.date: 12/07/2018
online version: https://docs.microsoft.com/powershell/module/psreadline/remove-psreadlinekeyhandler?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-PSReadLineKeyHandler
ms.openlocfilehash: d280eba2e717ccfb0b896d62f42079390d1db848
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599194"
---
# Remove-PSReadLineKeyHandler

## ZUSAMMENFASSUNG
Entfernt eine tastenbindung.

## SYNTAX

```
Remove-PSReadLineKeyHandler [-Chord] <String[]> [-ViMode <ViMode>] [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `Remove-PSReadLineKeyHandler` Cmdlet wird eine angegebene schlüsselbindung entfernt.

## BEISPIELE

### Beispiel 1: Entfernen einer Bindung

```powershell
Remove-PSReadLineKeyHandler -Chord Ctrl+B
```

Mit diesem Befehl wird die Bindung aus der Tastenkombination (oder dem Akkord) entfernt `Ctrl+B` . Der `Ctrl+B` Akkord wird im Artikel erstellt `Set-PSReadLineKeyHandler` .

## PARAMETERS

### -Akkord

Gibt ein Array von Schlüsseln oder Sequenzen von Schlüsseln an, die entfernt werden sollen. Eine einzelne Bindung wird mit einer einzelnen Zeichenfolge angegeben. Wenn die Bindung eine Sequenz von Schlüsseln ist, trennen Sie die Schlüssel durch ein Komma, wie im folgenden Beispiel gezeigt:

`Ctrl+x,Ctrl+l`

Dieser Parameter akzeptiert ein Array von Zeichen folgen. Jede Zeichenfolge ist eine separate Bindung und keine Sequenz von Schlüsseln für eine einzelne Bindung.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Key

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Vimode

Geben Sie den VI-Modus an, für den die Bindung gilt. Mögliche Werte sind: INSERT, Command.

```yaml
Type: Microsoft.PowerShell.ViMode
Parameter Sets: (All)
Aliases:
Accepted values: Insert, Command

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### Keine

Objekte können nicht an dieses Cmdlet weitergereicht werden.

## AUSGABEN

### Keine

## HINWEISE

## VERWANDTE LINKS

[Get-psread linekeyhandler](Get-PSReadLineKeyHandler.md)

[Get-psread lineoption](Get-PSReadLineOption.md)

[Set-psread lineoption](Set-PSReadLineOption.md)

[Set-psread linekeyhandler](Set-PSReadLineKeyHandler.md)

