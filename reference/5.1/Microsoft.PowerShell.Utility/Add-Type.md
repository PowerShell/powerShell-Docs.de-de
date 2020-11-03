---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/26/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/add-type?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Add-Type
ms.openlocfilehash: af7cd937ccfc7c5f05fd0213764ed51a3ba9f2bb
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214159"
---
# <span data-ttu-id="e5362-103">Add-Type</span><span class="sxs-lookup"><span data-stu-id="e5362-103">Add-Type</span></span>

## <span data-ttu-id="e5362-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="e5362-104">SYNOPSIS</span></span>
<span data-ttu-id="e5362-105">Fügt einer PowerShell-Sitzung eine Microsoft .NET Framework-Klasse hinzu.</span><span class="sxs-lookup"><span data-stu-id="e5362-105">Adds a Microsoft .NET Framework class to a PowerShell session.</span></span>

## <span data-ttu-id="e5362-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e5362-106">SYNTAX</span></span>

### <span data-ttu-id="e5362-107">Fromsource (Standard)</span><span class="sxs-lookup"><span data-stu-id="e5362-107">FromSource (Default)</span></span>

```
Add-Type [-CodeDomProvider <CodeDomProvider>] [-CompilerParameters <CompilerParameters>]
 [-TypeDefinition] <String> [-Language <Language>] [-ReferencedAssemblies <String[]>]
 [-OutputAssembly <String>] [-OutputType <OutputAssemblyType>] [-PassThru] [-IgnoreWarnings]
 [<CommonParameters>]
```

### <span data-ttu-id="e5362-108">Frommember</span><span class="sxs-lookup"><span data-stu-id="e5362-108">FromMember</span></span>

```
Add-Type [-CodeDomProvider <CodeDomProvider>] [-CompilerParameters <CompilerParameters>]
 [-Name] <String> [-MemberDefinition] <String[]> [-Namespace <String>] [-UsingNamespace <String[]>]
 [-Language <Language>] [-ReferencedAssemblies <String[]>] [-OutputAssembly <String>]
 [-OutputType <OutputAssemblyType>] [-PassThru] [-IgnoreWarnings] [<CommonParameters>]
```

### <span data-ttu-id="e5362-109">Frompath</span><span class="sxs-lookup"><span data-stu-id="e5362-109">FromPath</span></span>

```
Add-Type [-CompilerParameters <CompilerParameters>] [-Path] <String[]>
 [-ReferencedAssemblies <String[]>] [-OutputAssembly <String>] [-OutputType <OutputAssemblyType>]
 [-PassThru] [-IgnoreWarnings] [<CommonParameters>]
```

### <span data-ttu-id="e5362-110">Fromliteralpath</span><span class="sxs-lookup"><span data-stu-id="e5362-110">FromLiteralPath</span></span>

```
Add-Type [-CompilerParameters <CompilerParameters>] -LiteralPath <String[]>
 [-ReferencedAssemblies <String[]>] [-OutputAssembly <String>] [-OutputType <OutputAssemblyType>]
 [-PassThru] [-IgnoreWarnings] [<CommonParameters>]
```

### <span data-ttu-id="e5362-111">Fromassemblyname</span><span class="sxs-lookup"><span data-stu-id="e5362-111">FromAssemblyName</span></span>

```
Add-Type -AssemblyName <String[]> [-PassThru] [-IgnoreWarnings] [<CommonParameters>]
```

## <span data-ttu-id="e5362-112">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e5362-112">DESCRIPTION</span></span>

<span data-ttu-id="e5362-113">Mit dem- `Add-Type` Cmdlet können Sie in ihrer PowerShell-Sitzung eine Microsoft .NET Framework-Klasse definieren.</span><span class="sxs-lookup"><span data-stu-id="e5362-113">The `Add-Type` cmdlet lets you define a Microsoft .NET Framework class in your PowerShell session.</span></span>
<span data-ttu-id="e5362-114">Anschließend können Sie Objekte mit dem `New-Object` Cmdlet instanziieren und die Objekte wie jedes beliebige .NET Framework Objekt verwenden.</span><span class="sxs-lookup"><span data-stu-id="e5362-114">You can then instantiate objects, by using the `New-Object` cmdlet, and use the objects just as you would use any .NET Framework object.</span></span> <span data-ttu-id="e5362-115">Wenn Sie `Add-Type` Ihrem PowerShell-Profil einen Befehl hinzufügen, ist die Klasse in allen PowerShell-Sitzungen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e5362-115">If you add an `Add-Type` command to your PowerShell profile, the class is available in all PowerShell sessions.</span></span>

<span data-ttu-id="e5362-116">Sie können den Typ angeben, indem Sie eine vorhandene Assembly oder Quellcodedateien angeben, oder Sie können den Quellcode inline oder in einer Variablen gespeichert angeben.</span><span class="sxs-lookup"><span data-stu-id="e5362-116">You can specify the type by specifying an existing assembly or source code files, or you can specify the source code inline or saved in a variable.</span></span> <span data-ttu-id="e5362-117">Sie können sogar nur eine-Methode angeben und `Add-Type` die-Klasse definieren und generieren.</span><span class="sxs-lookup"><span data-stu-id="e5362-117">You can even specify only a method and `Add-Type` will define and generate the class.</span></span> <span data-ttu-id="e5362-118">Unter Windows können Sie diese Funktion verwenden, um Platt Form Aufrufe (P/aufrufen) von nicht verwalteten Funktionen in PowerShell durchführen.</span><span class="sxs-lookup"><span data-stu-id="e5362-118">On Windows, you can use this feature to make Platform Invoke (P/Invoke) calls to unmanaged functions in PowerShell.</span></span> <span data-ttu-id="e5362-119">Wenn Sie Quellcode angeben, `Add-Type` kompiliert den angegebenen Quellcode und generiert eine in-Memory-Assembly, die die neuen .NET Framework Typen enthält.</span><span class="sxs-lookup"><span data-stu-id="e5362-119">If you specify source code, `Add-Type` compiles the specified source code and generates an in-memory assembly that contains the new .NET Framework types.</span></span>

<span data-ttu-id="e5362-120">Sie können die Parameter von verwenden, `Add-Type` um eine alternative Sprache und einen anderen Compiler anzugeben, c# ist die Standardeinstellung, Compileroptionen, Assemblyabhängigkeiten, den Klassen Namespace, die Namen des Typs und die resultierende Assembly.</span><span class="sxs-lookup"><span data-stu-id="e5362-120">You can use the parameters of `Add-Type` to specify an alternate language and compiler, C# is the default, compiler options, assembly dependencies, the class namespace, the names of the type, and the resulting assembly.</span></span>

## <span data-ttu-id="e5362-121">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="e5362-121">EXAMPLES</span></span>

### <span data-ttu-id="e5362-122">Beispiel 1: Hinzufügen eines .net-Typs zu einer Sitzung</span><span class="sxs-lookup"><span data-stu-id="e5362-122">Example 1: Add a .NET type to a session</span></span>

<span data-ttu-id="e5362-123">In diesem Beispiel wird die **basictest** -Klasse der Sitzung hinzugefügt, indem Quellcode angegeben wird, der in einer Variablen gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="e5362-123">This example adds the **BasicTest** class to the session by specifying source code that is stored in a variable.</span></span> <span data-ttu-id="e5362-124">Die **basictest** -Klasse wird verwendet, um ganze Zahlen hinzuzufügen, ein Objekt zu erstellen und ganze Zahlen zu multiplizieren.</span><span class="sxs-lookup"><span data-stu-id="e5362-124">The **BasicTest** class is used to add integers, create an object, and multiply integers.</span></span>

