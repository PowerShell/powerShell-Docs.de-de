---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-process?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Process
ms.openlocfilehash: d1a576ce9c718561718bac5fee065983a057d458
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2020
ms.locfileid: "94388296"
---
# Get-Process

## ZUSAMMENFASSUNG
Ruft die Prozesse ab, die auf dem lokalen Computer oder einem Remotecomputer ausgeführt werden.

## SYNTAX

### Name (Standard)

```
Get-Process [[-Name] <String[]>] [-ComputerName <String[]>] [-Module] [-FileVersionInfo] [<CommonParameters>]
```

### Namewithusername

```
Get-Process [[-Name] <String[]>] [-IncludeUserName] [<CommonParameters>]
```

### Idwithusername

```
Get-Process -Id <Int32[]> [-IncludeUserName] [<CommonParameters>]
```

### Id

```
Get-Process -Id <Int32[]> [-ComputerName <String[]>] [-Module] [-FileVersionInfo] [<CommonParameters>]
```

### Inputobjectwithusername

```
Get-Process -InputObject <Process[]> [-IncludeUserName] [<CommonParameters>]
```

### InputObject

```
Get-Process -InputObject <Process[]> [-ComputerName <String[]>] [-Module] [-FileVersionInfo]
 [<CommonParameters>]
```

## DESCRIPTION

Das- `Get-Process` Cmdlet ruft die Prozesse auf einem lokalen Computer oder einem Remote Computer ab.

Ohne Parameter ruft dieses Cmdlet alle Prozesse auf dem lokalen Computer ab. Sie können auch einen bestimmten Prozess mit dem Prozessnamen oder der Prozess-ID (PID) angeben oder ein Prozess Objekt über die Pipeline an dieses Cmdlet übergeben.

Standardmäßig gibt dieses Cmdlet ein Prozess Objekt mit detaillierten Informationen über den Prozess zurück und unterstützt Methoden, mit denen Sie den Prozess starten und abbrechen können. Sie können auch die Parameter des `Get-Process` Cmdlets verwenden, um Datei Versionsinformationen für das Programm zu erhalten, das im Prozess ausgeführt wird, und um die vom Prozess geladenen Module zu erhalten.

## BEISPIELE

### Beispiel 1: erhalten einer Liste aller aktiven Prozesse auf dem lokalen Computer

```powershell
Get-Process
```

Mit diesem Befehl wird eine Liste aller aktiven Prozesse abgerufen, die auf dem lokalen Computer ausgeführt werden. Eine Definition der einzelnen Spalten finden Sie im Abschnitt " [Hinweise](#notes) ".

### Beispiel 2: alle verfügbaren Daten zu einem oder mehreren Prozessen

```powershell
Get-Process winword, explorer | Format-List *
```

Mit diesem Befehl werden alle verfügbaren Daten zum Winword- und zum Explorer-Prozess auf dem Computer abgerufen. Er verwendet den **Name** -Parameter, um die Prozesse anzugeben, der optionale Parameter Name wird jedoch ausgelassen. Der Pipeline Operator `|` übergibt die Daten an das `Format-List` Cmdlet, das alle verfügbaren Eigenschaften `*` der Winword-und Explorer-Prozess Objekte anzeigt.

Sie können die Prozesse auch anhand ihrer Prozess-IDs angeben. Beispielsweise `Get-Process -Id 664, 2060`.

### Beispiel 3: alle Prozesse mit einem Workingset, das größer ist als die angegebene Größe

```powershell
Get-Process | Where-Object {$_.WorkingSet -gt 20000000}
```

Mit diesem Befehl werden alle Prozesse mit einem Arbeitssatz abgerufen, dessen Größe 20 MB übersteigt. Er verwendet das `Get-Process` Cmdlet, um alle laufenden Prozesse zu erhalten. Der Pipeline Operator `|` übergibt die Prozess Objekte an das `Where-Object` Cmdlet, das nur das Objekt auswählt, dessen Wert größer als 20 Millionen Byte für die **Workingset** -Eigenschaft ist.

