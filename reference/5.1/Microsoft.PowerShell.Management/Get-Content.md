---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 04/23/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-content?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Content
ms.openlocfilehash: e2b78a2062ac551b76c0a1b6b31d721bfefcf3bd
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215471"
---
# Get-Content

## ZUSAMMENFASSUNG
Ruft den Inhalt des Elements am angegebenen Speicherort ab.

## SYNTAX

### Pfad (Standard)

```
Get-Content [-ReadCount <Int64>] [-TotalCount <Int64>] [-Tail <Int32>] [-Path] <String[]>
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Force] [-Credential <PSCredential>]
 [-UseTransaction] [-Delimiter <String>] [-Wait] [-Raw]
 [-Encoding <FileSystemCmdletProviderEncoding>] [-Stream <String>] [<CommonParameters>]
```

### LiteralPath

```
Get-Content [-ReadCount <Int64>] [-TotalCount <Int64>] [-Tail <Int32>] -LiteralPath <String[]>
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Force] [-Credential <PSCredential>]
 [-UseTransaction] [-Delimiter <String>] [-Wait] [-Raw]
 [-Encoding <FileSystemCmdletProviderEncoding>] [-Stream <String>] [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `Get-Content` Cmdlet wird der Inhalt des Elements an dem durch den Pfad angegebenen Speicherort abgerufen, z. b. der Text in einer Datei oder der Inhalt einer Funktion. Bei Dateien wird der Inhalt zeilenweise gelesen und gibt eine Auflistung von-Objekten zurück, die jeweils eine Zeile von Inhalten darstellen.

Ab PowerShell 3,0 `Get-Content` kann auch eine angegebene Anzahl von Zeilen vom Anfang oder Ende eines Elements erhalten.

## BEISPIELE

### Beispiel 1: erhalten des Inhalts einer Textdatei

In diesem Beispiel wird der Inhalt einer Datei im aktuellen Verzeichnis abgerufen. Die `LineNumbers.txt` Datei enthält 100 Zeilen im Format, d. h. **Zeile X** und wird in mehreren Beispielen verwendet.

```powershell
1..100 | ForEach-Object { Add-Content -Path .\LineNumbers.txt -Value "This is line $_." }
Get-Content -Path .\LineNumbers.txt
```

```Output
This is Line 1
This is Line 2
...
This is line 99.
This is line 100.
```

Die Array Werte 1-100 werden über die Pipeline an das `ForEach-Object` Cmdlet gesendet. `ForEach-Object` verwendet einen Skriptblock mit dem- `Add-Content` Cmdlet, um die Datei zu erstellen `LineNumbers.txt` . Die-Variable `$_` stellt die Array Werte dar, wenn jedes Objekt in der Pipeline gesendet wird. Das `Get-Content` Cmdlet verwendet den **path** -Parameter, um die Datei anzugeben, `LineNumbers.txt` und zeigt den Inhalt in der PowerShell-Konsole an.

### Beispiel 2: Begrenzen der Anzahl der Zeilen Get-Content die zurückgibt

Mit diesem Befehl werden die ersten fünf Zeilen einer Datei abgerufen. Der **Total count** -Parameter wird verwendet, um die ersten fünf Inhalts Zeilen zu erhalten. In diesem Beispiel wird die `LineNumbers.txt` Datei verwendet, die in Beispiel 1 erstellt wurde.

```powershell
Get-Content -Path .\LineNumbers.txt -TotalCount 5
```

```Output
This is Line 1
This is Line 2
This is Line 3
This is Line 4
This is Line 5
```

### Beispiel 3: beziehen einer bestimmten Inhalts Zeile aus einer Textdatei

Mit diesem Befehl wird eine bestimmte Anzahl von Zeilen aus einer Datei abgerufen, und dann wird nur die letzte Zeile dieses Inhalts angezeigt. Der **Total count** -Parameter ruft die ersten 25 Inhalts Zeilen ab. In diesem Beispiel wird die `LineNumbers.txt` Datei verwendet, die in Beispiel 1 erstellt wurde.

```powershell
(Get-Content -Path .\LineNumbers.txt -TotalCount 25)[-1]
```

```Output
This is Line 25
```

Der `Get-Content` Befehl wird in Klammern eingeschlossen, sodass der Befehl abgeschlossen ist, bevor er mit dem nächsten Schritt fortfahren kann. `Get-Content`Gibt ein Array von Zeilen zurück. Dadurch können Sie die Index Notation hinter der Klammer hinzufügen, um eine bestimmte Zeilennummer abzurufen. In diesem Fall gibt der `[-1]` Index den letzten Index im zurückgegebenen Array von 25 abgerufenen Zeilen an.

### Beispiel 4: erhalten der letzten Zeile einer Textdatei

Mit diesem Befehl werden die erste Zeile und die letzte Zeile des Inhalts aus einer Datei abgerufen. In diesem Beispiel wird die `LineNumbers.txt` Datei verwendet, die in Beispiel 1 erstellt wurde.

```powershell
Get-Item -Path .\LineNumbers.txt | Get-Content -Tail 1
```

```Output
This is Line 100
```

In diesem Beispiel wird das- `Get-Item` Cmdlet verwendet, um zu veranschaulichen, dass Sie Dateien an den- `Get-Content` Parameter übergeben können. Mit dem **Tail** -Parameter wird die letzte Zeile der Datei abgerufen. Diese Methode ist schneller als das Abrufen aller Zeilen und die Verwendung der `[-1]` Index Notation.

### Beispiel 5: erhalten des Inhalts eines alternativen Datenstroms

In diesem Beispiel wird beschrieben, wie der **Stream** -Parameter verwendet wird, um den Inhalt eines alternativen Datenstroms für Dateien zu erhalten, die auf einem Windows NTFS-Volume gespeichert sind. In diesem Beispiel wird das- `Set-Content` Cmdlet zum Erstellen von Beispiel Inhalt in einer Datei namens verwendet `Stream.txt` .

```powershell
Set-Content -Path .\Stream.txt -Value 'This is the content of the Stream.txt file'
# Specify a wildcard to the Stream parameter to display all streams of the recently created file.
Get-Item -Path .\Stream.txt -Stream *
```

```Output
PSPath        : Microsoft.PowerShell.Core\FileSystem::C:\Test\Stream.txt::$DATA
PSParentPath  : Microsoft.PowerShell.Core\FileSystem::C:\Test
PSChildName   : Stream.txt::$DATA
PSDrive       : C
PSProvider    : Microsoft.PowerShell.Core\FileSystem
PSIsContainer : False
FileName      : C:\Test\Stream.txt
Stream        : :$DATA
Length        : 44
```

```powershell
# Retrieve the content of the primary, or $DATA stream.
Get-Content -Path .\Stream.txt -Stream $DATA
```

```Output
This is the content of the Stream.txt file
```

```powershell
# Use the Stream parameter of Add-Content to create a new Stream containing sample content.
Add-Content -Path .\Stream.txt -Stream NewStream -Value 'Added a stream named NewStream to Stream.txt'
# Use Get-Item to verify the stream was created.
Get-Item -Path .\Stream.txt -Stream *
```

```Output
PSPath        : Microsoft.PowerShell.Core\FileSystem::C:\Test\Stream.txt::$DATA
PSParentPath  : Microsoft.PowerShell.Core\FileSystem::C:\Test
PSChildName   : Stream.txt::$DATA
PSDrive       : C
PSProvider    : Microsoft.PowerShell.Core\FileSystem
PSIsContainer : False
FileName      : C:\Test\Stream.txt
Stream        : :$DATA
Length        : 44