```powershell
$Source = @"
public class BasicTest
{
  public static int Add(int a, int b)
    {
        return (a + b);
    }
  public int Multiply(int a, int b)
    {
    return (a * b);
    }
}
"@

Add-Type -TypeDefinition $Source
[BasicTest]::Add(4, 3)
$BasicTestObject = New-Object BasicTest
$BasicTestObject.Multiply(5, 2)
```

<span data-ttu-id="e5362-125">Die- `$Source` Variable speichert den Quellcode für die-Klasse.</span><span class="sxs-lookup"><span data-stu-id="e5362-125">The `$Source` variable stores the source code for the class.</span></span> <span data-ttu-id="e5362-126">Der-Typ verfügt über eine statische Methode mit dem Namen `Add` und eine nicht statische Methode mit dem Namen `Multiply` .</span><span class="sxs-lookup"><span data-stu-id="e5362-126">The type has a static method called `Add` and a non-static method called `Multiply`.</span></span>

<span data-ttu-id="e5362-127">Mit dem- `Add-Type` Cmdlet wird die-Klasse der Sitzung hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="e5362-127">The `Add-Type` cmdlet adds the class to the session.</span></span> <span data-ttu-id="e5362-128">Da es Inline Quellcode verwendet, verwendet der Befehl den **typeDefinition** -Parameter, um den Code in der `$Source` Variablen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="e5362-128">Because it's using inline source code, the command uses the **TypeDefinition** parameter to specify the code in the `$Source` variable.</span></span>

<span data-ttu-id="e5362-129">Die `Add` statische-Methode der **basictest** -Klasse verwendet die doppelten Doppelpunkte ( `::` ), um einen statischen Member der-Klasse anzugeben.</span><span class="sxs-lookup"><span data-stu-id="e5362-129">The `Add` static method of the **BasicTest** class uses the double-colon characters (`::`) to specify a static member of the class.</span></span> <span data-ttu-id="e5362-130">Die ganzen Zahlen werden hinzugefügt, und die Summe wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e5362-130">The integers are added and the sum is displayed.</span></span>

<span data-ttu-id="e5362-131">Das- `New-Object` Cmdlet instanziiert eine Instanz der **basictest** -Klasse.</span><span class="sxs-lookup"><span data-stu-id="e5362-131">The `New-Object` cmdlet instantiates an instance of the **BasicTest** class.</span></span> <span data-ttu-id="e5362-132">Das neue Objekt wird in der `$BasicTestObject` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="e5362-132">It saves the new object in the `$BasicTestObject` variable.</span></span>

<span data-ttu-id="e5362-133">`$BasicTestObject` verwendet die- `Multiply` Methode.</span><span class="sxs-lookup"><span data-stu-id="e5362-133">`$BasicTestObject` uses the `Multiply` method.</span></span> <span data-ttu-id="e5362-134">Die ganzen Zahlen werden multipliziert, und das Produkt wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e5362-134">The integers are multiplied and the product is displayed.</span></span>

### <span data-ttu-id="e5362-135">Beispiel 2: Untersuchen eines hinzugefügten Typs</span><span class="sxs-lookup"><span data-stu-id="e5362-135">Example 2: Examine an added type</span></span>

<span data-ttu-id="e5362-136">In diesem Beispiel wird das `Get-Member` -Cmdlet verwendet, um die Objekte zu überprüfen, die `Add-Type` `New-Object` in **Beispiel 1** erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="e5362-136">This example uses the `Get-Member` cmdlet to examine the objects that the `Add-Type` and `New-Object` cmdlets created in **Example 1** .</span></span>

```powershell
[BasicTest] | Get-Member
```

```Output
   TypeName: System.RuntimeType

Name                 MemberType Definition
----                 ---------- ----------
AsType               Method     type AsType()
Clone                Method     System.Object Clone(), System.Object ICloneable.Clone()
Equals               Method     bool Equals(System.Object obj), bool Equals(type o)
FindInterfaces       Method     type[] FindInterfaces(System.Reflection.TypeFilter filter...
...
```

```powershell
[BasicTest] | Get-Member -Static
```

```Output
  TypeName: BasicTest

Name            MemberType Definition
----            ---------- ----------
Add             Method     static int Add(int a, int b)
Equals          Method     static bool Equals(System.Object objA, System.Object objB)
new             Method     BasicTest new()
ReferenceEquals Method     static bool ReferenceEquals(System.Object objA, System.Object objB)
```

```powershell
$BasicTestObject | Get-Member
```

```Output
   TypeName: BasicTest

Name        MemberType Definition
----        ---------- ----------
Equals      Method     bool Equals(System.Object obj)
GetHashCode Method     int GetHashCode()
GetType     Method     type GetType()
Multiply    Method     int Multiply(int a, int b)
ToString    Method     string ToString()
```

<span data-ttu-id="e5362-137">`Get-Member`Mit dem-Cmdlet werden der Typ und die Member der **basictest** -Klasse abgerufen, die `Add-Type` der Sitzung hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="e5362-137">The `Get-Member` cmdlet gets the type and members of the **BasicTest** class that `Add-Type` added to the session.</span></span> <span data-ttu-id="e5362-138">Der `Get-Member` Befehl zeigt, dass es sich um ein **System. RuntimeType** -Objekt handelt, das von der **System. Object** -Klasse abgeleitet ist.</span><span class="sxs-lookup"><span data-stu-id="e5362-138">The `Get-Member` command reveals that it's a **System.RuntimeType** object, which is derived from the **System.Object** class.</span></span>

<span data-ttu-id="e5362-139">Der `Get-Member` **static** -Parameter ruft die statischen Eigenschaften und Methoden der **basictest** -Klasse ab.</span><span class="sxs-lookup"><span data-stu-id="e5362-139">The `Get-Member` **Static** parameter gets the static properties and methods of the **BasicTest** class.</span></span> <span data-ttu-id="e5362-140">Die Ausgabe zeigt, dass die- `Add` Methode enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="e5362-140">The output shows that the `Add` method is included.</span></span>

<span data-ttu-id="e5362-141">Das- `Get-Member` Cmdlet ruft die Member des-Objekts ab, das in der Variablen gespeichert ist `$BasicTestObject` .</span><span class="sxs-lookup"><span data-stu-id="e5362-141">The `Get-Member` cmdlet gets the members of the object stored in the `$BasicTestObject` variable.</span></span>
<span data-ttu-id="e5362-142">`$BasicTestObject` wurde mithilfe des `New-Object` Cmdlets mit der **basictest** -Klasse erstellt.</span><span class="sxs-lookup"><span data-stu-id="e5362-142">`$BasicTestObject` was created by using the `New-Object` cmdlet with the **BasicTest** class.</span></span> <span data-ttu-id="e5362-143">Die Ausgabe zeigt, dass der Wert der `$BasicTestObject` Variablen eine Instanz der **basictest** -Klasse ist und einen Member mit dem Namen enthält `Multiply` .</span><span class="sxs-lookup"><span data-stu-id="e5362-143">The output reveals that the value of the `$BasicTestObject` variable is an instance of the **BasicTest** class and that it includes a member called `Multiply`.</span></span>

### <span data-ttu-id="e5362-144">Beispiel 3: Hinzufügen von Typen aus einer Assembly</span><span class="sxs-lookup"><span data-stu-id="e5362-144">Example 3: Add types from an assembly</span></span>

