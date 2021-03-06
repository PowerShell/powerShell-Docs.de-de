---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-object?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Object
ms.openlocfilehash: 3b2db400c5a8a1c61ec30ecee07f91d29b5eb3c1
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601130"
---
# New-Object

## ZUSAMMENFASSUNG
Erstellt eine Instanz eines Microsoft .NET Framework- oder COM-Objekts.

## SYNTAX

### NET (Standard)

```
New-Object [-TypeName] <String> [[-ArgumentList] <Object[]>] [-Property <IDictionary>] [<CommonParameters>]
```

### KOM

```
New-Object [-ComObject] <String> [-Strict] [-Property <IDictionary>] [<CommonParameters>]
```

## DESCRIPTION

Das- `New-Object` Cmdlet erstellt eine Instanz eines .NET Framework-oder COM-Objekts.

Sie können entweder den Typ einer .NET Framework-Klasse oder eine ProgID eines COM-Objekts angeben. Standardmäßig geben Sie den vollqualifizierten Namen einer .NET Framework-Klasse ein, und das Cmdlet gibt einen Verweis auf eine Instanz dieser Klasse zurück. Um eine Instanz eines COM-Objekts zu erstellen, verwenden Sie den **ComObject** -Parameter, und geben Sie die ProgID des Objekts als Wert an.

## BEISPIELE

### Beispiel 1: Erstellen eines System. Version-Objekts

In diesem Beispiel wird ein **System. Version** -Objekt mit der Zeichenfolge "1.2.3.4" als Konstruktor erstellt.

```powershell
New-Object -TypeName System.Version -ArgumentList "1.2.3.4"
```

```Output
Major  Minor  Build  Revision
-----  -----  -----  --------
1      2      3      4
```

### Beispiel 2: Erstellen eines COM-Objekts in Internet Explorer

In diesem Beispiel werden zwei Instanzen des COM-Objekts erstellt, das die Internet Explorer-Anwendung darstellt. Die erste Instanz verwendet die Hash Tabelle der **Eigenschaften** Parameter, um die **Navigate2** -Methode aufzurufen, und legt die **Visible** -Eigenschaft des-Objekts auf fest, `$True` um die Anwendung sichtbar zu machen.
Die zweite Instanz erhält dieselben Ergebnisse mit einzelnen Befehlen.

```powershell
$IE1 = New-Object -COMObject InternetExplorer.Application -Property @{Navigate2="www.microsoft.com"; Visible = $True}

# The following command gets the same results as the example above.
$IE2 = New-Object -COMObject InternetExplorer.Application`
$IE2.Navigate2("www.microsoft.com")`
$IE2.Visible = $True`
```

### Beispiel 3: Verwenden Sie den Strict-Parameter, um einen Fehler ohne Abbruch zu generieren.

In diesem Beispiel wird veranschaulicht, dass das Hinzufügen des **Strict** -Parameters bewirkt, dass das `New-Object` Cmdlet einen Fehler ohne Abbruch generiert, wenn das COM-Objekt eine Interop-Assembly verwendet.

```powershell
$A = New-Object -COMObject Word.Application -Strict -Property @{Visible = $True}
```

```Output
New-Object : The object written to the pipeline is an instance of the type
"Microsoft.Office.Interop.Word.ApplicationClass" from the component's primary interop assembly. If
this type exposes different members than the IDispatch members, scripts written to work with this
object might not work if the primary interop assembly is not installed.

At line:1 char:14
+ $A = New-Object  <<<< -COM Word.Application -Strict; $a.visible=$true
```

### Beispiel 4: Erstellen eines COM-Objekts zum Verwalten von Windows-Desktop

Dieses Beispiel zeigt das Erstellen und Verwenden eines COM-Objekts zur Verwaltung Ihres Windows-Desktops.

Der erste Befehl verwendet den **ComObject** -Parameter des `New-Object` Cmdlets zum Erstellen eines COM-Objekts mit der **Shell. Application** ProgID. Das resultierende Objekt wird in der `$ObjShell` Variablen gespeichert. Mit dem zweiten Befehl `$ObjShell` wird die Variable an das `Get-Member` Cmdlet weitergeleitet, das die Eigenschaften und Methoden des COM-Objekts anzeigt. Zu den Methoden gehört die Methode " **deggledesktop** ". Der dritte Befehl ruft die **ToggleDesktop**-Methode des Objekts auf, um die geöffneten Fenster auf dem Desktop zu minimieren.

```powershell
$Objshell = New-Object -COMObject "Shell.Application"
$objshell | Get-Member
$objshell.ToggleDesktop()
```

```Output
   TypeName: System.__ComObject#{866738b9-6cf2-4de8-8767-f794ebe74f4e}