PSPath        : Microsoft.PowerShell.Core\FileSystem::C:\Test\Stream.txt:NewStream
PSParentPath  : Microsoft.PowerShell.Core\FileSystem::C:\Test
PSChildName   : Stream.txt:NewStream
PSDrive       : C
PSProvider    : Microsoft.PowerShell.Core\FileSystem
PSIsContainer : False
FileName      : C:\Test\Stream.txt
Stream        : NewStream
Length        : 46
```

```powershell
# Retrieve the content of your newly created Stream.
Get-Content -Path .\Stream.txt -Stream NewStream
```

```Output
Added a stream named NewStream to Stream.txt
```

Der **Stream** -Parameter ist ein dynamischer Parameter des [File System-Anbieters](../microsoft.powershell.core/about/about_filesystem_provider.md#stream-systemstring).
Standardmäßig `Get-Content` werden nur Daten aus dem primären oder dem `$DATA` Stream abgerufen. **Streams** können zum Speichern ausgeblendeter Daten verwendet werden, wie z. b. Attribute, Sicherheitseinstellungen oder andere Daten.

### Beispiel 6: erhalten von Rohdaten

Mit den Befehlen in diesem Beispiel wird der Inhalt einer Datei als eine Zeichenfolge anstelle eines Arrays von Zeichen folgen angezeigt. Standardmäßig wird der Inhalt **ohne den** unformatierten dynamischen Parameter als Array von Zeichen folgen mit Zeilen Trennzeichen zurückgegeben. In diesem Beispiel wird die `LineNumbers.txt` Datei verwendet, die im Beispiel erstellt wurde.
1.

```powershell
$raw = Get-Content -Path .\LineNumbers.txt -Raw
$lines = Get-Content -Path .\LineNumbers.txt
Write-Host "Raw contains $($raw.Count) lines."
Write-Host "Lines contains $($lines.Count) lines."
```

```Output
Raw contains 1 lines.
Lines contains 100 lines.
```

### Beispiel 7: Verwenden von Filtern mit Get-Content

Sie können einen Filter für das `Get-Content` Cmdlet angeben. Wenn Sie den **path** -Parameter mithilfe von Filtern qualifizieren, müssen Sie ein nach gestelltes Sternchen () einfügen, `*` um den Inhalt des Pfads anzugeben.

Mit dem folgenden Befehl wird der Inhalt aller `*.log` Dateien im `C:\Temp` Verzeichnis abgerufen.

```powershell
Get-Content -Path C:\Temp\* -Filter *.log
```

### Beispiel 8: Dateiinhalte als Bytearray

In diesem Beispiel wird veranschaulicht, wie Sie den Inhalt einer Datei als ein `[byte[]]` einzelnes Objekt als ein einzelnes Objekt erhalten.

```powershell
$byteArray = Get-Content -Path C:\temp\test.txt -Encoding Byte -Raw
Get-Member -InputObject $bytearray
```

```Output
   TypeName: System.Byte[]

