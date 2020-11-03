---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 5/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-itempropertyvalue?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ItemPropertyValue
ms.openlocfilehash: fe49b968c859060b6f1c82c27bac87b33dabe079
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93216327"
---
# <span data-ttu-id="564ee-103">Get-ItemPropertyValue</span><span class="sxs-lookup"><span data-stu-id="564ee-103">Get-ItemPropertyValue</span></span>

## <span data-ttu-id="564ee-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="564ee-104">SYNOPSIS</span></span>
<span data-ttu-id="564ee-105">Ruft den Wert für eine oder mehrere Eigenschaften eines angegebenen Elements ab.</span><span class="sxs-lookup"><span data-stu-id="564ee-105">Gets the value for one or more properties of a specified item.</span></span>

## <span data-ttu-id="564ee-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="564ee-106">SYNTAX</span></span>

### <span data-ttu-id="564ee-107">Pfad (Standard)</span><span class="sxs-lookup"><span data-stu-id="564ee-107">Path (Default)</span></span>

```
Get-ItemPropertyValue [[-Path] <String[]>] [-Name] <String[]> [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-Credential <PSCredential>] [<CommonParameters>]
```

### <span data-ttu-id="564ee-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="564ee-108">LiteralPath</span></span>

```
Get-ItemPropertyValue -LiteralPath <String[]> [-Name] <String[]> [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-Credential <PSCredential>] [<CommonParameters>]
```

## <span data-ttu-id="564ee-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="564ee-109">DESCRIPTION</span></span>

<span data-ttu-id="564ee-110">Der ruft `Get-ItemPropertyValue` den aktuellen Wert für eine Eigenschaft ab, die Sie angeben, wenn Sie den *Name* -Parameter verwenden, der sich in einem Pfad befindet, den Sie mit dem *path* -Parameter oder dem *literalpath* -Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="564ee-110">The `Get-ItemPropertyValue` gets the current value for a property that you specify when you use the *Name* parameter, located in a path that you specify with either the *Path* or *LiteralPath* parameters.</span></span>

## <span data-ttu-id="564ee-111">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="564ee-111">EXAMPLES</span></span>

### <span data-ttu-id="564ee-112">Beispiel 1: erhalten des Werts der ProductID-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="564ee-112">Example 1: Get the value of the ProductID property</span></span>

<span data-ttu-id="564ee-113">Mit diesem Befehl wird der Wert der **ProductID-** Eigenschaft des Objekts "\SOFTWARE\Microsoft\Windows NT\CurrentVersion" im Windows-Registrierungs Anbieter abgerufen.</span><span class="sxs-lookup"><span data-stu-id="564ee-113">This command gets the value of the **ProductID** property of the "\SOFTWARE\Microsoft\Windows NT\CurrentVersion" object in the Windows Registry provider.</span></span>

```powershell
Get-ItemPropertyValue 'HKLM:\SOFTWARE\Microsoft\Windows NT\CurrentVersion' -Name ProductID
```

```output
94253-50000-11141-AA785
```

### <span data-ttu-id="564ee-114">Beispiel 2: erhalten der letzten Schreibzeit einer Datei oder eines Ordners</span><span class="sxs-lookup"><span data-stu-id="564ee-114">Example 2: Get the last write time of a file or folder</span></span>

<span data-ttu-id="564ee-115">Mit diesem Befehl wird der Wert der **LastWrite Time** -Eigenschaft oder der Zeitpunkt der letzten Änderung einer Datei oder eines Ordners aus dem Ordner "c:\users\test\documents\modulecomassembly" abgerufen, der im File System-Anbieter funktioniert.</span><span class="sxs-lookup"><span data-stu-id="564ee-115">This command gets the value of the **LastWriteTime** property, or the last time a file or folder was changed, from the "C:\Users\Test\Documents\ModuleToAssembly" folder, working in the FileSystem provider.</span></span>

```powershell
Get-ItemPropertyValue -Path C:\Users\Test\Documents\ModuleToAssembly -Name LastWriteTime
```

```output
Wednesday, September 3, 2014 2:53:22 PM
```

### <span data-ttu-id="564ee-116">Beispiel 3: erhalten mehrerer Eigenschaftswerte einer Datei oder eines Ordners</span><span class="sxs-lookup"><span data-stu-id="564ee-116">Example 3: Get multiple property values of a file or folder</span></span>

<span data-ttu-id="564ee-117">Mit diesem Befehl werden die Werte der Eigenschaften " **lastschreitetime** ", " **kreationtime** " und " **root** " eines Ordners abgerufen.</span><span class="sxs-lookup"><span data-stu-id="564ee-117">This command gets the values of the **LastWriteTime** , **CreationTime** , and **Root** properties of a folder.</span></span> <span data-ttu-id="564ee-118">Die Eigenschaftswerte werden in der Reihenfolge zurückgegeben, in der Sie die Eigenschaftsnamen angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="564ee-118">The property values are returned in the order in which you specified the property names.</span></span>