<span data-ttu-id="e5362-145">In diesem Beispiel werden die Klassen der- `Accessibility.dll` Assembly der aktuellen Sitzung hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="e5362-145">This example adds the classes from the `Accessibility.dll` assembly to the current session.</span></span>

```powershell
$AccType = Add-Type -AssemblyName "accessib*" -PassThru
```

<span data-ttu-id="e5362-146">Die- `$AccType` Variable speichert ein mit dem- `Add-Type` Cmdlet erstelltes Objekt.</span><span class="sxs-lookup"><span data-stu-id="e5362-146">The `$AccType` variable stores an object created with the `Add-Type` cmdlet.</span></span> <span data-ttu-id="e5362-147">`Add-Type` verwendet den **AssemblyName** -Parameter, um den Namen der Assembly anzugeben.</span><span class="sxs-lookup"><span data-stu-id="e5362-147">`Add-Type` uses the **AssemblyName** parameter to specify the name of the assembly.</span></span> <span data-ttu-id="e5362-148">Mit dem Platzhalter Zeichen Sternchen ( `*` ) können Sie die richtige Assembly auch dann erhalten, wenn Sie den Namen oder die Schreibweise nicht sicher sind.</span><span class="sxs-lookup"><span data-stu-id="e5362-148">The asterisk (`*`) wildcard character allows you to get the correct assembly even when you aren't sure of the name or its spelling.</span></span> <span data-ttu-id="e5362-149">Der **passthru** -Parameter generiert-Objekte, die die Klassen darstellen, die der Sitzung hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="e5362-149">The **PassThru** parameter generates objects that represent the classes that are added to the session.</span></span>

### <span data-ttu-id="e5362-150">Beispiel 4: Abrufen von systemeigenen Windows-APIs</span><span class="sxs-lookup"><span data-stu-id="e5362-150">Example 4: Call native Windows APIs</span></span>

<span data-ttu-id="e5362-151">In diesem Beispiel wird veranschaulicht, wie Native Windows-APIs in PowerShell aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="e5362-151">This example demonstrates how to call native Windows APIs in PowerShell.</span></span> <span data-ttu-id="e5362-152">`Add-Type` verwendet den Platt Form Aufruf-Mechanismus (P/aufrufen), um eine Funktion in über `User32.dll` PowerShell aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="e5362-152">`Add-Type` uses the Platform Invoke (P/Invoke) mechanism to call a function in `User32.dll` from PowerShell.</span></span> <span data-ttu-id="e5362-153">Dieses Beispiel funktioniert nur auf Computern, auf denen das Windows-Betriebssystem ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e5362-153">This example only works on computers running the Windows operating system.</span></span>

```powershell
$Signature = @"
[DllImport("user32.dll")]public static extern bool ShowWindowAsync(IntPtr hWnd, int nCmdShow);
"@

$ShowWindowAsync = Add-Type -MemberDefinition $Signature -Name "Win32ShowWindowAsync" -Namespace Win32Functions -PassThru

# Minimize the PowerShell console

$ShowWindowAsync::ShowWindowAsync((Get-Process -Id $pid).MainWindowHandle, 2)

# Restore the PowerShell console

$ShowWindowAsync::ShowWindowAsync((Get-Process -Id $Pid).MainWindowHandle, 4)
```

<span data-ttu-id="e5362-154">Die `$Signature` Variable speichert die c#-Signatur der `ShowWindowAsync` Funktion.</span><span class="sxs-lookup"><span data-stu-id="e5362-154">The `$Signature` variable stores the C# signature of the `ShowWindowAsync` function.</span></span> <span data-ttu-id="e5362-155">Um sicherzustellen, dass die resultierende Methode in einer PowerShell-Sitzung sichtbar ist, wurde das- `public` Schlüsselwort der Standard Signatur hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="e5362-155">To ensure that the resulting method will be visible in a PowerShell session, the `public` keyword was added to the standard signature.</span></span> <span data-ttu-id="e5362-156">Weitere Informationen finden Sie unter [ShowWindowAsync-Funktion](/windows/win32/api/winuser/nf-winuser-showwindowasync).</span><span class="sxs-lookup"><span data-stu-id="e5362-156">For more information, see [ShowWindowAsync function](/windows/win32/api/winuser/nf-winuser-showwindowasync).</span></span>

<span data-ttu-id="e5362-157">Die- `$ShowWindowAsync` Variable speichert das-Objekt, das vom `Add-Type` **passthru** -Parameter erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="e5362-157">The `$ShowWindowAsync` variable stores the object created by the `Add-Type` **PassThru** parameter.</span></span>
<span data-ttu-id="e5362-158">Das- `Add-Type` Cmdlet fügt die `ShowWindowAsync` Funktion als statische Methode zur PowerShell-Sitzung hinzu.</span><span class="sxs-lookup"><span data-stu-id="e5362-158">The `Add-Type` cmdlet adds the `ShowWindowAsync` function to the PowerShell session as a static method.</span></span> <span data-ttu-id="e5362-159">Der Befehl verwendet den Parameter " **Membership Definition** ", um die in der Variablen gespeicherte Methoden Definition anzugeben `$Signature` .</span><span class="sxs-lookup"><span data-stu-id="e5362-159">The command uses the **MemberDefinition** parameter to specify the method definition saved in the `$Signature` variable.</span></span> <span data-ttu-id="e5362-160">Der Befehl verwendet die Parameter **Name** und **Namespace** , um einen Namen und einen Namespace für die Klasse anzugeben.</span><span class="sxs-lookup"><span data-stu-id="e5362-160">The command uses the **Name** and **Namespace** parameters to specify a name and namespace for the class.</span></span> <span data-ttu-id="e5362-161">Der **passthru** -Parameter generiert ein Objekt, das die Typen darstellt.</span><span class="sxs-lookup"><span data-stu-id="e5362-161">The **PassThru** parameter generates an object that represents the types.</span></span>

<span data-ttu-id="e5362-162">Die neue `ShowWindowAsync` statische Methode wird in den Befehlen verwendet, um die PowerShell-Konsole zu minimieren und wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="e5362-162">The new `ShowWindowAsync` static method is used in the commands to minimize and restore the PowerShell console.</span></span> <span data-ttu-id="e5362-163">Die-Methode nimmt zwei Parameter an: das Fenster Handle und eine ganze Zahl, die angibt, wie das Fenster angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="e5362-163">The method takes two parameters: the window handle, and an integer that specifies how the window is displayed.</span></span>

<span data-ttu-id="e5362-164">Um die PowerShell-Konsole zu minimieren, `ShowWindowAsync` verwendet das `Get-Process` Cmdlet mit der `$PID` automatischen Variablen, um den Prozess zu erhalten, der die aktuelle PowerShell-Sitzung gehostet.</span><span class="sxs-lookup"><span data-stu-id="e5362-164">To minimize the PowerShell console, `ShowWindowAsync` uses the `Get-Process` cmdlet with the `$PID` automatic variable to get the process that is hosting the current PowerShell session.</span></span> <span data-ttu-id="e5362-165">Anschließend wird die **MainWindowHandle** -Eigenschaft des aktuellen Prozesses und der Wert verwendet `2` , der den- `SW_MINIMIZE` Wert darstellt.</span><span class="sxs-lookup"><span data-stu-id="e5362-165">Then it uses the **MainWindowHandle** property of the current process and a value of `2`, which represents the `SW_MINIMIZE` value.</span></span>