**Workingset** ist eine von vielen Eigenschaften von Prozess Objekten. Um alle Eigenschaften anzuzeigen, geben Sie ein `Get-Process | Get-Member` . Standardmäßig werden die Werte aller Mengeneigenschaften in Bytes angegeben, auch wenn sie in der Standardanzeige in Kilobytes und Megabytes aufgeführt werden.

### Beispiel 4: Auflisten von Prozessen auf dem Computer in Gruppen basierend auf der Priorität

```powershell
$A = Get-Process
$A | Get-Process | Format-Table -View priority
```

Diese Befehle Listen die Prozesse auf dem Computer in Gruppen auf Grundlage ihrer Prioritäts Klasse auf. Der erste Befehl ruft alle Prozesse auf dem Computer ab und speichert Sie dann in der `$A` Variablen.

Mit dem zweiten Befehl wird das in der Variablen gespeicherte **Prozess** Objekt `$A` an das `Get-Process` Cmdlet weitergeleitet, dann an das `Format-Table` Cmdlet, das die Prozesse mithilfe der **Prioritäts** Ansicht formatiert.

Die **Prioritäts** Ansicht und andere Ansichten werden in den PS1XML-Format Dateien im PowerShell-Basisverzeichnis ( `$pshome` ) definiert.

### Beispiel 5: Hinzufügen einer Eigenschaft zur Standard Get-Process Ausgabe Anzeige

```powershell
Get-Process powershell -ComputerName S1, localhost | Format-Table `
    @{Label = "NPM(K)"; Expression = {[int]($_.NPM / 1024)}},
    @{Label = "PM(K)"; Expression = {[int]($_.PM / 1024)}},
    @{Label = "WS(K)"; Expression = {[int]($_.WS / 1024)}},
    @{Label = "VM(M)"; Expression = {[int]($_.VM / 1MB)}},
    @{Label = "CPU(s)"; Expression = {if ($_.CPU) {$_.CPU.ToString("N")}}},
    Id, MachineName, ProcessName -AutoSize
```

```Output
NPM(K) PM(K) WS(K) VM(M) CPU(s)   Id MachineName ProcessName
------ ----- ----- ----- ------   -- ----------- -----------
     6 23500 31340   142 1.70   1980 S1          powershell
     6 23500 31348   142 2.75   4016 S1          powershell
    27 54572 54520   576 5.52   4428 localhost   powershell