Name           MemberType            Definition
----           ----------            ----------
Count          AliasProperty         Count = Length
Add            Method                int IList.Add(System.Object value)
```

Der erste Befehl verwendet den **Encoding** -Parameter, um den Stream von Bytes aus der Datei zu erhalten.
Der **RAW** -Parameter stellt sicher, dass die Bytes als zurückgegeben werden `[System.Byte[]]` . Wenn der **RAW** -Parameter nicht vorhanden ist, ist der Rückgabewert ein Bytestream, der von PowerShell als interpretiert wird `[System.Object[]]` .

## PARAMETERS

### -Path

Gibt den Pfad zu einem Element an, in dem `Get-Content` der Inhalt abgerufen wird. Platzhalterzeichen sind zulässig. Die Pfade müssen auf Elemente und nicht auf Container zeigen. Sie müssen beispielsweise einen Pfad zu Dateien angeben, ein Pfad zu einem Verzeichnis ist nicht zulässig.

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -Literalpath

Gibt einen Pfad zu einem oder mehreren Speicherorten an. Der Wert von **literalpath** wird genau so verwendet, wie er eingegeben wurde. Es werden keine Zeichen als Platzhalter interpretiert. Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen. Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.

Weitere Informationen finden Sie unter [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -"-Lesen"

Gibt an, wie viele Zeilen mit Inhalt gleichzeitig über die Pipeline übergeben werden. Der Standardwert ist 1.
Mit dem Wert %%amp;quot;0%%amp;quot; (null) wird der gesamte Inhalt auf einmal übergeben.

Dieser Parameter ändert den angezeigten Inhalt nicht, sondern wirkt sich auf die Zeit aus, die zum Anzeigen des Inhalts benötigt wird. Je größer der Wert von **ReadCount** wird, desto länger dauert es, bis die erste Zeile zurückgegeben wird. Die erforderliche Gesamtzeit für den Vorgang hingegen verringert sich. Dies kann zu einem wahrnehmbaren Unterschied in großen Elementen führen.

```yaml
Type: System.Int64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 1
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TotalCount