<span data-ttu-id="e5362-166">Um das Fenster wiederherzustellen, `ShowWindowAsync` verwendet den Wert `4` für die Fensterposition, die den `SW_RESTORE` Wert darstellt.</span><span class="sxs-lookup"><span data-stu-id="e5362-166">To restore the window, `ShowWindowAsync` uses a value of `4` for the window position, which represents the `SW_RESTORE` value.</span></span>

<span data-ttu-id="e5362-167">Um das Fenster zu maximieren, verwenden Sie den Wert von `3` , der darstellt `SW_MAXIMIZE` .</span><span class="sxs-lookup"><span data-stu-id="e5362-167">To maximize the window, use the value of `3` that represents `SW_MAXIMIZE`.</span></span>

### <span data-ttu-id="e5362-168">Beispiel 5: Hinzufügen eines Typs aus einer Visual Basic Datei</span><span class="sxs-lookup"><span data-stu-id="e5362-168">Example 5: Add a type from a Visual Basic file</span></span>

<span data-ttu-id="e5362-169">In diesem Beispiel wird das `Add-Type` -Cmdlet verwendet, um die in der Datei definierte **vbfromfile** -Klasse `Hello.vb` der aktuellen Sitzung hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="e5362-169">This example uses the `Add-Type` cmdlet to add the **VBFromFile** class that's defined in the `Hello.vb` file to the current session.</span></span> <span data-ttu-id="e5362-170">Der Text der `Hello.vb` Datei wird in der Befehlsausgabe angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e5362-170">The text of the `Hello.vb` file is shown in the command output.</span></span>

```powershell
Add-Type -Path "C:\PS-Test\Hello.vb"
[VBFromFile]::SayHello(", World")

# From Hello.vb

Public Class VBFromFile
  Public Shared Function SayHello(sourceName As String) As String
    Dim myValue As String = "Hello"
    return myValue + sourceName
  End Function
End Class
```

```Output
Hello, World
```

<span data-ttu-id="e5362-171">`Add-Type` verwendet den **path** -Parameter, um die Quelldatei anzugeben, `Hello.vb` und fügt den in der Datei definierten Typ hinzu.</span><span class="sxs-lookup"><span data-stu-id="e5362-171">`Add-Type` uses the **Path** parameter to specify the source file, `Hello.vb`, and adds the type defined in the file.</span></span> <span data-ttu-id="e5362-172">Die- `SayHello` Funktion wird als statische Methode der **vbfromfile** -Klasse aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="e5362-172">The `SayHello` function is called as a static method of the **VBFromFile** class.</span></span>

### <span data-ttu-id="e5362-173">Beispiel 6: Hinzufügen einer Klasse mit JScript.net</span><span class="sxs-lookup"><span data-stu-id="e5362-173">Example 6: Add a class with JScript.NET</span></span>

<span data-ttu-id="e5362-174">In diesem Beispiel wird JScript.NET verwendet, um eine neue Klasse ( **frechteck** ) in der PowerShell-Sitzung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e5362-174">This example uses JScript.NET to create a new class, **FRectangle** , in your PowerShell session.</span></span>

```powershell
Add-Type @'
 class FRectangle {
   var Length : double;
   var Height : double;
   function Perimeter() : double {
       return (Length + Height) * 2; }
   function Area() : double {
       return Length * Height;  } }
'@ -Language JScript

$rect = [FRectangle]::new()
$rect
```

```Output
Length Height
------ ------
     0      0
```

### <span data-ttu-id="e5362-175">Beispiel 7: Hinzufügen eines F #-Compilers</span><span class="sxs-lookup"><span data-stu-id="e5362-175">Example 7: Add an F# compiler</span></span>

<span data-ttu-id="e5362-176">In diesem Beispiel wird gezeigt, wie Sie mit dem `Add-Type` Cmdlet ihrer PowerShell-Sitzung einen F #-Code Compiler hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="e5362-176">This example shows how to use the `Add-Type` cmdlet to add an F# code compiler to your PowerShell session.</span></span> <span data-ttu-id="e5362-177">Um dieses Beispiel in PowerShell auszuführen, müssen Sie über das verfügen, das `FSharp.Compiler.CodeDom.dll` mit der Sprache F # installiert ist.</span><span class="sxs-lookup"><span data-stu-id="e5362-177">To run this example in PowerShell, you must have the `FSharp.Compiler.CodeDom.dll` that is installed with the F# language.</span></span>

```powershell
Add-Type -Path "FSharp.Compiler.CodeDom.dll"
$Provider = New-Object Microsoft.FSharp.Compiler.CodeDom.FSharpCodeProvider
$FSharpCode = @"
let rec loop n =if n <= 0 then () else beginprint_endline (string_of_int n);loop (n-1)end
"@
$FSharpType = Add-Type -TypeDefinition $FSharpCode -CodeDomProvider $Provider -PassThru |
   Where-Object { $_.IsPublic }
$FSharpType::loop(4)
```

```Output
4
3
2
1
```

<span data-ttu-id="e5362-178">`Add-Type` verwendet den **path** -Parameter, um eine Assembly anzugeben, und ruft die Typen in der Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="e5362-178">`Add-Type` uses the **Path** parameter to specify an assembly and gets the types in the assembly.</span></span>
<span data-ttu-id="e5362-179">`New-Object` erstellt eine Instanz des F #-Code Anbieters und speichert das Ergebnis in der `$Provider` Variablen.</span><span class="sxs-lookup"><span data-stu-id="e5362-179">`New-Object` creates an instance of the F# code provider and saves the result in the `$Provider` variable.</span></span> <span data-ttu-id="e5362-180">Die- `$FSharpCode` Variable speichert den F #-Code, der die **Schleifen** Methode definiert.</span><span class="sxs-lookup"><span data-stu-id="e5362-180">The `$FSharpCode` variable saves the F# code that defines the **Loop** method.</span></span>

<span data-ttu-id="e5362-181">Die- `$FSharpType` Variable speichert die Ergebnisse des- `Add-Type` Cmdlets, das die in definierten öffentlichen Typen speichert `$FSharpCode` .</span><span class="sxs-lookup"><span data-stu-id="e5362-181">The the `$FSharpType` variable stores the results of the `Add-Type` cmdlet that saves the public types defined in `$FSharpCode`.</span></span> <span data-ttu-id="e5362-182">Der **TypeDefinition** -Parameter gibt den Quellcode an, der die Typen definiert.</span><span class="sxs-lookup"><span data-stu-id="e5362-182">The **TypeDefinition** parameter specifies the source code that defines the types.</span></span> <span data-ttu-id="e5362-183">Der **CodeDomProvider** -Parameter gibt den Quellcodecompiler an.</span><span class="sxs-lookup"><span data-stu-id="e5362-183">The **CodeDomProvider** parameter specifies the source code compiler.</span></span> <span data-ttu-id="e5362-184">Der **passthru** -Parameter weist `Add-Type` an, ein **Lauf** Zeit Objekt zurückzugeben, das die Typen darstellt.</span><span class="sxs-lookup"><span data-stu-id="e5362-184">The **PassThru** parameter directs `Add-Type` to return a **Runtime** object that represents the types.</span></span>
<span data-ttu-id="e5362-185">Die Objekte werden über die Pipeline an das `Where-Object` Cmdlet gesendet, das nur die öffentlichen Typen zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="e5362-185">The objects are sent down the pipeline to the `Where-Object` cmdlet, which returns only the public types.</span></span> <span data-ttu-id="e5362-186">Das **Where-Object-** Cmdlet wird verwendet, da der F #-Anbieter nicht öffentliche Typen generiert, um den resultierenden öffentlichen Typ zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="e5362-186">The **Where-Object** cmdlet is used because the F# provider generates non-public types to support the resulting public type.</span></span>