```

In diesem Beispiel werden Prozesse vom lokalen Computer und einem Remote Computer (S1) abgerufen. Die abgerufenen Prozesse werden an den Befehl weitergeleitet `Format-Table` , der die **MachineName** -Eigenschaft der Standard `Get-Process` Ausgabe Anzeige hinzufügt.

### Beispiel 6: erhalten von Versionsinformationen für einen Prozess

```powershell
Get-Process powershell -FileVersionInfo
```

```Output
ProductVersion   FileVersion      FileName
--------------   -----------      --------
6.1.6713.1       6.1.6713.1 (f... C:\WINDOWS\system32\WindowsPowerShell\v1.0\powershell.exe
```

Dieser Befehl verwendet den **FileVersionInfo** -Parameter, um die Versionsinformationen für die powershell.exe-Datei zu erhalten, die das Hauptmodul für den PowerShell-Prozess ist.

Wenn Sie diesen Befehl mit Prozessen ausführen möchten, die Sie nicht unter Windows Vista und höheren Versionen von Windows besitzen, müssen Sie PowerShell mit der Option als Administrator ausführen öffnen.

### Beispiel 7: Get-Module, die mit dem angegebenen Prozess geladen wurden

```powershell
Get-Process SQL* -Module
```

Dieser Befehl verwendet den **Module-Parameter,** um die Module, die vom Prozess geladen wurden, zu erhalten.
Dieser Befehl ruft die Module für die Prozesse ab, deren Namen mit SQL beginnen.

Wenn Sie diesen Befehl unter Windows Vista und höheren Versionen von Windows mit Prozessen ausführen möchten, die Sie nicht besitzen, müssen Sie PowerShell mit der Option als Administrator ausführen starten.

### Beispiel 8: Ermitteln des Besitzers eines Prozesses

```powershell
Get-Process pwsh -IncludeUserName
```

```Output
Handles      WS(K)   CPU(s)     Id UserName            ProcessName
-------      -----   ------     -- --------            -----------
    782     132080     2.08   2188 DOMAIN01\user01     powershell
```

```powershell
$p = Get-WmiObject Win32_Process -Filter "name='powershell.exe'"
$p.GetOwner()
```

```Output
__GENUS          : 2
__CLASS          : __PARAMETERS
__SUPERCLASS     :
__DYNASTY        : __PARAMETERS
__RELPATH        :
__PROPERTY_COUNT : 3
__DERIVATION     : {}
__SERVER         :
__NAMESPACE      :
__PATH           :
Domain           : DOMAIN01
ReturnValue      : 0
User             : user01
```

Der erste Befehl zeigt, wie der Besitzer eines Prozesses ermittelt wird. Der **includeusername** -Parameter erfordert erhöhte Benutzerrechte (als Administrator ausführen). Die Ausgabe zeigt, dass der Besitzer Domain01\user01. ist.

Mit dem zweiten und dritten Befehl können Sie den Besitzer eines Prozesses ermitteln.

Der zweite Befehl verwendet `Get-WmiObject` , um den PowerShell-Prozess zu erhalten.
Sie speichert Sie in der `$p` Variablen.

Der dritte Befehl verwendet die GetOwner-Methode, um den Besitzer des Prozesses in zu erhalten `$p` . Die Ausgabe zeigt, dass der Besitzer Domain01\user01. ist.

### Beispiel 9: Verwenden einer automatischen Variablen zum Identifizieren des Prozesses, der die aktuelle Sitzung gehostet

```powershell
Get-Process powershell
```

```Output
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
308      26        52308      61780   567     3.18   5632 powershell
377      26        62676      63384   575     3.88   5888 powershell
```

```powershell
Get-Process -Id $PID
```

```Output
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
396      26        56488      57236   575     3.90   5888 powershell
```

Diese Befehle zeigen, wie Sie die `$PID` Automatische Variable verwenden, um den Prozess zu identifizieren, der die aktuelle PowerShell-Sitzung gehostet. Sie können den Hostprozess mithilfe dieser Methode von anderen PowerShell-Prozessen unterscheiden, die Sie beenden oder schließen möchten.

Der erste Befehl ruft alle PowerShell-Prozesse in der aktuellen Sitzung ab.

Der zweite Befehl ruft den PowerShell-Prozess ab, der die aktuelle Sitzung gehostet.

### Beispiel 10: Hiermit werden alle Prozesse mit einem Hauptfenster Titel und in einer Tabelle angezeigt.

```powershell
Get-Process | Where-Object {$_.mainWindowTitle} | Format-Table Id, Name, mainWindowtitle -AutoSize
```

Mit diesem Befehl werden alle Prozesse mit einem Hauptfenstertitel abgerufen und in einer Tabelle mit der Prozess-ID und dem Prozessnamen angezeigt.

Die **MainWindowTitle** -Eigenschaft ist nur eine von vielen nützlichen Eigenschaften des **Prozess** Objekts, das `Get-Process` zurückgibt. Um alle Eigenschaften anzuzeigen, reichen Sie die Ergebnisse eines Befehls über `Get-Process` die Pipeline an das `Get-Member` Cmdlet weiter `Get-Process | Get-Member` .

## PARAMETERS

### -ComputerName

Gibt die Computer an, für die dieses Cmdlet aktive Prozesse abruft. Die Standardeinstellung ist der lokale Computer.

Geben Sie den NetBIOS-Namen, eine IP-Adresse oder einen voll qualifizierten Domänen Namen (Fully Qualified Domain Name, FQDN) eines oder mehrerer Computer ein. Geben Sie den Computernamen, einen Punkt (.) oder einen localhost ein, um den lokalen Computer anzugeben.

Dieser Parameter beruht nicht auf Windows PowerShell-Remoting. Sie können den Computer **Name** -Parameter dieses Cmdlets auch dann verwenden, wenn der Computer nicht für das Ausführen von Remote Befehlen konfiguriert ist.

```yaml
Type: System.String[]
Parameter Sets: Name, Id, InputObject
Aliases: Cn

Required: False
Position: Named
Default value: Local computer
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -FileVersionInfo

Gibt an, dass dieses Cmdlet die Datei Versionsinformationen für das Programm abruft, das im Prozess ausgeführt wird.

Unter Windows Vista und höheren Versionen von Windows müssen Sie PowerShell mit der Option "als Administrator ausführen" öffnen, um diesen Parameter für Prozesse zu verwenden, deren Besitzer Sie sind.

Der **FileVersionInfo** -Parameter und der **Computername** -Parameter des `Get-Process` Cmdlets können nicht im selben Befehl verwendet werden.

Verwenden Sie das-Cmdlet, um die Datei Versionsinformationen für einen Prozess auf einem Remote Computer zu erhalten `Invoke-Command` .

Die Verwendung dieses Parameters entspricht dem erhalten der **MainModule. FileVersionInfo** -Eigenschaft für jedes Prozess Objekt. Wenn Sie diesen Parameter verwenden, `Get-Process` gibt ein **FileVersionInfo** -Objekt **System. Diagnostics. FileVersionInfo** zurück, kein Prozess Objekt. Daher können Sie die Ausgabe des Befehls nicht an ein Cmdlet übergeben, das ein Prozess Objekt erwartet, z `Stop-Process` . b..

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Name, Id, InputObject
Aliases: FV, FVI

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id

Gibt einen oder mehrere Prozesse anhand der Prozess-ID (PID) an. Wenn Sie mehrere IDs angeben, trennen Sie diese durch Kommas. Um die PID eines Prozesses zu ermitteln, geben Sie ein `Get-Process` .

```yaml
Type: System.Int32[]
Parameter Sets: IdWithUserName, Id
Aliases: PID

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Includeusername

Gibt an, dass der UserName-Wert des **Prozess** Objekts mit den Ergebnissen des Befehls zurückgegeben wird.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NameWithUserName, IdWithUserName, InputObjectWithUserName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Gibt Prozessobjekte an. Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, mit dem die Objekte abgerufen werden.

```yaml
Type: System.Diagnostics.Process[]
Parameter Sets: InputObjectWithUserName, InputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Modul

Gibt an, dass dieses Cmdlet die Module abruft, die von den Prozessen geladen wurden.

Unter Windows Vista und höheren Versionen von Windows müssen Sie PowerShell mit der Option " **als Administrator ausführen** " öffnen, um diesen Parameter für Prozesse zu verwenden, deren Besitzer Sie sind.

Verwenden Sie das Cmdlet, um die Module, die von einem Prozess auf einem Remote Computer geladen wurden, zu erhalten `Invoke-Command` .

Dieser Parameter entspricht dem erhalten der **modules** -Eigenschaft jedes Prozess Objekts. Wenn Sie diesen Parameter verwenden, gibt dieses Cmdlet ein **ProcessModule** -Objekt **System. Diagnostics. ProcessModule** zurück, kein Prozess Objekt. Daher können Sie die Ausgabe des Befehls nicht an ein Cmdlet übergeben, das ein Prozess Objekt erwartet, z `Stop-Process` . b..

Wenn Sie den *Module* -Parameter und den **FileVersionInfo** -Parameter im gleichen Befehl verwenden, gibt dieses Cmdlet ein **FileVersionInfo** -Objekt mit Informationen zur Dateiversion aller Module zurück.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Name, Id, InputObject
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

Gibt einen oder mehrere Prozesse mit ihrem Prozessnamen an. Sie können mehrere Prozessnamen eingeben (getrennt durch Kommas) und Platzhalterzeichen verwenden. Der Parametername (Name) ist optional.

```yaml
Type: System.String[]
Parameter Sets: Name, NameWithUserName
Aliases: ProcessName

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## EINGABEN

### System.Diagnostics.Process

Sie können ein Prozess Objekt über die Pipeline an dieses Cmdlet übergeben.

## AUSGABEN

### System. Diagnostics. Process, System. Diagnostics. FileVersionInfo, System. Diagnostics. ProcessModule

Standardmäßig gibt dieses Cmdlet ein **System. Diagnostics. Process** -Objekt zurück. Wenn Sie den **FileVersionInfo** -Parameter verwenden, wird ein **System. Diagnostics. FileVersionInfo** -Objekt zurückgegeben. Wenn Sie den **Module** -Parameter ohne den **FileVersionInfo** -Parameter verwenden, wird ein **System. Diagnostics. ProcessModule** -Objekt zurückgegeben.

## HINWEISE

- Sie können dieses Cmdlet auch über die integrierten Aliase, PS und GPS verweisen. Weitere Informationen finden Sie unter [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).
- Auf Computern, auf denen eine 64-Bit-Version von Windows ausgeführt wird, werden von der 64-Bit-Version von PowerShell nur 64-Bit-Prozessmodule abgerufen, und die 32-Bit-Version von PowerShell erhält nur die 32-Bit-Prozessmodule.
- Sie können die Eigenschaften und Methoden des Windows-Verwaltungsinstrumentation (WMI) Win32_Process-Objekts in PowerShell verwenden. Weitere Informationen finden Sie unter `Get-WmiObject` und im WMI SDK.
- Die Standardanzeige eines Prozesses ist eine Tabelle mit den folgenden Spalten: Eine Beschreibung aller Eigenschaften von Prozess Objekten finden Sie unter [Prozess Eigenschaften](/dotnet/api/system.diagnostics.process).
  - Handles: die Anzahl der Handles, die der Prozess geöffnet hat.
  - NPM (K): die Menge des vom Prozess verwendeten nicht auslagerbaren Speichers in Kilobyte.
  - PM (K): die Menge des vom Prozess verwendeten Speicher abrechenbaren Speichers in Kilobyte.
  - WS (K): die Größe des Workingsets des Prozesses in Kilobyte.
    Der Arbeitssatz besteht aus Speicherseiten, auf die zuvor vom Prozess verwiesen wurde.
  - VM (M): die Menge des vom Prozess verwendeten virtuellen Speichers in Megabyte.
    Der virtuelle Speicher umfasst den Speicher der Auslagerungsdateien auf dem Datenträger.
  - CPU (s): die Prozessorzeit (in Sekunden), die vom Prozess auf allen Prozessoren verwendet wurde.
  - ID: die Prozess-ID (PID) des Prozesses.
  - ProcessName: der Name des Prozesses. Erläuterungen zu den Prozesskonzepten finden Sie im Glossar des Hilfe- und Supportcenters sowie in der Hilfe des Task-Managers.
- Sie können auch die integrierten alternativen Ansichten der Prozesse verwenden, die in verfügbar sind `Format-Table` , z. b. **StartTime** und **Priority** , und Sie können Ihre eigenen Ansichten entwerfen.

## VERWANDTE LINKS

[Debug-Process](Debug-Process.md)

[Get-Process](Get-Process.md)

[Start-Process](Start-Process.md)

[Stop-Process](Stop-Process.md)

[Wait-Process](Wait-Process.md)
