---
ms.date: 01/02/2020
title: Verwenden des Konsolenbereichs in der Windows PowerShell ISE
description: Verwenden des Konsolenbereichs in der Windows PowerShell ISE
ms.openlocfilehash: 7f6d3f5a3e4e596beb0d5c0bc395e3e7bf39906d
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92663668"
---
# <a name="how-to-use-the-console-pane-in-the-windows-powershell-ise"></a>Verwenden des Konsolenbereichs in der Windows PowerShell ISE

Der Konsolenbereich in Windows PowerShell Integrated Scripting Environment (ISE) funktioniert genauso wie das eigenständige Windows PowerShell ISE-Konsolenfenster.

Um einen Befehl im Konsolenbereich auszuführen, geben Sie einen Befehl ein und drücken dann die <kbd>EINGABETASTE</kbd>. Um mehrere Befehle einzugeben, die nacheinander ausgeführt werden sollen, drücken Sie <kbd>UMSCHALT</kbd>+<kbd>EINGABETASTE</kbd> zwischen den Befehlen. Hilfe zum Eingeben von Befehlen finden Sie unter [Verwenden von Vervollständigung mit der TAB-TASTE im Skriptbereich und Konsolenbereich](How-to-Use-Tab-Completion-in-the-Script-Pane-and-Console-Pane.md).

Um einen Befehl zu beenden, klicken Sie auf der Symbolleiste auf **Vorgang beenden** , oder drücken Sie <kbd>STRG</kbd>+<kbd>UNTBR</kbd>. Sie können auch <kbd>STRG</kbd>+<kbd>C</kbd> verwenden, um einen Befehl zu beenden, sofern der Kontext eindeutig ist. Wenn im aktuellen Bereich beispielsweise Text ausgewählt ist,wird <kbd>STRG</kbd>+<kbd>C</kbd> dem Kopiervorgang zugeordnet.

Seit Windows PowerShell Version 3 ist der Ausgabebereich mit dem Konsolenbereich kombiniert. Dies hat den Vorteil, dass sich das System wie die eigenständige Windows PowerShell-Konsole verhält, und beseitigt die Unterschiede in den Vorgehensweisen, die erforderlich waren, als die Bereiche getrennt waren. Ihre Möglichkeiten:

- Markieren von Text im Konsolenbereich und Kopieren des markierten Texts in die Zwischenablage, um ihn in einem anderen Fenster einzufügen. Um Text zu markieren, ziehen Sie mit der Maus bei gedrückter linker Maustaste über den Text, den Sie erfassen möchten. Sie können Text auch markieren, indem Sie bei gedrückter <kbd>UMSCHALTTASTE</kbd> die Cursortasten verwenden. Drücken Sie dann <kbd>STRG</kbd>+<kbd>C</kbd>, oder klicken Sie auf der Symbolleiste auf das Symbol **Kopieren** .

- Einfügen des markierten Texts an der aktuellen Cursorposition. Klicken Sie auf der Symbolleiste auf das Symbol **Einfügen** .

- Löschen des gesamten Texts im Konsolenbereich. Sie können auf der Symbolleiste auf das Symbol **Konsolenbereich löschen** klicken, oder Sie führen den Befehl `Clear-Host` oder dessen Alias `cls` aus, um den Konsolenbereich zu löschen.

## <a name="see-also"></a>Weitere Informationen

- [Einführung in die Windows PowerShell ISE](Introducing-the-Windows-PowerShell-ISE.md)