<span data-ttu-id="e5362-187">Die Schleifen Methode wird als statische Methode des in der Variablen gespeicherten Typs aufgerufen `$FSharpType` .</span><span class="sxs-lookup"><span data-stu-id="e5362-187">The Loop method is called as a static method of the type stored in the `$FSharpType` variable.</span></span>

## <span data-ttu-id="e5362-188">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e5362-188">PARAMETERS</span></span>

### <span data-ttu-id="e5362-189">-AssemblyName</span><span class="sxs-lookup"><span data-stu-id="e5362-189">-AssemblyName</span></span>

<span data-ttu-id="e5362-190">Gibt den Namen einer Assembly an, die die Typen enthält.</span><span class="sxs-lookup"><span data-stu-id="e5362-190">Specifies the name of an assembly that includes the types.</span></span> <span data-ttu-id="e5362-191">`Add-Type` nimmt die Typen aus der angegebenen Assembly.</span><span class="sxs-lookup"><span data-stu-id="e5362-191">`Add-Type` takes the types from the specified assembly.</span></span> <span data-ttu-id="e5362-192">Dieser Parameter ist erforderlich, wenn Sie Typen auf der Grundlage eines Assemblynamens erstellen.</span><span class="sxs-lookup"><span data-stu-id="e5362-192">This parameter is required when you're creating types based on an assembly name.</span></span>

<span data-ttu-id="e5362-193">Geben Sie den vollständigen oder einfachen Namen einer Assembly ein, die auch als partieller Name bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="e5362-193">Enter the full or simple name, also known as the partial name, of an assembly.</span></span> <span data-ttu-id="e5362-194">Der Assemblyname darf Platzhalterzeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="e5362-194">Wildcard characters are permitted in the assembly name.</span></span> <span data-ttu-id="e5362-195">Wenn Sie einen einfachen oder partiellen Namen eingeben, wird `Add-Type` dieser in den vollständigen Namen aufgelöst, und dann wird der vollständige Name verwendet, um die Assembly zu laden.</span><span class="sxs-lookup"><span data-stu-id="e5362-195">If you enter a simple or partial name, `Add-Type` resolves it to the full name, and then uses the full name to load the assembly.</span></span>

<span data-ttu-id="e5362-196">Dieser Parameter akzeptiert keinen Pfad oder Dateinamen.</span><span class="sxs-lookup"><span data-stu-id="e5362-196">This parameter doesn't accept a path or a file name.</span></span> <span data-ttu-id="e5362-197">Um den Pfad zur DLL-Datei (Dynamic Link Library) der Assembly einzugeben, verwenden Sie den **path** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="e5362-197">To enter the path to the assembly dynamic-link library (DLL) file, use the **Path** parameter.</span></span>

```yaml
Type: System.String[]
Parameter Sets: FromAssemblyName
Aliases: AN

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="e5362-198">-CodeDom Provider</span><span class="sxs-lookup"><span data-stu-id="e5362-198">-CodeDomProvider</span></span>

<span data-ttu-id="e5362-199">Gibt einen Code-Generator oder Compiler an.</span><span class="sxs-lookup"><span data-stu-id="e5362-199">Specifies a code generator or compiler.</span></span> <span data-ttu-id="e5362-200">`Add-Type` verwendet den angegebenen Compiler zum Kompilieren des Quellcodes.</span><span class="sxs-lookup"><span data-stu-id="e5362-200">`Add-Type` uses the specified compiler to compile the source code.</span></span> <span data-ttu-id="e5362-201">Der Standardwert ist der c#-Compiler.</span><span class="sxs-lookup"><span data-stu-id="e5362-201">The default is the C# compiler.</span></span> <span data-ttu-id="e5362-202">Verwenden Sie diesen Parameter, wenn Sie eine Sprache verwenden, die mit dem **Language** -Parameter nicht angegeben werden kann.</span><span class="sxs-lookup"><span data-stu-id="e5362-202">Use this parameter if you're using a language that can't be specified by using the **Language** parameter.</span></span> <span data-ttu-id="e5362-203">Der von Ihnen angegebene **CodeDom Provider** muss in der Lage sein, Assemblys aus dem Quellcode zu generieren.</span><span class="sxs-lookup"><span data-stu-id="e5362-203">The **CodeDomProvider** that you specify must be able to generate assemblies from source code.</span></span>

```yaml
Type: System.CodeDom.Compiler.CodeDomProvider
Parameter Sets: FromSource, FromMember
Aliases: Provider

Required: False
Position: Named
Default value: C# compiler
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e5362-204">-CompilerParameters</span><span class="sxs-lookup"><span data-stu-id="e5362-204">-CompilerParameters</span></span>

<span data-ttu-id="e5362-205">Gibt die Optionen für den Quellcodecompiler an.</span><span class="sxs-lookup"><span data-stu-id="e5362-205">Specifies the options for the source code compiler.</span></span> <span data-ttu-id="e5362-206">Diese Optionen werden ohne Revision an den Compiler gesendet.</span><span class="sxs-lookup"><span data-stu-id="e5362-206">These options are sent to the compiler without revision.</span></span>

<span data-ttu-id="e5362-207">Mit diesem Parameter können Sie den Compiler anweisen, eine ausführbare Datei zu generieren, Ressourcen einzubetten oder Befehlszeilenoptionen (z. b. die Option) festzulegen `/unsafe` .</span><span class="sxs-lookup"><span data-stu-id="e5362-207">This parameter allows you to direct the compiler to generate an executable file, embed resources, or set command-line options, such as the `/unsafe` option.</span></span> <span data-ttu-id="e5362-208">Dieser Parameter implementiert die **CompilerParameters** -Klasse, **System. CodeDom. Compiler. CompilerParameters** .</span><span class="sxs-lookup"><span data-stu-id="e5362-208">This parameter implements the **CompilerParameters** class, **System.CodeDom.Compiler.CompilerParameters** .</span></span>

<span data-ttu-id="e5362-209">Der **CompilerParameters** -Parameter und der **referencedassemblyparameter** können nicht im selben Befehl verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e5362-209">You can't use the **CompilerParameters** and **ReferencedAssemblies** parameters in the same command.</span></span>