Gibt die Anzahl der Zeilen vom Anfang einer Datei oder eines anderen Elements an. Der Standardwert ist %%amp;quot;-1%%amp;quot; (alle Zeilen).

Sie können den **totalCount** -Parameternamen oder seine Aliase ( **First** oder **Head** ) verwenden.

```yaml
Type: System.Int64
Parameter Sets: (All)
Aliases: First, Head

Required: False
Position: Named
Default value: -1
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Tail

Gibt die Anzahl der Zeilen vom Ende einer Datei oder eines anderen Elements an. Sie können den Namen des **Tail** -Parameters oder den zugehörigen Alias **verwenden.** Dieser Parameter wurde in PowerShell 3,0 eingeführt.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: Last

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Filter

Gibt einen Filter zum Qualifizieren des **path** -Parameters an. Der [File System](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) -Anbieter ist der einzige installierte PowerShell-Anbieter, der die Verwendung von Filtern unterstützt. Die Syntax für die Filter Sprache des **Dateisystems** finden Sie in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).
Filter sind effizienter als andere Parameter, da Sie vom Anbieter angewendet werden, wenn das Cmdlet die Objekte abruft, statt dass PowerShell die Objekte nach dem Abrufen filtert.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Include

Gibt als Zeichen folgen Array ein Element oder Elemente an, die dieses Cmdlet in den Vorgang einschließt. Der Wert dieses Parameters qualifiziert den **Path** -Parameter. Geben Sie ein Pfad Element oder-Muster ein, z `"*.txt"` . b.. Platzhalterzeichen sind zulässig. Der **include** -Parameter ist nur wirksam, wenn der-Befehl den Inhalt eines Elements enthält, z `C:\Windows\*` . b., wobei das Platzhalter Zeichen den Inhalt des `C:\Windows` Verzeichnisses angibt.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Ausschließen

Gibt als Zeichen folgen Array ein Element oder Elemente an, die von diesem Cmdlet im Vorgang ausgeschlossen werden.
Der Wert dieses Parameters qualifiziert den **Path** -Parameter.

Geben Sie ein Pfad Element oder-Muster ein, z `*.txt` . b..
Platzhalterzeichen sind zulässig.

Der **Exclude** -Parameter ist nur wirksam, wenn der-Befehl den Inhalt eines Elements enthält, z `C:\Windows\*` . b., wobei das Platzhalter Zeichen den Inhalt des `C:\Windows` Verzeichnisses angibt.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Force

**Force** überschreibt ein Schreib geschütztes Attribut oder erstellt Verzeichnisse, um einen Dateipfad abzuschließen. Der **Force** -Parameter versucht nicht, Dateiberechtigungen zu ändern oder Sicherheitseinschränkungen zu überschreiben.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential

> [!NOTE]
> Dieser Parameter wird von Anbietern, die mit PowerShell installiert wurden, nicht unterstützt.
> Verwenden Sie zum Annehmen der Identität eines anderen Benutzers oder zum herauf Stufen ihrer Anmelde Informationen bei der Ausführung dieses Cmdlets "Start [-Command](../Microsoft.PowerShell.Core/Invoke-Command.md)".

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Delimiter

Gibt das Trennzeichen an, das `Get-Content` von verwendet wird, um die Datei beim Lesen in Objekte aufzuteilen. Der Standardwert ist `\n` , das Zeilenendezeichen. Gibt beim Lesen einer Textdatei `Get-Content` eine Auflistung von Zeichen folgen Objekten zurück, die jeweils mit einem Zeilenendezeichen enden. Wenn Sie ein Trennzeichen eingeben, das in der Datei nicht vorhanden ist, `Get-Content` gibt die gesamte Datei als einzelnes, nicht Begrenzungs Objekt zurück.

Sie können diesen Parameter verwenden, um eine große Datei in kleinere Dateien aufzuteilen, indem Sie ein Datei Trennzeichen als Trennzeichen angeben. Das Trennzeichen wird beibehalten (nicht verworfen) und wird das letzte Element in jedem Dateiabschnitt.

**Delimiter** ist ein dynamischer Parameter, den der **File System** -Anbieter zum `Get-Content` Cmdlet hinzufügt. Dieser Parameter funktioniert nur in Dateisystemlaufwerken.

> [!NOTE]
> Wenn der Wert des **Delimiter** -Parameters eine leere Zeichenfolge ist, gibt aktuell `Get-Content` nichts zurück. Dies ist ein bekanntes Problem. , Um zu erzwingen, dass `Get-Content` die gesamte Datei als einzelne, nicht durch Trennzeichen getrennte Zeichenfolge zurückgegeben wird. Geben Sie einen Wert ein, der in der Datei nicht vorhanden ist.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: End-of-line character
Accept pipeline input: False
Accept wildcard characters: False
```

