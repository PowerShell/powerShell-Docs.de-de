---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 5/15/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-module?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Module
ms.openlocfilehash: 4098b40c01085b266fa279107e5795b1283705cd
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212028"
---
# <span data-ttu-id="f7638-103">Get-Module</span><span class="sxs-lookup"><span data-stu-id="f7638-103">Get-Module</span></span>

## <span data-ttu-id="f7638-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="f7638-104">SYNOPSIS</span></span>
<span data-ttu-id="f7638-105">Ruft die Module ab, die in die aktuelle Sitzung importiert wurden oder importiert werden können.</span><span class="sxs-lookup"><span data-stu-id="f7638-105">Gets the modules that have been imported or that can be imported into the current session.</span></span>

## <span data-ttu-id="f7638-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f7638-106">SYNTAX</span></span>

### <span data-ttu-id="f7638-107">Geladen (Standard)</span><span class="sxs-lookup"><span data-stu-id="f7638-107">Loaded (Default)</span></span>

```
Get-Module [[-Name] <String[]>] [-FullyQualifiedName <ModuleSpecification[]>] [-All] [<CommonParameters>]
```

### <span data-ttu-id="f7638-108">Verfügbar</span><span class="sxs-lookup"><span data-stu-id="f7638-108">Available</span></span>

```
Get-Module [[-Name] <String[]>] [-FullyQualifiedName <ModuleSpecification[]>] [-All] [-ListAvailable]
 [-PSEdition <String>] [-Refresh] [<CommonParameters>]
```

### <span data-ttu-id="f7638-109">PsSession</span><span class="sxs-lookup"><span data-stu-id="f7638-109">PsSession</span></span>

```
Get-Module [[-Name] <String[]>] [-FullyQualifiedName <ModuleSpecification[]>] [-ListAvailable]
 [-PSEdition <String>] [-Refresh] -PSSession <PSSession> [<CommonParameters>]
```

### <span data-ttu-id="f7638-110">CimSession</span><span class="sxs-lookup"><span data-stu-id="f7638-110">CimSession</span></span>

```
Get-Module [[-Name] <String[]>] [-FullyQualifiedName <ModuleSpecification[]>] [-ListAvailable] [-Refresh]
 -CimSession <CimSession> [-CimResourceUri <Uri>] [-CimNamespace <String>] [<CommonParameters>]
```

## <span data-ttu-id="f7638-111">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="f7638-111">DESCRIPTION</span></span>

<span data-ttu-id="f7638-112">Das- `Get-Module` Cmdlet ruft die PowerShell-Module ab, die importiert oder in eine PowerShell-Sitzung importiert werden können.</span><span class="sxs-lookup"><span data-stu-id="f7638-112">The `Get-Module` cmdlet gets the PowerShell modules that have been imported, or that can be imported, into a PowerShell session.</span></span>
<span data-ttu-id="f7638-113">Das Modul Objekt, das `Get-Module` zurückgibt, enthält wertvolle Informationen über das Modul.</span><span class="sxs-lookup"><span data-stu-id="f7638-113">The module object that `Get-Module` returns contains valuable information about the module.</span></span>
<span data-ttu-id="f7638-114">Sie können die Modul Objekte auch an andere Cmdlets weiterreichen, wie z `Import-Module` . b. die-und- `Remove-Module` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="f7638-114">You can also pipe the module objects to other cmdlets, such as the `Import-Module` and `Remove-Module` cmdlets.</span></span>

<span data-ttu-id="f7638-115">Ohne Parameter ruft `Get-Module` Module ab, die in die aktuelle Sitzung importiert wurden.</span><span class="sxs-lookup"><span data-stu-id="f7638-115">Without parameters, `Get-Module` gets modules that have been imported into the current session.</span></span>
<span data-ttu-id="f7638-116">Um alle installierten Module zu erhalten, geben Sie den **listavailable** -Parameter an.</span><span class="sxs-lookup"><span data-stu-id="f7638-116">To get all installed modules, specify the **ListAvailable** parameter.</span></span>

<span data-ttu-id="f7638-117">`Get-Module` Ruft Module ab, importiert diese jedoch nicht.</span><span class="sxs-lookup"><span data-stu-id="f7638-117">`Get-Module` gets modules, but it does not import them.</span></span>
<span data-ttu-id="f7638-118">Ab Windows PowerShell 3,0 werden Module automatisch importiert, wenn Sie einen Befehl im Modul verwenden, aber ein `Get-Module` Befehl löst keinen automatischen Import aus.</span><span class="sxs-lookup"><span data-stu-id="f7638-118">Starting in Windows PowerShell 3.0, modules are automatically imported when you use a command in the module, but a `Get-Module` command does not trigger an automatic import.</span></span>
<span data-ttu-id="f7638-119">Sie können die Module auch mithilfe des Cmdlets in Ihre Sitzung importieren `Import-Module` .</span><span class="sxs-lookup"><span data-stu-id="f7638-119">You can also import the modules into your session by using the `Import-Module` cmdlet.</span></span>

<span data-ttu-id="f7638-120">Ab Windows PowerShell 3,0 können Sie Module aus Remote Sitzungen in die lokale Sitzung importieren und dann importieren.</span><span class="sxs-lookup"><span data-stu-id="f7638-120">Starting in Windows PowerShell 3.0, you can get and then, import modules from remote sessions into the local session.</span></span>
<span data-ttu-id="f7638-121">Diese Strategie verwendet das implizite Remoting-Feature von PowerShell und entspricht der Verwendung des- `Import-PSSession` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="f7638-121">This strategy uses the Implicit Remoting feature of PowerShell and is equivalent to using the `Import-PSSession` cmdlet.</span></span>
<span data-ttu-id="f7638-122">Wenn Sie Befehle in Modulen verwenden, die aus einer anderen Sitzung importiert wurden, werden die Befehle implizit in der Remote Sitzung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="f7638-122">When you use commands in modules imported from another session, the commands run implicitly in the remote session.</span></span> <span data-ttu-id="f7638-123">Mit dieser Funktion können Sie den Remote Computer über die lokale Sitzung verwalten.</span><span class="sxs-lookup"><span data-stu-id="f7638-123">This feature lets you manage the remote computer from the local session.</span></span>

<span data-ttu-id="f7638-124">Außerdem können Sie ab Windows PowerShell 3,0 und verwenden, `Get-Module` `Import-Module` um Common Information Model (CIM)-Module zu erhalten und zu importieren, in denen die Cmdlets in Cmdlet-Definitions-XML-Dateien (cdxml) definiert sind.</span><span class="sxs-lookup"><span data-stu-id="f7638-124">Also, starting in Windows PowerShell 3.0, you can use `Get-Module` and `Import-Module` to get and import Common Information Model (CIM) modules, in which the cmdlets are defined in Cmdlet Definition XML (CDXML) files.</span></span>
<span data-ttu-id="f7638-125">Mit dieser Funktion können Sie Cmdlets verwenden, die in nicht verwalteten Codeassemblys implementiert sind, z. b. in C++ geschriebene Assemblys.</span><span class="sxs-lookup"><span data-stu-id="f7638-125">This feature lets you use cmdlets that are implemented in non-managed code assemblies, such as those written in C++.</span></span>

<span data-ttu-id="f7638-126">Mit diesen neuen Features werden die `Get-Module` -und- `Import-Module` Cmdlets zu den wichtigsten Tools für die Verwaltung heterogener Unternehmen, die Computer, auf denen das Windows-Betriebssystem ausgeführt wird, sowie Computer mit anderen Betriebssystemen enthalten.</span><span class="sxs-lookup"><span data-stu-id="f7638-126">With these new features, the `Get-Module` and `Import-Module` cmdlets become primary tools for managing heterogeneous enterprises that include computers that run the Windows operating system and computers that run other operating systems.</span></span>