```yaml
Type: System.CodeDom.Compiler.CompilerParameters
Parameter Sets: FromSource, FromMember, FromPath, FromLiteralPath
Aliases: CP

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e5362-210">-Ignorewarning</span><span class="sxs-lookup"><span data-stu-id="e5362-210">-IgnoreWarnings</span></span>

<span data-ttu-id="e5362-211">Ignoriert Compilerwarnungen.</span><span class="sxs-lookup"><span data-stu-id="e5362-211">Ignores compiler warnings.</span></span> <span data-ttu-id="e5362-212">Verwenden Sie diesen Parameter, um zu verhindern, dass `Add-Type` Compilerwarnungen als Fehler behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="e5362-212">Use this parameter to prevent `Add-Type` from handling compiler warnings as errors.</span></span>

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

### <span data-ttu-id="e5362-213">-Sprache</span><span class="sxs-lookup"><span data-stu-id="e5362-213">-Language</span></span>

<span data-ttu-id="e5362-214">Gibt die Sprache an, die im Quellcode verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e5362-214">Specifies the language that is used in the source code.</span></span> <span data-ttu-id="e5362-215">Das `Add-Type` Cmdlet verwendet den Wert dieses Parameters, um den entsprechenden **CodeDom Provider** auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="e5362-215">The `Add-Type` cmdlet uses the value of this parameter to select the appropriate **CodeDomProvider** .</span></span> <span data-ttu-id="e5362-216">CSharp ist der Standardwert.</span><span class="sxs-lookup"><span data-stu-id="e5362-216">CSharp is the default value.</span></span> <span data-ttu-id="e5362-217">Die zulässigen Werte für diesen Parameter lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="e5362-217">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="e5362-218">CSharp</span><span class="sxs-lookup"><span data-stu-id="e5362-218">CSharp</span></span>
- <span data-ttu-id="e5362-219">CSharpVersion2</span><span class="sxs-lookup"><span data-stu-id="e5362-219">CSharpVersion2</span></span>
- <span data-ttu-id="e5362-220">CSharpVersion3</span><span class="sxs-lookup"><span data-stu-id="e5362-220">CSharpVersion3</span></span>
- <span data-ttu-id="e5362-221">JScript</span><span class="sxs-lookup"><span data-stu-id="e5362-221">JScript</span></span>
- <span data-ttu-id="e5362-222">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e5362-222">VisualBasic</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.Language
Parameter Sets: FromSource, FromMember
Aliases:
Accepted values: CSharp, CSharpVersion2, CSharpVersion3, JScript, VisualBasic

Required: False
Position: Named
Default value: CSharp
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e5362-223">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="e5362-223">-LiteralPath</span></span>

<span data-ttu-id="e5362-224">Gibt den Pfad zu Quellcodedateien oder Assembly-DLL-Dateien an, die die Typen enthalten.</span><span class="sxs-lookup"><span data-stu-id="e5362-224">Specifies the path to source code files or assembly DLL files that contain the types.</span></span> <span data-ttu-id="e5362-225">Im Gegensatz zu **path** wird der Wert des **literalpath** -Parameters genau so verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="e5362-225">Unlike **Path** , the value of the **LiteralPath** parameter is used exactly as it's typed.</span></span> <span data-ttu-id="e5362-226">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="e5362-226">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="e5362-227">Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="e5362-227">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="e5362-228">Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="e5362-228">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: FromLiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e5362-229">-Mitglieddefinition</span><span class="sxs-lookup"><span data-stu-id="e5362-229">-MemberDefinition</span></span>

<span data-ttu-id="e5362-230">Gibt neue Eigenschaften oder Methoden für die Klasse an.</span><span class="sxs-lookup"><span data-stu-id="e5362-230">Specifies new properties or methods for the class.</span></span> <span data-ttu-id="e5362-231">`Add-Type` generiert den Vorlagen Code, der zur Unterstützung der Eigenschaften oder Methoden erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="e5362-231">`Add-Type` generates the template code that is required to support the properties or methods.</span></span>

<span data-ttu-id="e5362-232">Unter Windows können Sie diese Funktion verwenden, um Platt Form Aufrufe (P/aufrufen) von nicht verwalteten Funktionen in PowerShell durchführen.</span><span class="sxs-lookup"><span data-stu-id="e5362-232">On Windows, you can use this feature to make Platform Invoke (P/Invoke) calls to unmanaged functions in PowerShell.</span></span>

```yaml
Type: System.String[]
Parameter Sets: FromMember
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e5362-233">-Name</span><span class="sxs-lookup"><span data-stu-id="e5362-233">-Name</span></span>

<span data-ttu-id="e5362-234">Gibt den Namen der zu erstellenden Klasse an.</span><span class="sxs-lookup"><span data-stu-id="e5362-234">Specifies the name of the class to create.</span></span> <span data-ttu-id="e5362-235">Dieser Parameter ist beim Generieren eines Typs aus einer Memberdefinition erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e5362-235">This parameter is required when generating a type from a member definition.</span></span>

<span data-ttu-id="e5362-236">Der Typname und der Namespace müssen innerhalb einer Sitzung eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="e5362-236">The type name and namespace must be unique within a session.</span></span> <span data-ttu-id="e5362-237">Ein Typ kann nicht entladen oder geändert werden.</span><span class="sxs-lookup"><span data-stu-id="e5362-237">You can't unload a type or change it.</span></span>
<span data-ttu-id="e5362-238">Wenn Sie den Code für einen Typ ändern möchten, müssen Sie den Namen ändern oder eine neue PowerShell-Sitzung starten.</span><span class="sxs-lookup"><span data-stu-id="e5362-238">To change the code for a type, you must change the name or start a new PowerShell session.</span></span>
<span data-ttu-id="e5362-239">Andernfalls führt der Befehl zu einem Fehler.</span><span class="sxs-lookup"><span data-stu-id="e5362-239">Otherwise, the command fails.</span></span>

```yaml
Type: System.String
Parameter Sets: FromMember
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e5362-240">-Namespace</span><span class="sxs-lookup"><span data-stu-id="e5362-240">-Namespace</span></span>

<span data-ttu-id="e5362-241">Gibt einen Namespace für den Typ an.</span><span class="sxs-lookup"><span data-stu-id="e5362-241">Specifies a namespace for the type.</span></span>

<span data-ttu-id="e5362-242">Wenn dieser Parameter nicht im Befehl enthalten ist, wird der Typ im **Microsoft. PowerShell. Commands. AddType. autogeneratedtypes** -Namespace erstellt.</span><span class="sxs-lookup"><span data-stu-id="e5362-242">If this parameter isn't included in the command, the type is created in the **Microsoft.PowerShell.Commands.AddType.AutoGeneratedTypes** namespace.</span></span> <span data-ttu-id="e5362-243">Wenn der Parameter im Befehl mit einem leeren Zeichen folgen Wert oder einem Wert von enthalten ist `$Null` , wird der Typ im globalen Namespace generiert.</span><span class="sxs-lookup"><span data-stu-id="e5362-243">If the parameter is included in the command with an empty string value or a value of `$Null`, the type is generated in the global namespace.</span></span>

```yaml
Type: System.String
Parameter Sets: FromMember
Aliases: NS

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e5362-244">-OutputAssembly</span><span class="sxs-lookup"><span data-stu-id="e5362-244">-OutputAssembly</span></span>

<span data-ttu-id="e5362-245">Generiert eine DLL-Datei für die Assembly mit dem angegebenen Namen an dem Speicherort.</span><span class="sxs-lookup"><span data-stu-id="e5362-245">Generates a DLL file for the assembly with the specified name in the location.</span></span> <span data-ttu-id="e5362-246">Geben Sie einen optionalen Pfad und Dateinamen ein.</span><span class="sxs-lookup"><span data-stu-id="e5362-246">Enter an optional path and file name.</span></span> <span data-ttu-id="e5362-247">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="e5362-247">Wildcard characters are permitted.</span></span> <span data-ttu-id="e5362-248">Standardmäßig `Add-Type` generiert die Assembly nur im Arbeitsspeicher.</span><span class="sxs-lookup"><span data-stu-id="e5362-248">By default, `Add-Type` generates the assembly only in memory.</span></span>