Name                 MemberType Definition
----                 ---------- ----------
AddToRecent          Method     void AddToRecent (Variant, string)
BrowseForFolder      Method     Folder BrowseForFolder (int, string, int, Variant)
CanStartStopService  Method     Variant CanStartStopService (string)
CascadeWindows       Method     void CascadeWindows ()
ControlPanelItem     Method     void ControlPanelItem (string)
EjectPC              Method     void EjectPC ()
Explore              Method     void Explore (Variant)
ExplorerPolicy       Method     Variant ExplorerPolicy (string)
FileRun              Method     void FileRun ()
FindComputer         Method     void FindComputer ()
FindFiles            Method     void FindFiles ()
FindPrinter          Method     void FindPrinter (string, string, string)
GetSetting           Method     bool GetSetting (int)
GetSystemInformation Method     Variant GetSystemInformation (string)
Help                 Method     void Help ()
IsRestricted         Method     int IsRestricted (string, string)
IsServiceRunning     Method     Variant IsServiceRunning (string)
MinimizeAll          Method     void MinimizeAll ()
NameSpace            Method     Folder NameSpace (Variant)
Open                 Method     void Open (Variant)
RefreshMenu          Method     void RefreshMenu ()
ServiceStart         Method     Variant ServiceStart (string, Variant)
ServiceStop          Method     Variant ServiceStop (string, Variant)
SetTime              Method     void SetTime ()
ShellExecute         Method     void ShellExecute (string, Variant, Variant, Variant, Variant)
ShowBrowserBar       Method     Variant ShowBrowserBar (string, Variant)
ShutdownWindows      Method     void ShutdownWindows ()
Suspend              Method     void Suspend ()
TileHorizontally     Method     void TileHorizontally ()
TileVertically       Method     void TileVertically ()
ToggleDesktop        Method     void ToggleDesktop ()
TrayProperties       Method     void TrayProperties ()
UndoMinimizeALL      Method     void UndoMinimizeALL ()
Windows              Method     IDispatch Windows ()
WindowsSecurity      Method     void WindowsSecurity ()
WindowSwitcher       Method     void WindowSwitcher ()
Application          Property   IDispatch Application () {get}
Parent               Property   IDispatch Parent () {get}
```

### Beispiel 5: übergeben von mehreren Argumenten an einen Konstruktor

In diesem Beispiel wird gezeigt, wie ein-Objekt mit einem Konstruktor erstellt wird, der mehrere Parameter annimmt. Die Parameter müssen in ein Array eingefügt werden, wenn der Argument **List** -Parameter verwendet wird.

```powershell
$array = @('One', 'Two', 'Three')
$parameters = @{
    TypeName = 'System.Collections.Generic.HashSet[string]'
    ArgumentList = ([string[]]$array, [System.StringComparer]::OrdinalIgnoreCase)
}
$set = New-Object @parameters
```

PowerShell bindet jeden Member des Arrays an einen Parameter des Konstruktors.

> [!NOTE]
> In diesem Beispiel werden Parameter-Verteilung zur besseren Lesbarkeit verwendet. Weitere Informationen finden Sie unter [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md).

### Beispiel 6: Aufrufen eines Konstruktors, der ein Array als einzelnen Parameter annimmt

Dieses Beispiel zeigt, wie ein Objekt mit einem Konstruktor erstellt wird, der einen Parameter annimmt, bei dem es sich um ein Array oder eine Auflistung handelt. Der Array Parameter muss in ein anderes Array eingefügt werden.

```powershell
$array = @('One', 'Two', 'Three')
# This command throws an exception.
$set = New-Object -TypeName 'System.Collections.Generic.HashSet[string]' -ArgumentList $array
# This command succeeds.
$set = New-Object -TypeName 'System.Collections.Generic.HashSet[string]' -ArgumentList (,[string[]]$array)
$set
```

```Output
New-Object : Cannot find an overload for "HashSet`1" and the argument count: "3".
At line:1 char:8
+ $set = New-Object -TypeName 'System.Collections.Generic.HashSet[strin ...
+        ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
+ CategoryInfo          : InvalidOperation: (:) [New-Object], MethodException
+ FullyQualifiedErrorId : ConstructorInvokedThrowException,Microsoft.PowerShell.Commands.NewObjectCommand