```powershell
Get-ItemPropertyValue -Path C:\Users\Test\Documents\ModuleToAssembly -Name LastWriteTime,CreationTime,Root
```

```output
Wednesday, September 3, 2014 2:53:22 PM
Wednesday, September 3, 2014 2:53:10 PM

Name              : C:\
Parent            :
Exists            : True
Root              : C:\
FullName          : C:\
Extension         :
CreationTime      : 9/1/2014 4:59:45 AM
CreationTimeUtc   : 9/1/2014 11:59:45 AM
LastAccessTime    : 9/27/2014 5:22:02 PM
LastAccessTimeUtc : 9/28/2014 12:22:02 AM
LastWriteTime     : 9/27/2014 5:22:02 PM
LastWriteTimeUtc  : 9/28/2014 12:22:02 AM
Attributes        : Hidden, System, Directory
BaseName          : C:\
Target            :
LinkType          :
Mode              : d--hs-
```

## <span data-ttu-id="564ee-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="564ee-119">PARAMETERS</span></span>

### <span data-ttu-id="564ee-120">-Credential</span><span class="sxs-lookup"><span data-stu-id="564ee-120">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="564ee-121">Dieser Parameter wird von Anbietern, die mit PowerShell installiert wurden, nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="564ee-121">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="564ee-122">Verwenden Sie zum Annehmen der Identität eines anderen Benutzers oder zum herauf Stufen ihrer Anmelde Informationen bei der Ausführung dieses Cmdlets "Start [-Command](../Microsoft.PowerShell.Core/Invoke-Command.md)".</span><span class="sxs-lookup"><span data-stu-id="564ee-122">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="564ee-123">-Ausschließen</span><span class="sxs-lookup"><span data-stu-id="564ee-123">-Exclude</span></span>

<span data-ttu-id="564ee-124">Gibt als Zeichen folgen Array ein Element oder Elemente an, die von diesem Cmdlet im Vorgang ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="564ee-124">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="564ee-125">Der Wert dieses Parameters qualifiziert den **Path** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="564ee-125">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="564ee-126">Geben Sie ein Pfad Element oder-Muster ein, z `*.txt` . b..</span><span class="sxs-lookup"><span data-stu-id="564ee-126">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="564ee-127">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="564ee-127">Wildcard characters are permitted.</span></span> <span data-ttu-id="564ee-128">Der **Exclude** -Parameter ist nur wirksam, wenn der-Befehl den Inhalt eines Elements enthält, z `C:\Windows\*` . b., wobei das Platzhalter Zeichen den Inhalt des `C:\Windows` Verzeichnisses angibt.</span><span class="sxs-lookup"><span data-stu-id="564ee-128">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="564ee-129">-Filter</span><span class="sxs-lookup"><span data-stu-id="564ee-129">-Filter</span></span>

<span data-ttu-id="564ee-130">Gibt einen Filter zum Qualifizieren des **path** -Parameters an.</span><span class="sxs-lookup"><span data-stu-id="564ee-130">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="564ee-131">Der [File System](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) -Anbieter ist der einzige installierte PowerShell-Anbieter, der die Verwendung von Filtern unterstützt.</span><span class="sxs-lookup"><span data-stu-id="564ee-131">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="564ee-132">Die Syntax für die Filter Sprache des **Dateisystems** finden Sie in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="564ee-132">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="564ee-133">Filter sind effizienter als andere Parameter, da Sie vom Anbieter angewendet werden, wenn das Cmdlet die Objekte abruft, statt dass PowerShell die Objekte nach dem Abrufen filtert.</span><span class="sxs-lookup"><span data-stu-id="564ee-133">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="564ee-134">-Include</span><span class="sxs-lookup"><span data-stu-id="564ee-134">-Include</span></span>

<span data-ttu-id="564ee-135">Gibt als Zeichen folgen Array ein Element oder Elemente an, die dieses Cmdlet in den Vorgang einschließt.</span><span class="sxs-lookup"><span data-stu-id="564ee-135">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="564ee-136">Der Wert dieses Parameters qualifiziert den **Path** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="564ee-136">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="564ee-137">Geben Sie ein Pfad Element oder-Muster ein, z `"*.txt"` . b..</span><span class="sxs-lookup"><span data-stu-id="564ee-137">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="564ee-138">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="564ee-138">Wildcard characters are permitted.</span></span> <span data-ttu-id="564ee-139">Der **include** -Parameter ist nur wirksam, wenn der-Befehl den Inhalt eines Elements enthält, z `C:\Windows\*` . b., wobei das Platzhalter Zeichen den Inhalt des `C:\Windows` Verzeichnisses angibt.</span><span class="sxs-lookup"><span data-stu-id="564ee-139">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="564ee-140">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="564ee-140">-LiteralPath</span></span>