<span data-ttu-id="f7638-127">Zum Verwalten von Remote Computern, auf denen das Windows-Betriebssystem ausgeführt wird, auf dem PowerShell und PowerShell-Remoting aktiviert sind, erstellen Sie eine **PSSession** auf dem Remote Computer, und verwenden Sie dann den **PSSession** -Parameter von `Get-Module` zum Aufrufen der PowerShell-Module in der **PSSession** .</span><span class="sxs-lookup"><span data-stu-id="f7638-127">To manage remote computers that run the Windows operating system that have PowerShell and PowerShell remoting enabled, create a **PSSession** on the remote computer and then use the **PSSession** parameter of `Get-Module` to get the PowerShell modules in the **PSSession** .</span></span>
<span data-ttu-id="f7638-128">Wenn Sie die Module importieren und dann die importierten Befehle in der aktuellen Sitzung verwenden, werden die Befehle implizit in der **PSSession** auf dem Remote Computer ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="f7638-128">When you import the modules, and then use the imported commands in the current session, the commands run implicitly in the **PSSession** on the remote computer.</span></span>
<span data-ttu-id="f7638-129">Mit dieser Strategie können Sie den Remotecomputer verwalten.</span><span class="sxs-lookup"><span data-stu-id="f7638-129">You can use this strategy to manage the remote computer.</span></span>

<span data-ttu-id="f7638-130">Sie können eine ähnliche Strategie zum Verwalten von Computern verwenden, auf denen PowerShell-Remoting nicht aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="f7638-130">You can use a similar strategy to manage computers that do not have PowerShell remoting enabled.</span></span>
<span data-ttu-id="f7638-131">Dies umfasst Computer, auf denen das Windows-Betriebssystem nicht ausgeführt wird, sowie Computer, auf denen PowerShell, aber nicht PowerShell-Remoting aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="f7638-131">These include computers that are not running the Windows operating system, and computers that have PowerShell but do not have PowerShell remoting enabled.</span></span>

<span data-ttu-id="f7638-132">Beginnen Sie, indem Sie eine CIM-Sitzung auf dem Remote Computer erstellen.</span><span class="sxs-lookup"><span data-stu-id="f7638-132">Start by creating a CIM session on the remote computer.</span></span>
<span data-ttu-id="f7638-133">Eine CIM-Sitzung ist eine Verbindung mit Windows-Verwaltungsinstrumentation (WMI) auf dem Remote Computer.</span><span class="sxs-lookup"><span data-stu-id="f7638-133">A CIM session is a connection to Windows Management Instrumentation (WMI) on the remote computer.</span></span>
<span data-ttu-id="f7638-134">Verwenden Sie dann den **cimsession** -Parameter von `Get-Module` , um CIM-Module aus der CIM-Sitzung zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="f7638-134">Then use the **CIMSession** parameter of `Get-Module` to get CIM modules from the CIM session.</span></span>
<span data-ttu-id="f7638-135">Wenn Sie ein CIM-Modul mit dem `Import-Module` Cmdlet importieren und dann die importierten Befehle ausführen, werden die Befehle implizit auf dem Remote Computer ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="f7638-135">When you import a CIM module by using the `Import-Module` cmdlet and then run the imported commands, the commands run implicitly on the remote computer.</span></span>
<span data-ttu-id="f7638-136">Mit dieser WMI- und CIM-Strategie können Sie den Remotecomputer verwalten.</span><span class="sxs-lookup"><span data-stu-id="f7638-136">You can use this WMI and CIM strategy to manage the remote computer.</span></span>

## <span data-ttu-id="f7638-137">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="f7638-137">EXAMPLES</span></span>

### <span data-ttu-id="f7638-138">Beispiel 1: Importieren von Modulen, die in die aktuelle Sitzung importiert werden</span><span class="sxs-lookup"><span data-stu-id="f7638-138">Example 1: Get modules imported into the current session</span></span>

```powershell
Get-Module
```

<span data-ttu-id="f7638-139">Dieser Befehl ruft Module ab, die in die aktuelle Sitzung importiert wurden.</span><span class="sxs-lookup"><span data-stu-id="f7638-139">This command gets modules that have been imported into the current session.</span></span>

### <span data-ttu-id="f7638-140">Beispiel 2: Get installierter Module und verfügbarer Module</span><span class="sxs-lookup"><span data-stu-id="f7638-140">Example 2: Get installed modules and available modules</span></span>

```powershell
Get-Module -ListAvailable
```

<span data-ttu-id="f7638-141">Dieser Befehl ruft die Module ab, die auf dem Computer installiert sind und in die aktuelle Sitzung importiert werden können.</span><span class="sxs-lookup"><span data-stu-id="f7638-141">This command gets the modules that are installed on the computer and can be imported into the current session.</span></span>