One
Two
Three
```

Beim ersten Versuch, das-Objekt in diesem Beispiel zu erstellen, tritt ein Fehler auf. PowerShell hat versucht, die drei Member von `$array` an Parameter des Konstruktors zu binden, aber der Konstruktor akzeptiert nicht drei Parameter. `$array`Durch das umwickeln in ein anderes Array wird verhindert, dass PowerShell versucht, die drei Member von `$array` an Parameter des Konstruktors zu binden.

## PARAMETERS

### -Argumentlist

Gibt ein Array von Argumenten an, die an den Konstruktor der .NET Framework Klasse übergeben werden sollen. Wenn der Konstruktor einen einzelnen Parameter annimmt, bei dem es sich um ein Array handelt, müssen Sie diesen Parameter in einem anderen Array einschließen. Beispiel:

`$cert = New-Object System.Security.Cryptography.X509Certificates.X509Certificate -ArgumentList (,$bytes)`

Weitere Informationen zum Verhalten von **argumentlist** finden Sie unter [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md#splatting-with-arrays).

Der Alias für **ArgumentList** ist **Args**.

```yaml
Type: System.Object[]
Parameter Sets: Net
Aliases: Args

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComObject

Gibt den Programmbezeichner (ProgID) des COM-Objekts an.

```yaml
Type: System.String
Parameter Sets: Com
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Eigenschaft

Legt Eigenschaftswerte fest und ruft Methoden des neuen Objekts auf.

Geben Sie eine Hashtabelle ein, in der die Schlüssel die Namen von Eigenschaften oder Methoden und die Werte Eigenschaftswerte oder Methodenargumente sind. `New-Object` erstellt das-Objekt und legt die einzelnen Eigenschaftswerte fest und ruft jede Methode in der Reihenfolge auf, in der Sie in der Hash Tabelle angezeigt werden.

Wenn das neue Objekt von der **psobject** -Klasse abgeleitet wird und Sie eine Eigenschaft angeben, die im Objekt nicht vorhanden ist, `New-Object` fügt die angegebene Eigenschaft dem Objekt als NoteProperty hinzu. Wenn das Objekt kein **psobject** ist, generiert der Befehl einen Fehler ohne Abbruch.

```yaml
Type: System.Collections.IDictionary
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Strict

Gibt an, dass das Cmdlet einen Fehler ohne Abbruch generiert, wenn ein COM-Objekt, das Sie zu erstellen versuchen, eine Interop-Assembly verwendet. Dieses Feature unterscheidet tatsächliche COM-Objekte von .NET Framework-Objekten mit COM Callable Wrappers.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Com
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Typname

Gibt den vollqualifizierten Namen der .NET Framework-Klasse an. Sie können nicht gleichzeitig den **tykame** -Parameter und den **ComObject** -Parameter angeben.

```yaml
Type: System.String
Parameter Sets: Net
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### Keine

Eingaben können nicht an dieses Cmdlet weitergereicht werden.

## AUSGABEN

### Object

`New-Object` Gibt das-Objekt zurück, das erstellt wird.

## HINWEISE

- `New-Object` stellt die am häufigsten verwendete Funktionalität der VBScript-Funktion "deateobject" bereit. Eine Anweisung wie `Set objShell = CreateObject("Shell.Application")` in VBScript kann `$objShell = New-Object -COMObject "Shell.Application"` in PowerShell in übersetzt werden.
- `New-Object` erweitert die Funktionen, die in der Windows Script Host-Umgebung verfügbar sind, indem die Arbeit mit .NET Framework-Objekten über die Befehlszeile und innerhalb von Skripts vereinfacht wird.

## VERWANDTE LINKS

[about_Object_Creation](../Microsoft.PowerShell.Core/About/about_Object_Creation.md)

[Compare-Object](Compare-Object.md)

[Group-Object](Group-Object.md)

[Measure-Object](Measure-Object.md)

[Select-Object](Select-Object.md)

[Sort-Object](Sort-Object.md)

[Tee-Object](Tee-Object.md)

