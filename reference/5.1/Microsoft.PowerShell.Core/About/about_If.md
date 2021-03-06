---
description: Beschreibt einen Sprachbefehl, den Sie verwenden können, um Anweisungs Listen basierend auf den Ergebnissen von einem oder mehreren bedingten Tests auszuführen.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_if?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_If
ms.openlocfilehash: 8b1be96167dab47e7e15e3e5b89c46126f117541
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93223447"
---
# <a name="about-if"></a>Informationen zu if

## <a name="short-description"></a>KURZE BESCHREIBUNG
Beschreibt einen Sprachbefehl, den Sie verwenden können, um Anweisungs Listen basierend auf den Ergebnissen von einem oder mehreren bedingten Tests auszuführen.

## <a name="long-description"></a>LANGE BESCHREIBUNG
Sie können die- `If` Anweisung verwenden, um Code Blöcke auszuführen, wenn für einen angegebenen bedingten Test true ausgewertet wird. Sie können auch einen oder mehrere zusätzliche bedingte Tests angeben, die ausgeführt werden sollen, wenn alle vorherigen Tests als false ausgewertet werden. Schließlich können Sie einen zusätzlichen Codeblock angeben, der ausgeführt wird, wenn kein anderer vorheriger bedingter Test zu true ausgewertet wird.

### <a name="syntax"></a>Syntax

Das folgende Beispiel zeigt die `If` Syntax der Anweisung:

```powershell
if (<test1>)
    {<statement list 1>}
[elseif (<test2>)
    {<statement list 2>}]
[else
    {<statement list 3>}]
```

Wenn Sie eine- `If` Anweisung ausführen, wertet PowerShell den `<test1>` bedingten Ausdruck als "true" oder "false" aus. Wenn `<test1>` true ist, wird ausgeführt `<statement list 1>` , und PowerShell beendet die- `If` Anweisung. Wenn `<test1>` den Wert false hat, wertet PowerShell die durch die `<test2>` bedingte Anweisung angegebene Bedingung aus.

Wenn `<test2>` true ist, wird ausgeführt `<statement list 2>` , und PowerShell beendet die- `If` Anweisung. Wenn sowohl `<test1>` als auch als `<test2>` false ausgewertet wird, wird der `<statement list 3`> Codeblock ausgeführt, und PowerShell beendet die if-Anweisung.

Sie können mehrere ElseIf-Anweisungen verwenden, um eine Reihe von bedingten Tests zu verketten. Daher wird jeder Test nur ausgeführt, wenn alle vorherigen Tests false sind.
Wenn Sie eine-Anweisung erstellen müssen, `If` die viele ElseIf-Anweisungen enthält, sollten Sie stattdessen eine Switch-Anweisung verwenden.

Beispiele:

Die einfachste `If` Anweisung enthält einen einzelnen Befehl, der keine ElseIf-Anweisungen oder andere Anweisungen enthält. Das folgende Beispiel zeigt die einfachste Form der- `If` Anweisung:

```powershell
if ($a -gt 2) {
    Write-Host "The value $a is greater than 2."
}
```

Wenn die $a Variable in diesem Beispiel größer als 2 ist, wird die Bedingung als "true" ausgewertet, und die Anweisungs Liste wird ausgeführt. Wenn $a jedoch kleiner oder gleich 2 ist oder keine vorhandene Variable ist, `If` zeigt die Anweisung keine Meldung an.

Wenn eine Else-Anweisung hinzugefügt wird, wird eine Meldung angezeigt, wenn $a kleiner oder gleich 2 ist. Das nächste Beispiel zeigt Folgendes:

```powershell
if ($a -gt 2) {
    Write-Host "The value $a is greater than 2."
}
else {
    Write-Host ("The value $a is less than or equal to 2," +
        " is not created or is not initialized.")
}
```

Zum weiteren verfeinern dieses Beispiels können Sie die ElseIf-Anweisung verwenden, um eine Meldung anzuzeigen, wenn der Wert von $a gleich 2 ist. Das nächste Beispiel zeigt Folgendes:

```powershell
if ($a -gt 2) {
    Write-Host "The value $a is greater than 2."
}
elseif ($a -eq 2) {
    Write-Host "The value $a is equal to 2."
}
else {
    Write-Host ("The value $a is less than 2 or" +
        " was not created or initialized.")
}
```

## <a name="see-also"></a>SIEHE AUCH

[about_Comparison_Operators](about_Comparison_Operators.md)

[about_Switch](about_Switch.md)