<span data-ttu-id="f7638-142">`Get-Module` sucht nach verfügbaren Modulen in dem Pfad, der in der **$ENV:P smodulepath** -Umgebungsvariablen angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="f7638-142">`Get-Module` looks for available modules in the path specified by the **$env:PSModulePath** environment variable.</span></span>
<span data-ttu-id="f7638-143">Weitere Informationen zu **PSModulePath** finden Sie unter [about_Modules](About/about_Modules.md) und [about_Environment_Variables](About/about_Environment_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="f7638-143">For more information about **PSModulePath** , see [about_Modules](About/about_Modules.md) and [about_Environment_Variables](About/about_Environment_Variables.md).</span></span>

### <span data-ttu-id="f7638-144">Beispiel 3: alle exportierten Dateien</span><span class="sxs-lookup"><span data-stu-id="f7638-144">Example 3: Get all exported files</span></span>

```powershell
Get-Module -ListAvailable -All
```

<span data-ttu-id="f7638-145">Dieser Befehl ruft alle exportierten Dateien für alle verfügbaren Module ab.</span><span class="sxs-lookup"><span data-stu-id="f7638-145">This command gets all of the exported files for all available modules.</span></span>

### <span data-ttu-id="f7638-146">Beispiel 4: Holen Sie ein Modul mit seinem voll qualifizierten Namen.</span><span class="sxs-lookup"><span data-stu-id="f7638-146">Example 4: Get a module by its fully qualified name</span></span>

```powershell
$FullyQualifedName = @{ModuleName="Microsoft.PowerShell.Management";ModuleVersion="3.1.0.0"}
Get-Module -FullyQualifiedName $FullyQualifedName | Format-Table -Property Name,Version
```

```Output
Name                             Version
----                             -------
Microsoft.PowerShell.Management  3.1.0.0
```

<span data-ttu-id="f7638-147">Mit diesem Befehl wird das **Microsoft. PowerShell. Management** -Modul abgerufen, indem der voll qualifizierte Name des Moduls mithilfe des **FullyQualifiedName** -Parameters angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="f7638-147">This command gets the **Microsoft.PowerShell.Management** module by specifying the fully qualified name of the module by using the **FullyQualifiedName** parameter.</span></span>
<span data-ttu-id="f7638-148">Der Befehl übergibt die Ergebnisse dann an das `Format-Table` Cmdlet, um die Ergebnisse als Tabelle mit dem **Namen** und der **Version** als Spaltenüberschriften zu formatieren.</span><span class="sxs-lookup"><span data-stu-id="f7638-148">The command then pipes the results into the `Format-Table` cmdlet to format the results as a table with **Name** and **Version** as the column headings.</span></span>

### <span data-ttu-id="f7638-149">Beispiel 5: erhalten der Eigenschaften eines Moduls</span><span class="sxs-lookup"><span data-stu-id="f7638-149">Example 5: Get properties of a module</span></span>

```powershell
Get-Module | Get-Member -MemberType Property | Format-Table Name
```

```Output
Name
----
AccessMode
Author
ClrVersion
CompanyName
Copyright
Definition
Description
DotNetFrameworkVersion
ExportedAliases
ExportedCmdlets
ExportedCommands
ExportedFormatFiles
ExportedFunctions
ExportedTypeFiles
ExportedVariables
ExportedWorkflows
FileList
Guid
HelpInfoUri
LogPipelineExecutionDetails
ModuleBase
ModuleList
ModuleType
Name
NestedModules
OnRemove
Path
PowerShellHostName
PowerShellHostVersion
PowerShellVersion
PrivateData
ProcessorArchitecture
RequiredAssemblies
RequiredModules
RootModule
Scripts
SessionState
Version
```

<span data-ttu-id="f7638-150">Mit diesem Befehl werden die Eigenschaften des **psmoduleinfo** -Objekts abgerufen, das `Get-Module` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="f7638-150">This command gets the properties of the **PSModuleInfo** object that `Get-Module` returns.</span></span>
<span data-ttu-id="f7638-151">Für jede Moduldatei ist ein Objekt vorhanden.</span><span class="sxs-lookup"><span data-stu-id="f7638-151">There is one object for each module file.</span></span>

<span data-ttu-id="f7638-152">Mit den Eigenschaften können Sie die Modulobjekte formatieren und filtern.</span><span class="sxs-lookup"><span data-stu-id="f7638-152">You can use the properties to format and filter the module objects.</span></span>
<span data-ttu-id="f7638-153">Weitere Informationen zu den Eigenschaften finden Sie unter [psmoduleinfo-Eigenschaften](/dotnet/api/system.management.automation.psmoduleinfo).</span><span class="sxs-lookup"><span data-stu-id="f7638-153">For more information about the properties, see [PSModuleInfo Properties](/dotnet/api/system.management.automation.psmoduleinfo).</span></span>

<span data-ttu-id="f7638-154">Die Ausgabe enthält die neuen Eigenschaften, z. b. " **Author** " und " **CompanyName** ", die in Windows PowerShell 3,0 eingeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="f7638-154">The output includes the new properties, such as **Author** and **CompanyName** , that were introduced in Windows PowerShell 3.0.</span></span>

### <span data-ttu-id="f7638-155">Beispiel 6: Gruppieren aller Module nach Name</span><span class="sxs-lookup"><span data-stu-id="f7638-155">Example 6: Group all modules by name</span></span>

```powershell
Get-Module -ListAvailable -All | Format-Table -Property Name, Moduletype, Path -Groupby Name
```

```Output
Name: AppLocker

Name      ModuleType Path
----      ---------- ----
AppLocker   Manifest C:\Windows\system32\WindowsPowerShell\v1.0\Modules\AppLocker\AppLocker.psd1


   Name: Appx

Name ModuleType Path
---- ---------- ----
Appx   Manifest C:\Windows\system32\WindowsPowerShell\v1.0\Modules\Appx\en-US\Appx.psd1
Appx   Manifest C:\Windows\system32\WindowsPowerShell\v1.0\Modules\Appx\Appx.psd1
Appx     Script C:\Windows\system32\WindowsPowerShell\v1.0\Modules\Appx\Appx.psm1


   Name: BestPractices

Name          ModuleType Path
----          ---------- ----
BestPractices   Manifest C:\Windows\system32\WindowsPowerShell\v1.0\Modules\BestPractices\BestPractices.psd1


   Name: BitsTransfer

Name         ModuleType Path
----         ---------- ----
BitsTransfer   Manifest C:\Windows\system32\WindowsPowerShell\v1.0\Modules\BitsTransfer\BitsTransfer.psd1
```

<span data-ttu-id="f7638-156">Dieser Befehl ruft alle Moduldateien ab, die importiert und verfügbar sind, und gruppiert Sie dann nach Modulname.</span><span class="sxs-lookup"><span data-stu-id="f7638-156">This command gets all module files, both imported and available, and then groups them by module name.</span></span> <span data-ttu-id="f7638-157">So können Sie die Moduldateien sehen, die von denen einzelnen Skripts exportiert werden.</span><span class="sxs-lookup"><span data-stu-id="f7638-157">This lets you see the module files that each script is exporting.</span></span>

### <span data-ttu-id="f7638-158">Beispiel 7: Anzeigen des Inhalts eines Modul Manifests</span><span class="sxs-lookup"><span data-stu-id="f7638-158">Example 7: Display the contents of a module manifest</span></span>

<span data-ttu-id="f7638-159">Diese Befehle zeigen den Inhalt des Modul Manifests für das Windows PowerShell- **bitstransfer** -Modul an.</span><span class="sxs-lookup"><span data-stu-id="f7638-159">These commands display the contents of the module manifest for the Windows PowerShell **BitsTransfer** module.</span></span>

<span data-ttu-id="f7638-160">Module müssen keine Manifest-Dateien haben.</span><span class="sxs-lookup"><span data-stu-id="f7638-160">Modules are not required to have manifest files.</span></span>
<span data-ttu-id="f7638-161">Wenn Sie über eine Manifest-Datei verfügen, muss die Manifest-Datei nur eine Versionsnummer enthalten.</span><span class="sxs-lookup"><span data-stu-id="f7638-161">When they do have a manifest file, the manifest file is required only to include a version number.</span></span>
<span data-ttu-id="f7638-162">Manifestdateien enthalten jedoch oft nützliche Informationen über ein Modul, seine Anforderungen und seinen Inhalt.</span><span class="sxs-lookup"><span data-stu-id="f7638-162">However, manifest files often provide useful information about a module, its requirements, and its contents.</span></span>

```powershell
# First command
$m = Get-Module -list -Name BitsTransfer

# Second command
Get-Content $m.Path
```

```Output
@ {
    GUID               = "{8FA5064B-8479-4c5c-86EA-0D311FE48875}"
    Author             = "Microsoft Corporation"
    CompanyName        = "Microsoft Corporation"
    Copyright          = "Microsoft Corporation. All rights reserved."
    ModuleVersion      = "1.0.0.0"
    Description        = "Windows PowerShell File Transfer Module"
    PowerShellVersion  = "2.0"
    CLRVersion         = "2.0"
    NestedModules      = "Microsoft.BackgroundIntelligentTransfer.Management"
    FormatsToProcess   = "FileTransfer.Format.ps1xml"
    RequiredAssemblies = Join-Path $psScriptRoot "Microsoft.BackgroundIntelligentTransfer.Management.Interop.dll"
}
```

<span data-ttu-id="f7638-163">Mit dem ersten Befehl wird das PSModuleInfo-Objekt abgerufen, das das BitsTransfer-Modul darstellt.</span><span class="sxs-lookup"><span data-stu-id="f7638-163">The first command gets the PSModuleInfo object that represents BitsTransfer module.</span></span> <span data-ttu-id="f7638-164">Das Objekt wird in der `$m` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="f7638-164">It saves the object in the `$m` variable.</span></span>

<span data-ttu-id="f7638-165">Der zweite Befehl verwendet das `Get-Content` Cmdlet, um den Inhalt der Manifest-Datei im angegebenen Pfad zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="f7638-165">The second command uses the `Get-Content` cmdlet to get the content of the manifest file in the specified path.</span></span> <span data-ttu-id="f7638-166">Mithilfe der Punktnotation wird der Pfad zur Manifestdatei abgerufen, der in der Path-Eigenschaft des Objekts gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="f7638-166">It uses dot notation to get the path to the manifest file, which is stored in the Path property of the object.</span></span> <span data-ttu-id="f7638-167">Die Ausgabe zeigt den Inhalt des Modulmanifests.</span><span class="sxs-lookup"><span data-stu-id="f7638-167">The output shows the contents of the module manifest.</span></span>

### <span data-ttu-id="f7638-168">Beispiel 8: Auflisten von Dateien im Modul Verzeichnis</span><span class="sxs-lookup"><span data-stu-id="f7638-168">Example 8: List files in module directory</span></span>

```powershell
dir (Get-Module -ListAvailable FileTransfer).ModuleBase
```

```Output
Directory: C:\Windows\system32\WindowsPowerShell\v1.0\Modules\FileTransfer
Mode                LastWriteTime     Length Name
----                -------------     ------ ----
d----        12/16/2008  12:36 PM            en-US
-a---        11/19/2008  11:30 PM      16184 FileTransfer.Format.ps1xml
-a---        11/20/2008  11:30 PM       1044 FileTransfer.psd1
-a---        12/16/2008  12:20 AM     108544 Microsoft.BackgroundIntelligentTransfer.Management.Interop.dll
```

<span data-ttu-id="f7638-169">Dieser Befehl listet die Dateien im Verzeichnis des Moduls auf.</span><span class="sxs-lookup"><span data-stu-id="f7638-169">This command lists the files in the directory of the module.</span></span>
<span data-ttu-id="f7638-170">Dies ist eine weitere Methode, um den Inhalt eines Modul zu ermitteln, bevor Sie es importieren.</span><span class="sxs-lookup"><span data-stu-id="f7638-170">This is another way to determine what is in a module before you import it.</span></span>
<span data-ttu-id="f7638-171">Einige Module verfügen möglicherweise über Hilfe- oder Infodateien, die das Modul beschreiben.</span><span class="sxs-lookup"><span data-stu-id="f7638-171">Some modules might have help files or ReadMe files that describe the module.</span></span>

### <span data-ttu-id="f7638-172">Beispiel 9: Installieren von Modulen, die auf einem Computer installiert sind</span><span class="sxs-lookup"><span data-stu-id="f7638-172">Example 9: Get modules installed on a computer</span></span>

```powershell
$s = New-PSSession -ComputerName Server01

Get-Module -PSSession $s -ListAvailable
```

<span data-ttu-id="f7638-173">Diese Befehle rufen die Module ab, die auf dem Computer Server01 installiert sind.</span><span class="sxs-lookup"><span data-stu-id="f7638-173">These commands get the modules that are installed on the Server01 computer.</span></span>

<span data-ttu-id="f7638-174">Der erste Befehl verwendet das `New-PSSession` Cmdlet, um eine **PSSession** auf dem Server01-Computer zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="f7638-174">The first command uses the `New-PSSession` cmdlet to create a **PSSession** on the Server01 computer.</span></span> <span data-ttu-id="f7638-175">Der Befehl speichert die **PSSession** in der $s Variable.</span><span class="sxs-lookup"><span data-stu-id="f7638-175">The command saves the **PSSession** in the $s variable.</span></span>

<span data-ttu-id="f7638-176">Der zweite Befehl verwendet den **PSSession** -und den **listavailable** -Parameter von `Get-Module` , um die Module in der **PSSession** in der $s-Variablen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="f7638-176">The second command uses the **PSSession** and **ListAvailable** parameters of `Get-Module` to get the modules in the **PSSession** in the $s variable.</span></span>

<span data-ttu-id="f7638-177">Wenn Sie Module aus anderen Sitzungen an das `Import-Module` Cmdlet weiterreichen, `Import-Module` importiert das Modul mithilfe des impliziten Remotingfeatures in die aktuelle Sitzung.</span><span class="sxs-lookup"><span data-stu-id="f7638-177">If you pipe modules from other sessions to the `Import-Module` cmdlet, `Import-Module` imports the module into the current session by using the implicit remoting feature.</span></span>
<span data-ttu-id="f7638-178">Dies entspricht der Verwendung des- `Import-PSSession` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="f7638-178">This is equivalent to using the `Import-PSSession` cmdlet.</span></span>
<span data-ttu-id="f7638-179">Sie können die Cmdlets aus dem Modul in der aktuellen Sitzung verwenden, die Befehle, die diese Cmdlets verwenden, werden jedoch tatsächlich in der Remotesitzung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="f7638-179">You can use the cmdlets from the module in the current session, but commands that use these cmdlets actually run the remote session.</span></span>
<span data-ttu-id="f7638-180">Weitere Informationen finden Sie unter [`Import-Module`](Import-Module.md) und [`Import-PSSession`](../Microsoft.PowerShell.Utility/Import-PSSession.md).</span><span class="sxs-lookup"><span data-stu-id="f7638-180">For more information, see [`Import-Module`](Import-Module.md) and [`Import-PSSession`](../Microsoft.PowerShell.Utility/Import-PSSession.md).</span></span>

### <span data-ttu-id="f7638-181">Beispiel 10: Verwalten eines Computers, auf dem das Windows-Betriebssystem nicht ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="f7638-181">Example 10: Manage a computer that does not run the Windows operating system</span></span>

<span data-ttu-id="f7638-182">Die Befehle in diesem Beispiel ermöglichen es Ihnen, die Speichersysteme eines Remote Computers zu verwalten, auf dem das Windows-Betriebssystem nicht ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f7638-182">The commands in this example enable you to manage the storage systems of a remote computer that is not running the Windows operating system.</span></span>
<span data-ttu-id="f7638-183">Da der Administrator des Computers in diesem Beispiel den WMI-Anbieter für die Modulerkennung installiert hat, können die CIM-Befehle die Standardwerte verwenden, für den Anbieter konzipiert wurden.</span><span class="sxs-lookup"><span data-stu-id="f7638-183">In this example, because the administrator of the computer has installed the Module Discovery WMI provider, the CIM commands can use the default values, which are designed for the provider.</span></span>

```powershell
$cs = New-CimSession -ComputerName RSDGF03
Get-Module -CimSession $cs -Name Storage | Import-Module
Get-Command Get-Disk
```

```Output
CommandType     Name                  ModuleName
-----------     ----                  ----------
Function        Get-Disk              Storage
```

```powershell
Get-Disk
```

```Output
Number Friendly Name              OperationalStatus          Total Size Partition Style
------ -------------              -----------------          ---------- ---------------
0      Virtual HD ATA Device      Online                          40 GB MBR
```

<span data-ttu-id="f7638-184">Der erste Befehl verwendet das `New-CimSession` Cmdlet, um eine Sitzung auf dem Remote Computer RSDGF03 zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="f7638-184">The first command uses the `New-CimSession` cmdlet to create a session on the RSDGF03 remote computer.</span></span> <span data-ttu-id="f7638-185">Die Sitzung stellt auf dem Remotecomputer eine Verbindung mit WMI her.</span><span class="sxs-lookup"><span data-stu-id="f7638-185">The session connects to WMI on the remote computer.</span></span> <span data-ttu-id="f7638-186">Der Befehl speichert die CIM-Sitzung in der `$cs` Variablen.</span><span class="sxs-lookup"><span data-stu-id="f7638-186">The command saves the CIM session in the `$cs` variable.</span></span>

<span data-ttu-id="f7638-187">Der zweite Befehl verwendet die CIM-Sitzung in der `$cs` Variablen, um `Get-Module` auf dem RSDGF03-Computer einen Befehl auszuführen.</span><span class="sxs-lookup"><span data-stu-id="f7638-187">The second command uses the CIM session in the `$cs` variable to run a `Get-Module` command on the RSDGF03 computer.</span></span> <span data-ttu-id="f7638-188">Mit dem Name-Parameter wird das Storage-Modul angegeben.</span><span class="sxs-lookup"><span data-stu-id="f7638-188">The command uses the Name parameter to specify the Storage module.</span></span> <span data-ttu-id="f7638-189">Der Befehl verwendet einen Pipeline Operator (|), um das Speichermodul an das `Import-Module` Cmdlet zu senden, das das Modul in die lokale Sitzung importiert.</span><span class="sxs-lookup"><span data-stu-id="f7638-189">The command uses a pipeline operator (|) to send the Storage module to the `Import-Module` cmdlet, which imports it into the local session.</span></span>

<span data-ttu-id="f7638-190">Mit dem dritten Befehl wird das `Get-Command` Cmdlet für den `Get-Disk` Befehl im Storage-Modul ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="f7638-190">The third command runs the `Get-Command` cmdlet on the `Get-Disk` command in the Storage module.</span></span>
<span data-ttu-id="f7638-191">Wenn Sie ein CIM-Modul in die lokale Sitzung importieren, konvertiert PowerShell die cdxml-Dateien, die das CIM-Modul darstellen, in PowerShell-Skripts, die als Funktionen in der lokalen Sitzung angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="f7638-191">When you import a CIM module into the local session, PowerShell converts the CDXML files that represent the CIM module into PowerShell scripts, which appear as functions in the local session.</span></span>

<span data-ttu-id="f7638-192">Der vierte Befehl führt den `Get-Disk` Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="f7638-192">The fourth command runs the `Get-Disk` command.</span></span> <span data-ttu-id="f7638-193">Obwohl der Befehl in die lokale Sitzung eingegeben wird, wird er implizit auf dem Remotecomputer ausgeführt, von dem er importiert wurde.</span><span class="sxs-lookup"><span data-stu-id="f7638-193">Although the command is typed in the local session, it runs implicitly on the remote computer from which it was imported.</span></span> <span data-ttu-id="f7638-194">Der Befehl ruft Objekte vom Remotecomputer ab und gibt sie an die lokale Sitzung zurück.</span><span class="sxs-lookup"><span data-stu-id="f7638-194">The command gets objects from the remote computer and returns them to the local session.</span></span>

## <span data-ttu-id="f7638-195">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f7638-195">PARAMETERS</span></span>

### <span data-ttu-id="f7638-196">-All</span><span class="sxs-lookup"><span data-stu-id="f7638-196">-All</span></span>

<span data-ttu-id="f7638-197">Gibt an, dass dieses Cmdlet alle Module in jedem Modul Ordner abruft, einschließlich der in einem Modul eingefügten Module, Manifest-Dateien (. psd1), Skript Moduldateien (. psm1) und binärer Moduldateien (. dll).</span><span class="sxs-lookup"><span data-stu-id="f7638-197">Indicates that this cmdlet gets all modules in each module folder, including nested modules, manifest (.psd1) files, script module (.psm1) files, and binary module (.dll) files.</span></span>
<span data-ttu-id="f7638-198">Ohne diesen Parameter `Get-Module` wird von nur das Standardmodul in jedem Modul Ordner abgerufen.</span><span class="sxs-lookup"><span data-stu-id="f7638-198">Without this parameter, `Get-Module` gets only the default module in each module folder.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Loaded, Available
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f7638-199">-Cimnamespace</span><span class="sxs-lookup"><span data-stu-id="f7638-199">-CimNamespace</span></span>

<span data-ttu-id="f7638-200">Gibt den Namespace eines alternativen CIM-Anbieters an, der CIM-Module verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="f7638-200">Specifies the namespace of an alternate CIM provider that exposes CIM modules.</span></span>
<span data-ttu-id="f7638-201">Der Standardwert ist der Namespace des WMI-Anbieters für die Modulerkennung.</span><span class="sxs-lookup"><span data-stu-id="f7638-201">The default value is the namespace of the Module Discovery WMI provider.</span></span>

<span data-ttu-id="f7638-202">Verwenden Sie diesen Parameter zum Aufrufen von CIM-Modulen von Computern und Geräten, auf denen das Windows-Betriebssystem nicht ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f7638-202">Use this parameter to get CIM modules from computers and devices that are not running the Windows operating system.</span></span>

<span data-ttu-id="f7638-203">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="f7638-203">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: CimSession
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f7638-204">-Cimresourceuri</span><span class="sxs-lookup"><span data-stu-id="f7638-204">-CimResourceUri</span></span>

<span data-ttu-id="f7638-205">Gibt einen alternativen Speicherort für die CIM-Module an.</span><span class="sxs-lookup"><span data-stu-id="f7638-205">Specifies an alternate location for CIM modules.</span></span>
<span data-ttu-id="f7638-206">Der Standardwert ist der Ressourcen-URI des WMI-Anbieters für die Modul Ermittlung auf dem Remote Computer.</span><span class="sxs-lookup"><span data-stu-id="f7638-206">The default value is the resource URI of the Module Discovery WMI provider on the remote computer.</span></span>

<span data-ttu-id="f7638-207">Verwenden Sie diesen Parameter zum Aufrufen von CIM-Modulen von Computern und Geräten, auf denen das Windows-Betriebssystem nicht ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f7638-207">Use this parameter to get CIM modules from computers and devices that are not running the Windows operating system.</span></span>

<span data-ttu-id="f7638-208">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="f7638-208">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Uri
Parameter Sets: CimSession
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f7638-209">-CimSession</span><span class="sxs-lookup"><span data-stu-id="f7638-209">-CimSession</span></span>

<span data-ttu-id="f7638-210">Gibt eine CIM-Sitzung auf dem Remotecomputer an.</span><span class="sxs-lookup"><span data-stu-id="f7638-210">Specifies a CIM session on the remote computer.</span></span>
<span data-ttu-id="f7638-211">Geben Sie eine Variable ein, die die CIM-Sitzung oder einen Befehl enthält, der die CIM-Sitzung abruft, z. b. den Befehl [Get-cimsession](/powershell/module/cimcmdlets/get-cimsession) .</span><span class="sxs-lookup"><span data-stu-id="f7638-211">Enter a variable that contains the CIM session or a command that gets the CIM session, such as a [Get-CimSession](/powershell/module/cimcmdlets/get-cimsession) command.</span></span>

<span data-ttu-id="f7638-212">`Get-Module` verwendet die CIM-Sitzungs Verbindung, um Module vom Remote Computer zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="f7638-212">`Get-Module` uses the CIM session connection to get modules from the remote computer.</span></span>
<span data-ttu-id="f7638-213">Wenn Sie das Modul mit dem `Import-Module` Cmdlet importieren und die Befehle aus dem importierten Modul in der aktuellen Sitzung verwenden, werden die Befehle tatsächlich auf dem Remote Computer ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="f7638-213">When you import the module by using the `Import-Module` cmdlet and use the commands from the imported module in the current session, the commands actually run on the remote computer.</span></span>

<span data-ttu-id="f7638-214">Sie können diesen Parameter verwenden, um Module von Computern und Geräten, auf denen das Windows-Betriebssystem ausgeführt wird, sowie für Computer mit PowerShell, für die PowerShell-Remoting nicht aktiviert ist, zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="f7638-214">You can use this parameter to get modules from computers and devices that are not running the Windows operating system, and computers that have PowerShell, but do not have PowerShell remoting enabled.</span></span>

<span data-ttu-id="f7638-215">Der **CimSession** -Parameter ruft alle Module in der **CIMSession** ab.</span><span class="sxs-lookup"><span data-stu-id="f7638-215">The **CimSession** parameter gets all modules in the **CIMSession** .</span></span>
<span data-ttu-id="f7638-216">Sie können jedoch nur CIM- und CDXML (Cmdlet Definition XML)-basierte Module importieren.</span><span class="sxs-lookup"><span data-stu-id="f7638-216">However, you can import only CIM-based and Cmdlet Definition XML (CDXML)-based modules.</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimSession
Parameter Sets: CimSession
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f7638-217">-FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="f7638-217">-FullyQualifiedName</span></span>

<span data-ttu-id="f7638-218">Gibt die Namen von Modulen in Form von **modulespecification** -Objekten an.</span><span class="sxs-lookup"><span data-stu-id="f7638-218">Specifies names of modules in the form of **ModuleSpecification** objects.</span></span>
<span data-ttu-id="f7638-219">Diese Objekte werden im Abschnitt "Hinweise" des [modulespecification-Konstruktors (Hash Tabelle)](https://msdn.microsoft.com/library/jj136290) in der MSDN Library beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f7638-219">These objects are described in the Remarks section of [ModuleSpecification Constructor (Hashtable)](https://msdn.microsoft.com/library/jj136290) in the MSDN library.</span></span>
<span data-ttu-id="f7638-220">Der **FullyQualifiedName** -Parameter akzeptiert z. b. einen Modulnamen, der in den folgenden Formaten angegeben ist:</span><span class="sxs-lookup"><span data-stu-id="f7638-220">For example, the **FullyQualifiedName** parameter accepts a module name that is specified in the following formats:</span></span>

- <span data-ttu-id="f7638-221">@ {ModuleName = "ModuleName"; Moduleversion = "version_number"}</span><span class="sxs-lookup"><span data-stu-id="f7638-221">@{ModuleName = "modulename"; ModuleVersion = "version_number"}</span></span>
- <span data-ttu-id="f7638-222">@ {ModuleName = "ModuleName"; Moduleversion = "version_number"; GUID = "GUID"}</span><span class="sxs-lookup"><span data-stu-id="f7638-222">@{ModuleName = "modulename"; ModuleVersion = "version_number"; Guid = "GUID"}</span></span>

<span data-ttu-id="f7638-223">**ModuleName** und **ModuleVersion** sind erforderlich, aber **Guid** ist optional.</span><span class="sxs-lookup"><span data-stu-id="f7638-223">**ModuleName** and **ModuleVersion** are required, but **Guid** is optional.</span></span>

<span data-ttu-id="f7638-224">Der **FullyQualifiedName** -Parameter kann nicht im selben Befehl wie ein **namens** Parameter angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="f7638-224">You cannot specify the **FullyQualifiedName** parameter in the same command as a **Name** parameter.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.ModuleSpecification[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="f7638-225">-Listavailable</span><span class="sxs-lookup"><span data-stu-id="f7638-225">-ListAvailable</span></span>

<span data-ttu-id="f7638-226">Gibt an, dass dieses Cmdlet alle installierten Module abruft.</span><span class="sxs-lookup"><span data-stu-id="f7638-226">Indicates that this cmdlet gets all installed modules.</span></span>
<span data-ttu-id="f7638-227">`Get-Module` Ruft Module in Pfaden ab, die in der **psmodulepath** -Umgebungsvariablen aufgelistet sind.</span><span class="sxs-lookup"><span data-stu-id="f7638-227">`Get-Module` gets modules in paths listed in the **PSModulePath** environment variable.</span></span>
<span data-ttu-id="f7638-228">Ohne diesen Parameter ruft `Get-Module` nur die Module ab, die in der **psmodulepath** -Umgebungsvariablen aufgelistet sind und in die aktuelle Sitzung geladen werden.</span><span class="sxs-lookup"><span data-stu-id="f7638-228">Without this parameter, `Get-Module` gets only the modules that are both listed in the **PSModulePath** environment variable, and that are loaded in the current session.</span></span>
<span data-ttu-id="f7638-229">**ListAvailable** gibt keine Informationen zu Modulen zurück, die in der **PSModulePath** -Umgebungsvariablen nicht gefunden wurden, selbst wenn diese Module in der aktuellen Sitzung geladen sind.</span><span class="sxs-lookup"><span data-stu-id="f7638-229">**ListAvailable** does not return information about modules that are not found in the **PSModulePath** environment variable, even if those modules are loaded in the current session.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Available, PsSession, CimSession
Aliases:

Required: True (Available), False (PsSession, CimSession)
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f7638-230">-Name</span><span class="sxs-lookup"><span data-stu-id="f7638-230">-Name</span></span>

<span data-ttu-id="f7638-231">Gibt die Namen oder Namensmuster von Modulen an, die von diesem Cmdlet abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="f7638-231">Specifies names or name patterns of modules that this cmdlet gets.</span></span>
<span data-ttu-id="f7638-232">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="f7638-232">Wildcard characters are permitted.</span></span>
<span data-ttu-id="f7638-233">Sie können die Namen auch über die Pipeline an senden `Get-Module` .</span><span class="sxs-lookup"><span data-stu-id="f7638-233">You can also pipe the names to `Get-Module`.</span></span>
<span data-ttu-id="f7638-234">Der **FullyQualifiedName** -Parameter kann nicht im selben Befehl wie ein **namens** Parameter angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="f7638-234">You cannot specify the **FullyQualifiedName** parameter in the same command as a **Name** parameter.</span></span>

<span data-ttu-id="f7638-235">Der **Name** darf keine Modul-GUID als Wert annehmen.</span><span class="sxs-lookup"><span data-stu-id="f7638-235">**Name** cannot accept a module GUID as a value.</span></span>
<span data-ttu-id="f7638-236">Um Module durch Angabe einer GUID zurückzugeben, verwenden Sie stattdessen **FullyQualifiedName** .</span><span class="sxs-lookup"><span data-stu-id="f7638-236">To return modules by specifying a GUID, use **FullyQualifiedName** instead.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="f7638-237">-P\* dition</span><span class="sxs-lookup"><span data-stu-id="f7638-237">-PSEdition</span></span>

<span data-ttu-id="f7638-238">Ruft die Module ab, die die angegebene Edition von PowerShell unterstützen.</span><span class="sxs-lookup"><span data-stu-id="f7638-238">Gets the modules that support specified edition of PowerShell.</span></span>

<span data-ttu-id="f7638-239">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="f7638-239">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="f7638-240">Desktop</span><span class="sxs-lookup"><span data-stu-id="f7638-240">Desktop</span></span>
- <span data-ttu-id="f7638-241">Core</span><span class="sxs-lookup"><span data-stu-id="f7638-241">Core</span></span>

<span data-ttu-id="f7638-242">Das Get-Module-Cmdlet überprüft die **compatiblepseditions** -Eigenschaft des **psmoduleinfo** -Objekts auf den angegebenen Wert und gibt nur die Module zurück, für die es festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="f7638-242">The Get-Module cmdlet checks **CompatiblePSEditions** property of **PSModuleInfo** object for the specified value and returns only those modules that have it set.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="f7638-243">**Desktop-Edition:** Diese Edition basiert auf .NET Framework und bietet Kompatibilität mit Skripts und Modulen für Versionen von PowerShell, die unter Vollversionen von Windows wie Server Core und Windows Desktop ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="f7638-243">**Desktop Edition:** Built on .NET Framework and provides compatibility with scripts and modules targeting versions of PowerShell running on full footprint editions of Windows such as Server Core and Windows Desktop.</span></span>
> - <span data-ttu-id="f7638-244">**Core-Edition:** Diese Edition basiert auf .NET Core und bietet Kompatibilität mit Skripts und Modulen für Versionen von PowerShell, die unter funktionsreduzierten Versionen von Windows wie Nano Server und Windows IoT ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="f7638-244">**Core Edition:** Built on .NET Core and provides compatibility with scripts and modules targeting versions of PowerShell running on reduced footprint editions of Windows such as Nano Server and Windows IoT.</span></span>

```yaml
Type: System.String
Parameter Sets: PsSession, Available
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f7638-245">-PSSession</span><span class="sxs-lookup"><span data-stu-id="f7638-245">-PSSession</span></span>

<span data-ttu-id="f7638-246">Ruft die Module in der angegebenen Benutzer verwalteten PowerShell-Sitzung ( **PSSession** ) ab.</span><span class="sxs-lookup"><span data-stu-id="f7638-246">Gets the modules in the specified user-managed PowerShell session ( **PSSession** ).</span></span>
<span data-ttu-id="f7638-247">Geben Sie eine Variable ein, die die Sitzung enthält, einen Befehl, der die Sitzung abruft, z. b. einen- `Get-PSSession` Befehl oder einen Befehl, der die Sitzung erstellt, z. b. einen- `New-PSSession` Befehl.</span><span class="sxs-lookup"><span data-stu-id="f7638-247">Enter a variable that contains the session, a command that gets the session, such as a `Get-PSSession` command, or a command that creates the session, such as a `New-PSSession` command.</span></span>

<span data-ttu-id="f7638-248">Wenn die Sitzung mit einem Remote Computer verbunden ist, müssen Sie den **listavailable** -Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="f7638-248">When the session is connected to a remote computer, you must specify the **ListAvailable** parameter.</span></span>

<span data-ttu-id="f7638-249">Ein `Get-Module` Befehl, der den **PSSession** -Parameter verwendet, entspricht der Verwendung des- `Invoke-Command` Cmdlets zum Ausführen eines `Get-Module -ListAvailable` Befehls in einer **PSSession** .</span><span class="sxs-lookup"><span data-stu-id="f7638-249">A `Get-Module` command that uses the **PSSession** parameter is equivalent to using the `Invoke-Command` cmdlet to run a `Get-Module -ListAvailable` command in a **PSSession** .</span></span>

<span data-ttu-id="f7638-250">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="f7638-250">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.PSSession
Parameter Sets: PsSession
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f7638-251">-Aktualisieren</span><span class="sxs-lookup"><span data-stu-id="f7638-251">-Refresh</span></span>

<span data-ttu-id="f7638-252">Gibt an, dass dieses Cmdlet den Cache der installierten Befehle aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="f7638-252">Indicates that this cmdlet refreshes the cache of installed commands.</span></span>
<span data-ttu-id="f7638-253">Der Befehlscache wird beim Starten der Sitzung erstellt.</span><span class="sxs-lookup"><span data-stu-id="f7638-253">The command cache is created when the session starts.</span></span>
<span data-ttu-id="f7638-254">Sie ermöglicht es dem `Get-Command` Cmdlet, Befehle aus Modulen zu erhalten, die nicht in die Sitzung importiert werden.</span><span class="sxs-lookup"><span data-stu-id="f7638-254">It enables the `Get-Command` cmdlet to get commands from modules that are not imported into the session.</span></span>

<span data-ttu-id="f7638-255">Dieser Parameter ist für Entwicklungs- und Testszenarien vorgesehen, in denen der Inhalt von Modulen sich seit dem Start der Sitzung geändert hat.</span><span class="sxs-lookup"><span data-stu-id="f7638-255">This parameter is designed for development and testing scenarios in which the contents of modules have changed since the session started.</span></span>

<span data-ttu-id="f7638-256">Wenn Sie den **Refresh** -Parameter in einem Befehl angeben, müssen Sie **listavailable** angeben.</span><span class="sxs-lookup"><span data-stu-id="f7638-256">When you specify the **Refresh** parameter in a command, you must specify **ListAvailable** .</span></span>

<span data-ttu-id="f7638-257">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="f7638-257">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PsSession, Available, CimSession
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f7638-258">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="f7638-258">CommonParameters</span></span>

<span data-ttu-id="f7638-259">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="f7638-259">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f7638-260">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="f7638-260">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="f7638-261">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="f7638-261">INPUTS</span></span>

### <span data-ttu-id="f7638-262">System.String</span><span class="sxs-lookup"><span data-stu-id="f7638-262">System.String</span></span>

<span data-ttu-id="f7638-263">Sie können Modulnamen an dieses Cmdlet weiterreichen.</span><span class="sxs-lookup"><span data-stu-id="f7638-263">You can pipe module names to this cmdlet.</span></span>

## <span data-ttu-id="f7638-264">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="f7638-264">OUTPUTS</span></span>

### <span data-ttu-id="f7638-265">System. Management. Automation. psmoduleinfo</span><span class="sxs-lookup"><span data-stu-id="f7638-265">System.Management.Automation.PSModuleInfo</span></span>

<span data-ttu-id="f7638-266">Dieses Cmdlet gibt Objekte zurück, die Module darstellen.</span><span class="sxs-lookup"><span data-stu-id="f7638-266">This cmdlet returns objects that represent modules.</span></span>
<span data-ttu-id="f7638-267">Wenn Sie den **listavailable** -Parameter angeben, `Get-Module` gibt ein **moduleinfogruppierung** -Objekt zurück, bei dem es sich um den Typ des **psmoduleinfo** -Objekts handelt, das über die gleichen Eigenschaften und Methoden verfügt.</span><span class="sxs-lookup"><span data-stu-id="f7638-267">When you specify the **ListAvailable** parameter, `Get-Module` returns a **ModuleInfoGrouping** object, which is a type of **PSModuleInfo** object that has the same properties and methods.</span></span>

## <span data-ttu-id="f7638-268">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="f7638-268">NOTES</span></span>

- <span data-ttu-id="f7638-269">Ab Windows PowerShell 3,0 werden die in PowerShell enthaltenen Hauptbefehle in Module gepackt.</span><span class="sxs-lookup"><span data-stu-id="f7638-269">Beginning in Windows PowerShell 3.0, the core commands that are included in PowerShell are packaged in modules.</span></span> <span data-ttu-id="f7638-270">Die Ausnahme ist " **Microsoft. PowerShell. Core** ", bei der es sich um ein Snap-in ( **PSSnapIn** ) handelt.</span><span class="sxs-lookup"><span data-stu-id="f7638-270">The exception is **Microsoft.PowerShell.Core** , which is a snap-in ( **PSSnapin** ).</span></span> <span data-ttu-id="f7638-271">Standardmäßig wird nur das **Microsoft.PowerShell.Core** -Snap-In der Sitzung hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="f7638-271">By default, only the **Microsoft.PowerShell.Core** snap-in is added to the session.</span></span>
<span data-ttu-id="f7638-272">Module werden bei der ersten Verwendung automatisch importiert, und Sie können das `Import-Module` Cmdlet verwenden, um Sie zu importieren.</span><span class="sxs-lookup"><span data-stu-id="f7638-272">Modules are imported automatically on first use and you can use the `Import-Module` cmdlet to import them.</span></span>
- <span data-ttu-id="f7638-273">Ab Windows PowerShell 3,0 werden die mit PowerShell installierten Hauptbefehle in Module gepackt.</span><span class="sxs-lookup"><span data-stu-id="f7638-273">Starting in Windows PowerShell 3.0, the core commands that are installed with PowerShell are packaged in modules.</span></span> <span data-ttu-id="f7638-274">In Windows PowerShell 2,0 und in Host Programmen, die in neueren Versionen von PowerShell ältere Sitzungen erstellen, werden die Hauptbefehle in Snap-Ins ( **pssnapins** ) gepackt.</span><span class="sxs-lookup"><span data-stu-id="f7638-274">In Windows PowerShell 2.0, and in host programs that create older-style sessions in later versions of PowerShell, the core commands are packaged in snap-ins ( **PSSnapins** ).</span></span> <span data-ttu-id="f7638-275">Die Ausnahme ist **Microsoft. PowerShell. Core** , bei der es sich immer um ein Snap-in handelt.</span><span class="sxs-lookup"><span data-stu-id="f7638-275">The exception is **Microsoft.PowerShell.Core** , which is always a snap-in.</span></span> <span data-ttu-id="f7638-276">Remote Sitzungen, wie z. b. die vom `New-PSSession` Cmdlet gestarteten, sind auch ältere Sitzungen, die Core-Snap-Ins enthalten.</span><span class="sxs-lookup"><span data-stu-id="f7638-276">Also, remote sessions, such as those started by the `New-PSSession` cmdlet, are older-style sessions that include core snap-ins.</span></span>

  <span data-ttu-id="f7638-277">Weitere Informationen über die **CreateDefault2** -Methode, die Sitzungen im neueren Stil mit Kernmodulen erstellt, finden Sie unter [CreateDefault2-Methode](/dotnet/api/system.management.automation.runspaces.initialsessionstate.createdefault2) in der MSDN Library.</span><span class="sxs-lookup"><span data-stu-id="f7638-277">For information about the **CreateDefault2** method that creates newer-style sessions with core modules, see [CreateDefault2 Method](/dotnet/api/system.management.automation.runspaces.initialsessionstate.createdefault2) in the MSDN library.</span></span>

- <span data-ttu-id="f7638-278">`Get-Module` Ruft nur Module an Speicherorten ab, die im Wert der **psmodulepath** -Umgebungsvariablen gespeichert sind ($env:P smodulepath).</span><span class="sxs-lookup"><span data-stu-id="f7638-278">`Get-Module` only gets modules in locations that are stored in the value of the **PSModulePath** environment variable ($env:PSModulePath).</span></span> <span data-ttu-id="f7638-279">Sie können den **path** -Parameter des `Import-Module` Cmdlets verwenden, um Module an anderen Speicherorten zu importieren, aber Sie können das `Get-Module` Cmdlet nicht verwenden, um Sie zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="f7638-279">You can use the **Path** parameter of the `Import-Module` cmdlet to import modules in other locations, but you cannot use the `Get-Module` cmdlet to get them.</span></span>
- <span data-ttu-id="f7638-280">Außerdem wurden ab PowerShell 3,0 neue Eigenschaften zum Objekt hinzugefügt, das zurückgibt, die das `Get-Module` Erlernen von Modulen vor dem Importieren vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="f7638-280">Also, starting in PowerShell 3.0, new properties have been added to the object that `Get-Module` returns that make it easier to learn about modules even before they are imported.</span></span> <span data-ttu-id="f7638-281">Alle Eigenschaften werden vor dem Importieren aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="f7638-281">All properties are populated before importing.</span></span> <span data-ttu-id="f7638-282">Hierzu gehören die **exportedcommands** -, **exportedcmdlets** -und **exportedfunctions** -Eigenschaften, die die Befehle auflisten, die das Modul exportiert.</span><span class="sxs-lookup"><span data-stu-id="f7638-282">These include the **ExportedCommands** , **ExportedCmdlets** and **ExportedFunctions** properties that list the commands that the module exports.</span></span>
- <span data-ttu-id="f7638-283">Der **listavailable** -Parameter ruft nur wohlgeformte Module ab, d. h. Ordner, die mindestens eine Datei enthalten, deren Basisname mit dem Namen des Modul Ordners identisch ist.</span><span class="sxs-lookup"><span data-stu-id="f7638-283">The **ListAvailable** parameter gets only well-formed modules, that is, folders that contain at least one file whose base name is the same as the name of the module folder.</span></span> <span data-ttu-id="f7638-284">Der Basisname ist der Name ohne die Dateinamenerweiterung.</span><span class="sxs-lookup"><span data-stu-id="f7638-284">The base name is the name without the file name extension.</span></span> <span data-ttu-id="f7638-285">Ordner, die Dateien mit unterschiedlichen Namen enthalten, gelten als Container, jedoch nicht als Module.</span><span class="sxs-lookup"><span data-stu-id="f7638-285">Folders that contain files that have different names are considered to be containers, but not modules.</span></span>

  <span data-ttu-id="f7638-286">Zum erhalten von Modulen, die als DLL-Dateien implementiert sind, aber nicht in einem Modul Ordner enthalten sind, geben Sie sowohl den **listavailable** -Parameter als auch **alle** -Parameter an.</span><span class="sxs-lookup"><span data-stu-id="f7638-286">To get modules that are implemented as .dll files, but are not enclosed in a module folder, specify both the **ListAvailable** and **All** parameters.</span></span>

- <span data-ttu-id="f7638-287">Um die CIM-Sitzung zu verwenden, müssen auf dem Remotecomputer WS-Management-Remoting und Windows-Verwaltungsinstrumentation (WMI) verfügbar sein, wobei es sich um die Microsoft-Implementierung des Common Information Model (CIM)-Standards handelt.</span><span class="sxs-lookup"><span data-stu-id="f7638-287">To use the CIM session feature, the remote computer must have WS-Management remoting and Windows Management Instrumentation (WMI), which is the Microsoft implementation of the Common Information Model (CIM) standard.</span></span> <span data-ttu-id="f7638-288">Auf dem Computer muss außerdem der WMI-Anbieter für die Modulerkennung oder ein alternativer WMI-Anbieter vorhanden sein, der die gleichen grundlegenden Funktionen bietet.</span><span class="sxs-lookup"><span data-stu-id="f7638-288">The computer must also have the Module Discovery WMI provider or an alternate WMI provider that has the same basic features.</span></span>

  <span data-ttu-id="f7638-289">Sie können die CIM-Sitzungs Funktion auf Computern verwenden, auf denen das Windows-Betriebssystem nicht ausgeführt wird, sowie auf Windows-Computern, auf denen PowerShell ausgeführt wird, für die PowerShell-Remoting jedoch nicht aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="f7638-289">You can use the CIM session feature on computers that are not running the Windows operating system and on Windows computers that have PowerShell, but do not have PowerShell remoting enabled.</span></span>

  <span data-ttu-id="f7638-290">Sie können auch die CIM-Parameter verwenden, um CIM-Module von Computern zu erhalten, auf denen PowerShell-Remoting aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="f7638-290">You can also use the CIM parameters to get CIM modules from computers that have PowerShell remoting enabled.</span></span> <span data-ttu-id="f7638-291">Dies schließt den lokalen Computer ein.</span><span class="sxs-lookup"><span data-stu-id="f7638-291">This includes the local computer.</span></span>
<span data-ttu-id="f7638-292">Wenn Sie eine CIM-Sitzung auf dem lokalen Computer erstellen, verwendet PowerShell DCOM anstelle von WMI, um die Sitzung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="f7638-292">When you create a CIM session on the local computer, PowerShell uses DCOM, instead of WMI, to create the session.</span></span>

## <span data-ttu-id="f7638-293">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="f7638-293">RELATED LINKS</span></span>

[<span data-ttu-id="f7638-294">Get-CimSession</span><span class="sxs-lookup"><span data-stu-id="f7638-294">Get-CimSession</span></span>](../CimCmdlets/Get-CimSession.md)

[<span data-ttu-id="f7638-295">New-CimSession</span><span class="sxs-lookup"><span data-stu-id="f7638-295">New-CimSession</span></span>](../CimCmdlets/New-CimSession.md)

[<span data-ttu-id="f7638-296">about_Modules</span><span class="sxs-lookup"><span data-stu-id="f7638-296">about_Modules</span></span>](About/about_Modules.md)

[<span data-ttu-id="f7638-297">Get-PSSession</span><span class="sxs-lookup"><span data-stu-id="f7638-297">Get-PSSession</span></span>](Get-PSSession.md)

[<span data-ttu-id="f7638-298">Import-Module</span><span class="sxs-lookup"><span data-stu-id="f7638-298">Import-Module</span></span>](Import-Module.md)

[<span data-ttu-id="f7638-299">Import-PSSession</span><span class="sxs-lookup"><span data-stu-id="f7638-299">Import-PSSession</span></span>](../Microsoft.PowerShell.Utility/Import-PSSession.md)

[<span data-ttu-id="f7638-300">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="f7638-300">New-PSSession</span></span>](New-PSSession.md)

[<span data-ttu-id="f7638-301">Remove-Module</span><span class="sxs-lookup"><span data-stu-id="f7638-301">Remove-Module</span></span>](Remove-Module.md)