### -Wait

Hält die Datei offen, nachdem alle vorhandenen Zeilen ausgegeben wurden. Beim Warten `Get-Content` überprüft die Datei einmal pro Sekunde und gibt ggf. neue Zeilen aus. Sie können den **warte** Vorgang durch Drücken von **STRG + C** unterbrechen. Warten wird auch beendet, wenn die Datei gelöscht wird. in diesem Fall wird ein Fehler ohne Abbruch gemeldet.

**Wait** ist ein dynamischer Parameter, den der File System-Anbieter zum `Get-Content` Cmdlet hinzufügt. Dieser Parameter funktioniert nur in Dateisystemlaufwerken. Der **warte** Vorgang kann nicht mit **RAW** kombiniert werden.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -RAW

Ignoriert Zeilen Umleitungs Zeichen und gibt den gesamten Inhalt einer Datei in einer Zeichenfolge zurück, wobei die Zeilenumbrüche beibehalten werden. Standardmäßig werden Zeilen vorzeichenfolgen als Trennzeichen verwendet, um die Eingabe in ein Array von Zeichen folgen zu trennen. Dieser Parameter wurde in PowerShell 3,0 eingeführt.

**RAW** ist ein dynamischer Parameter, den der **File** System-Anbieter zum `Get-Content` Cmdlet hinzufügt. dieser Parameter funktioniert nur in Dateisystem Laufwerken.

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

### -Codierung

Gibt den Typ der Codierung für die Zieldatei an. Der Standardwert ist `Default`.

Die zulässigen Werte für diesen Parameter lauten wie folgt:

- `Ascii` Verwendet den ASCII-Zeichensatz (7-Bit).
- `BigEndianUnicode` Verwendet UTF-16 mit der Big-Endian-Byte Reihenfolge.
- `BigEndianUTF32` Verwendet UTF-32 mit der Big-Endian-Byte Reihenfolge.
- `Byte` Codiert eine Reihe von Zeichen in eine Bytefolge.
- `Default` Verwendet die Codierung, die der aktiven Codepage des Systems entspricht (normalerweise ANSI).
- `Oem` Verwendet die Codierung, die der aktuellen OEM-Codepage des Systems entspricht.
- `String` Identisch mit `Unicode`.
- `Unicode` Verwendet UTF-16 mit der Little-Endian-Byte Reihenfolge.
- `Unknown` Identisch mit `Unicode`.
- `UTF7` Verwendet UTF-7.
- `UTF8` Verwendet UTF-8.
- `UTF32` Verwendet UTF-32 mit der Little-Endian-Byte Reihenfolge.

Encoding ist ein dynamischer Parameter, den der **File System** -Anbieter zum `Get-Content` Cmdlet hinzufügt.
Dieser Parameter funktioniert nur in Dateisystemlaufwerken.

Verwenden Sie beim Lesen aus und Schreiben in Binärdateien den Wert **Byte** für den dynamischen **Codierungs** Parameter und den Wert 0 für den **readCount** -Parameter. Der **Wert 0** (null) liest die gesamte Datei in einem einzigen Lesevorgang und konvertiert sie in ein einzelnes Objekt (psobject). Der Standardwert von "read **count** ", 1, liest ein Byte in jedem Lesevorgang und konvertiert jedes Byte in ein separates-Objekt, was zu Fehlern führt, wenn Sie das- `Set-Content` Cmdlet zum Schreiben der Bytes in eine Datei verwenden.

```yaml
Type: Microsoft.PowerShell.Commands.FileSystemCmdletProviderEncoding
Parameter Sets: (All)
Aliases:
Accepted values: ASCII, BigEndianUnicode, BigEndianUTF32, Byte, Default, OEM, String, Unicode, Unknown, UTF7, UTF8, UTF32

Required: False
Position: Named
Default value: Default
Accept pipeline input: False
Accept wildcard characters: False
```

### -Stream

Ruft die Inhalte des angegebenen alternativen NTFS-Dateidatenstroms aus der Datei ab. Geben Sie den Namen des Stroms ein.
Platzhalter werden nicht unterstützt.

**Stream** ist ein dynamischer Parameter, den der **File System** -Anbieter zum `Get-Content` Cmdlet hinzufügt.
Dieser Parameter funktioniert nur in Dateisystem Laufwerken auf Windows-Systemen. Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseTransaction

Schließt den Befehl in die aktive Transaktion ein. Dieser Parameter ist nur gültig, wenn gerade eine Transaktion ausgeführt wird. Weitere Informationen finden Sie unter [about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md).

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: usetx

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt die allgemeinen Parameter: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` und `-WarningVariable` . Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### System.Int64, System.String[], System.Management.Automation.PSCredential

Sie können die Anzahl von Lese-, Gesamt-, Pfad-oder Anmelde Informationen an über die Pipeline übergeben `Get-Content` .

## AUSGABEN

### System. Byte, System. String

`Get-Content` gibt Zeichen folgen oder Bytes zurück. Der Ausgabetyp ist abhängig vom Typ des Inhalts, den Sie als Eingabe angeben.

## HINWEISE

Das- `Get-Content` Cmdlet ist für die Arbeit mit den Daten konzipiert, die von beliebigen Anbietern verfügbar gemacht werden. Verwenden Sie das-Cmdlet, um die Anbieter in Ihrer Sitzung zu erhalten `Get-PSProvider` . Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).

## VERWANDTE LINKS

[about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md)

[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)

[Add-Content](Add-Content.md)

[Clear-Content](Clear-Content.md)

[ForEach-Object](../Microsoft.PowerShell.Core/ForEach-Object.md)

[Get-PSProvider](Get-PSProvider.md)

[Set-Content](Set-Content.md)