<span data-ttu-id="564ee-141">Gibt einen Pfad zu einem oder mehreren Speicherorten an.</span><span class="sxs-lookup"><span data-stu-id="564ee-141">Specifies a path to one or more locations.</span></span> <span data-ttu-id="564ee-142">Der Wert von **literalpath** wird genau so verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="564ee-142">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="564ee-143">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="564ee-143">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="564ee-144">Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="564ee-144">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="564ee-145">Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="564ee-145">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="564ee-146">Weitere Informationen finden Sie unter [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="564ee-146">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="564ee-147">-Name</span><span class="sxs-lookup"><span data-stu-id="564ee-147">-Name</span></span>

<span data-ttu-id="564ee-148">Gibt den Namen der abzurufenden Eigenschaft oder Eigenschaften an.</span><span class="sxs-lookup"><span data-stu-id="564ee-148">Specifies the name of the property or properties to retrieve.</span></span>
<span data-ttu-id="564ee-149">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="564ee-149">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: PSProperty

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="564ee-150">-Path</span><span class="sxs-lookup"><span data-stu-id="564ee-150">-Path</span></span>

<span data-ttu-id="564ee-151">Gibt den Pfad zu den Elementen an.</span><span class="sxs-lookup"><span data-stu-id="564ee-151">Specifies the path to the item or items.</span></span>
<span data-ttu-id="564ee-152">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="564ee-152">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="564ee-153">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="564ee-153">CommonParameters</span></span>

<span data-ttu-id="564ee-154">Dieses Cmdlet unterstützt die allgemeinen Parameter: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` und `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="564ee-154">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="564ee-155">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="564ee-155">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="564ee-156">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="564ee-156">INPUTS</span></span>

### <span data-ttu-id="564ee-157">System.String</span><span class="sxs-lookup"><span data-stu-id="564ee-157">System.String</span></span>

<span data-ttu-id="564ee-158">Sie können eine Zeichenfolge weiterreichen, die einen Pfad zu diesem Cmdlet enthält.</span><span class="sxs-lookup"><span data-stu-id="564ee-158">You can pipe a string that contains a path to this cmdlet.</span></span>

## <span data-ttu-id="564ee-159">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="564ee-159">OUTPUTS</span></span>

### <span data-ttu-id="564ee-160">System. Boolean, System. String, System. DateTime</span><span class="sxs-lookup"><span data-stu-id="564ee-160">System.Boolean, System.String, System.DateTime</span></span>

<span data-ttu-id="564ee-161">Dieses Cmdlet gibt ein Objekt für jeden Elementwert zurück, den es erhält.</span><span class="sxs-lookup"><span data-stu-id="564ee-161">This cmdlet returns an object for each item property value that it gets.</span></span>
<span data-ttu-id="564ee-162">Der Objekttyp hängt von dem abgerufenen Eigenschafts Wert ab.</span><span class="sxs-lookup"><span data-stu-id="564ee-162">The object type depends on the property value that is retrieved.</span></span>
<span data-ttu-id="564ee-163">Beispielsweise kann das Cmdlet in einem Dateisystem Laufwerk eine Datei oder einen Ordner zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="564ee-163">For example, in a file system drive, the cmdlet might return a file or folder.</span></span>

## <span data-ttu-id="564ee-164">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="564ee-164">NOTES</span></span>

<span data-ttu-id="564ee-165">Dieses Cmdlet ist für die Arbeit mit den Daten konzipiert, die von beliebigen Anbietern verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="564ee-165">This cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="564ee-166">Um die in Ihrer Sitzung verfügbaren Anbieter aufzulisten, führen Sie das- `Get-PSProvider` Cmdlet aus.</span><span class="sxs-lookup"><span data-stu-id="564ee-166">To list the providers available in your session, run the `Get-PSProvider` cmdlet.</span></span> <span data-ttu-id="564ee-167">Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="564ee-167">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="564ee-168">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="564ee-168">RELATED LINKS</span></span>

[<span data-ttu-id="564ee-169">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="564ee-169">Get-ItemProperty</span></span>](Get-ItemProperty.md)

[<span data-ttu-id="564ee-170">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="564ee-170">Clear-ItemProperty</span></span>](Clear-ItemProperty.md)

[<span data-ttu-id="564ee-171">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="564ee-171">Copy-ItemProperty</span></span>](Copy-ItemProperty.md)

[<span data-ttu-id="564ee-172">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="564ee-172">Get-PSProvider</span></span>](Get-PSProvider.md)

[<span data-ttu-id="564ee-173">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="564ee-173">Move-ItemProperty</span></span>](Move-ItemProperty.md)

[<span data-ttu-id="564ee-174">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="564ee-174">New-ItemProperty</span></span>](New-ItemProperty.md)

[<span data-ttu-id="564ee-175">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="564ee-175">Remove-ItemProperty</span></span>](Remove-ItemProperty.md)

[<span data-ttu-id="564ee-176">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="564ee-176">Rename-ItemProperty</span></span>](Rename-ItemProperty.md)

[<span data-ttu-id="564ee-177">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="564ee-177">Set-ItemProperty</span></span>](Set-ItemProperty.md)

[<span data-ttu-id="564ee-178">about_Providers</span><span class="sxs-lookup"><span data-stu-id="564ee-178">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)