```yaml
Type: System.String
Parameter Sets: FromSource, FromMember, FromPath, FromLiteralPath
Aliases: OA

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="e5362-249">-OutputType</span><span class="sxs-lookup"><span data-stu-id="e5362-249">-OutputType</span></span>

<span data-ttu-id="e5362-250">Gibt den Ausgabetyp der Ausgabeassembly an.</span><span class="sxs-lookup"><span data-stu-id="e5362-250">Specifies the output type of the output assembly.</span></span> <span data-ttu-id="e5362-251">Standardmäßig wird kein Ausgabetyp angegeben.</span><span class="sxs-lookup"><span data-stu-id="e5362-251">By default, no output type is specified.</span></span> <span data-ttu-id="e5362-252">Dieser Parameter gilt nur, wenn eine Ausgabeassembly im Befehl angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="e5362-252">This parameter is valid only when an output assembly is specified in the command.</span></span> <span data-ttu-id="e5362-253">Weitere Informationen zu den Werten finden Sie unter [outputassemblytype-Enumeration](/dotnet/api/microsoft.powershell.commands.outputassemblytype).</span><span class="sxs-lookup"><span data-stu-id="e5362-253">For more information about the values, see [OutputAssemblyType Enumeration](/dotnet/api/microsoft.powershell.commands.outputassemblytype).</span></span>

<span data-ttu-id="e5362-254">Die zulässigen Werte für diesen Parameter lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="e5362-254">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="e5362-255">ConsoleApplication</span><span class="sxs-lookup"><span data-stu-id="e5362-255">ConsoleApplication</span></span>
- <span data-ttu-id="e5362-256">Bibliothek</span><span class="sxs-lookup"><span data-stu-id="e5362-256">Library</span></span>
- <span data-ttu-id="e5362-257">Datei WindowsApplication</span><span class="sxs-lookup"><span data-stu-id="e5362-257">WindowsApplication</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.OutputAssemblyType
Parameter Sets: FromSource, FromMember, FromPath, FromLiteralPath
Aliases: OT
Accepted values: ConsoleApplication, Library, WindowsApplication

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e5362-258">-PassThru</span><span class="sxs-lookup"><span data-stu-id="e5362-258">-PassThru</span></span>

<span data-ttu-id="e5362-259">Gibt ein **System.Runtime** -Objekt zurück, das die Typen darstellt, die hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="e5362-259">Returns a **System.Runtime** object that represents the types that were added.</span></span> <span data-ttu-id="e5362-260">Standardmäßig generiert dieses Cmdlet keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="e5362-260">By default, this cmdlet doesn't generate any output.</span></span>

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

### <span data-ttu-id="e5362-261">-Path</span><span class="sxs-lookup"><span data-stu-id="e5362-261">-Path</span></span>

<span data-ttu-id="e5362-262">Gibt den Pfad zu Quellcodedateien oder Assembly-DLL-Dateien an, die die Typen enthalten.</span><span class="sxs-lookup"><span data-stu-id="e5362-262">Specifies the path to source code files or assembly DLL files that contain the types.</span></span>

<span data-ttu-id="e5362-263">Wenn Sie Quell Code Dateien übermitteln, `Add-Type` kompiliert den Code in den Dateien und erstellt eine in-Memory-Assembly der Typen.</span><span class="sxs-lookup"><span data-stu-id="e5362-263">If you submit source code files, `Add-Type` compiles the code in the files and creates an in-memory assembly of the types.</span></span> <span data-ttu-id="e5362-264">Die im **Pfad** Wert angegebene Dateinamenerweiterung bestimmt den Compiler, der von `Add-Type` verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e5362-264">The file name extension specified in the value of **Path** determines the compiler that `Add-Type` uses.</span></span>

<span data-ttu-id="e5362-265">Wenn Sie eine Assemblydatei übermitteln, `Add-Type` übernimmt die Typen aus der Assembly.</span><span class="sxs-lookup"><span data-stu-id="e5362-265">If you submit an assembly file, `Add-Type` takes the types from the assembly.</span></span> <span data-ttu-id="e5362-266">Um eine speicherinterne Assembly oder den globalen Assemblycache anzugeben, verwenden Sie den **AssemblyName** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="e5362-266">To specify an in-memory assembly or the global assembly cache, use the **AssemblyName** parameter.</span></span>

```yaml
Type: System.String[]
Parameter Sets: FromPath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e5362-267">-Referencedassemblys</span><span class="sxs-lookup"><span data-stu-id="e5362-267">-ReferencedAssemblies</span></span>

<span data-ttu-id="e5362-268">Gibt die Assemblys an, von denen der Typ abhängig ist.</span><span class="sxs-lookup"><span data-stu-id="e5362-268">Specifies the assemblies upon which the type depends.</span></span> <span data-ttu-id="e5362-269">Standardmäßig `Add-Type` verweist auf `System.dll` und `System.Management.Automation.dll` .</span><span class="sxs-lookup"><span data-stu-id="e5362-269">By default, `Add-Type` references `System.dll` and `System.Management.Automation.dll`.</span></span> <span data-ttu-id="e5362-270">Auf die Assemblys, die Sie mithilfe dieses Parameters angeben, wird zusätzlich zu den Standardassemblys verwiesen.</span><span class="sxs-lookup"><span data-stu-id="e5362-270">The assemblies that you specify by using this parameter are referenced in addition to the default assemblies.</span></span>

<span data-ttu-id="e5362-271">Der **CompilerParameters** -Parameter und der **referencedassemblyparameter** können nicht im selben Befehl verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e5362-271">You can't use the **CompilerParameters** and **ReferencedAssemblies** parameters in the same command.</span></span>

```yaml
Type: System.String[]
Parameter Sets: FromSource, FromMember, FromPath, FromLiteralPath
Aliases: RA

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e5362-272">-TypeDefinition</span><span class="sxs-lookup"><span data-stu-id="e5362-272">-TypeDefinition</span></span>

<span data-ttu-id="e5362-273">Gibt den Quellcode an, der die Typdefinitionen enthält.</span><span class="sxs-lookup"><span data-stu-id="e5362-273">Specifies the source code that contains the type definitions.</span></span> <span data-ttu-id="e5362-274">Geben Sie den Quellcode in einer Zeichenfolge oder einer here-Zeichenfolge ein, oder geben Sie eine Variable ein, die den Quellcode enthält.</span><span class="sxs-lookup"><span data-stu-id="e5362-274">Enter the source code in a string or here-string, or enter a variable that contains the source code.</span></span> <span data-ttu-id="e5362-275">Weitere Informationen zu here-Zeichen folgen finden Sie unter [about_Quoting_Rules](../Microsoft.PowerShell.Core/about/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="e5362-275">For more information about here-strings, see [about_Quoting_Rules](../Microsoft.PowerShell.Core/about/about_Quoting_Rules.md).</span></span>

<span data-ttu-id="e5362-276">Schließen Sie eine Namespacedeklaration in die Typdefinition ein.</span><span class="sxs-lookup"><span data-stu-id="e5362-276">Include a namespace declaration in your type definition.</span></span> <span data-ttu-id="e5362-277">Wenn Sie die Namespacedeklaration weglassen, kann der Typ denselben Namen wie ein anderer Typ oder die Verknüpfung für einen anderen Typ aufweisen, was zu einer unbeabsichtigten Überschreibung führen kann.</span><span class="sxs-lookup"><span data-stu-id="e5362-277">If you omit the namespace declaration, your type might have the same name as another type or the shortcut for another type, causing an unintentional overwrite.</span></span> <span data-ttu-id="e5362-278">Wenn Sie z. b. einen Typ mit dem Namen " **Exception** " definieren, schlagen Skripts, die eine **Ausnahme** als Verknüpfung für **System. Exception** verwenden, fehl.</span><span class="sxs-lookup"><span data-stu-id="e5362-278">For example, if you define a type called **Exception** , scripts that use **Exception** as the shortcut for **System.Exception** will fail.</span></span>

```yaml
Type: System.String
Parameter Sets: FromSource
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e5362-279">-Usingnamespace</span><span class="sxs-lookup"><span data-stu-id="e5362-279">-UsingNamespace</span></span>

<span data-ttu-id="e5362-280">Gibt andere Namespaces an, die für die Klasse erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="e5362-280">Specifies other namespaces that are required for the class.</span></span> <span data-ttu-id="e5362-281">Dies ähnelt dem c#-Schlüsselwort `Using` .</span><span class="sxs-lookup"><span data-stu-id="e5362-281">This is much like the C# keyword, `Using`.</span></span>

<span data-ttu-id="e5362-282">Standardmäßig `Add-Type` verweist auf den **System** -Namespace.</span><span class="sxs-lookup"><span data-stu-id="e5362-282">By default, `Add-Type` references the **System** namespace.</span></span> <span data-ttu-id="e5362-283">Wenn der Parameter " **Membership Definition** " verwendet wird, `Add-Type` verweist standardmäßig auch auf den **System. Runtime. InteropServices** -Namespace.</span><span class="sxs-lookup"><span data-stu-id="e5362-283">When the **MemberDefinition** parameter is used, `Add-Type` also references the **System.Runtime.InteropServices** namespace by default.</span></span> <span data-ttu-id="e5362-284">Auf die Namespaces, die Sie mithilfe der **UsingNamespace** -Parameter hinzufügen, wird zusätzlich zu den standardmäßigen Namespaces verwiesen.</span><span class="sxs-lookup"><span data-stu-id="e5362-284">The namespaces that you add by using the **UsingNamespace** parameter are referenced in addition to the default namespaces.</span></span>

```yaml
Type: System.String[]
Parameter Sets: FromMember
Aliases: Using

Required: False
Position: Named
Default value: System namespace
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e5362-285">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="e5362-285">CommonParameters</span></span>

<span data-ttu-id="e5362-286">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="e5362-286">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e5362-287">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="e5362-287">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e5362-288">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="e5362-288">INPUTS</span></span>

### <span data-ttu-id="e5362-289">Keine</span><span class="sxs-lookup"><span data-stu-id="e5362-289">None</span></span>

<span data-ttu-id="e5362-290">Objekte können nicht über die Pipeline an gesendet werden `Add-Type` .</span><span class="sxs-lookup"><span data-stu-id="e5362-290">You can't send objects down the pipeline to `Add-Type`.</span></span>

## <span data-ttu-id="e5362-291">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="e5362-291">OUTPUTS</span></span>

### <span data-ttu-id="e5362-292">None oder System. Type</span><span class="sxs-lookup"><span data-stu-id="e5362-292">None or System.Type</span></span>

<span data-ttu-id="e5362-293">Wenn Sie den **passthru** -Parameter verwenden, `Add-Type` gibt ein **System. Type** -Objekt zurück, das den neuen Typ darstellt.</span><span class="sxs-lookup"><span data-stu-id="e5362-293">When you use the **PassThru** parameter, `Add-Type` returns a **System.Type** object that represents the new type.</span></span> <span data-ttu-id="e5362-294">Andernfalls generiert dieses Cmdlet keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="e5362-294">Otherwise, this cmdlet doesn't generate any output.</span></span>

## <span data-ttu-id="e5362-295">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="e5362-295">NOTES</span></span>

<span data-ttu-id="e5362-296">Die Typen, die Sie hinzufügen, sind nur in der aktuellen Sitzung vorhanden.</span><span class="sxs-lookup"><span data-stu-id="e5362-296">The types that you add exist only in the current session.</span></span> <span data-ttu-id="e5362-297">Um die Typen in allen Sitzungen zu verwenden, fügen Sie Sie Ihrem PowerShell-Profil hinzu.</span><span class="sxs-lookup"><span data-stu-id="e5362-297">To use the types in all sessions, add them to your PowerShell profile.</span></span> <span data-ttu-id="e5362-298">Weitere Informationen zum Profil finden Sie unter [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="e5362-298">For more information about the profile, see [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).</span></span>

<span data-ttu-id="e5362-299">Typnamen und Namespaces müssen innerhalb einer Sitzung eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="e5362-299">Type names and namespaces must be unique within a session.</span></span> <span data-ttu-id="e5362-300">Ein Typ kann nicht entladen oder geändert werden.</span><span class="sxs-lookup"><span data-stu-id="e5362-300">You can't unload a type or change it.</span></span> <span data-ttu-id="e5362-301">Wenn Sie den Code für einen Typ ändern müssen, müssen Sie den Namen ändern oder eine neue PowerShell-Sitzung starten.</span><span class="sxs-lookup"><span data-stu-id="e5362-301">If you need to change the code for a type, you must change the name or start a new PowerShell session.</span></span>
<span data-ttu-id="e5362-302">Andernfalls führt der Befehl zu einem Fehler.</span><span class="sxs-lookup"><span data-stu-id="e5362-302">Otherwise, the command fails.</span></span>

<span data-ttu-id="e5362-303">Die **CodeDom Provider** -Klasse für einige Sprachen, z. b. IronPython und j#, generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="e5362-303">The **CodeDomProvider** class for some languages, such as IronPython and J#, doesn't generate output.</span></span> <span data-ttu-id="e5362-304">Daher können in diesen Sprachen geschriebene Typen nicht mit verwendet werden `Add-Type` .</span><span class="sxs-lookup"><span data-stu-id="e5362-304">As a result, types written in these languages can't be used with `Add-Type`.</span></span>

<span data-ttu-id="e5362-305">Dieses Cmdlet basiert auf der Microsoft .NET Framework- [CodeDom Provider-Klasse](/dotnet/api/system.codedom.compiler.codedomprovider).</span><span class="sxs-lookup"><span data-stu-id="e5362-305">This cmdlet is based on the Microsoft .NET Framework [CodeDomProvider Class](/dotnet/api/system.codedom.compiler.codedomprovider).</span></span>

## <span data-ttu-id="e5362-306">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="e5362-306">RELATED LINKS</span></span>

[<span data-ttu-id="e5362-307">about_Profiles</span><span class="sxs-lookup"><span data-stu-id="e5362-307">about_Profiles</span></span>](../Microsoft.PowerShell.Core/About/about_profiles.md)

[<span data-ttu-id="e5362-308">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="e5362-308">about_Quoting_Rules</span></span>](../Microsoft.PowerShell.Core/About/about_Quoting_Rules.md)

[<span data-ttu-id="e5362-309">Add-Member</span><span class="sxs-lookup"><span data-stu-id="e5362-309">Add-Member</span></span>](Add-Member.md)

[<span data-ttu-id="e5362-310">New-Object</span><span class="sxs-lookup"><span data-stu-id="e5362-310">New-Object</span></span>](New-Object.md)

[<span data-ttu-id="e5362-311">OutputAssemblyType</span><span class="sxs-lookup"><span data-stu-id="e5362-311">OutputAssemblyType</span></span>](/dotnet/api/microsoft.powershell.commands.outputassemblytype)

[<span data-ttu-id="e5362-312">Plattformaufruf (P/Invoke)</span><span class="sxs-lookup"><span data-stu-id="e5362-312">Platform Invoke (P/Invoke)</span></span>](/dotnet/standard/native-interop/pinvoke)

[<span data-ttu-id="e5362-313">Where-Object</span><span class="sxs-lookup"><span data-stu-id="e5362-313">Where-Object</span></span>](../Microsoft.PowerShell.Core/Where-Object.md)