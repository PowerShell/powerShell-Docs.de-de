---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-alias?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Alias
ms.openlocfilehash: e0a08a4ee6f00702f765bc359a20bf9e30b9b1c5
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213108"
---
# <span data-ttu-id="04209-103">Get-Alias</span><span class="sxs-lookup"><span data-stu-id="04209-103">Get-Alias</span></span>

## <span data-ttu-id="04209-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="04209-104">SYNOPSIS</span></span>
<span data-ttu-id="04209-105">Ruft die Aliase für die aktuelle Sitzung ab.</span><span class="sxs-lookup"><span data-stu-id="04209-105">Gets the aliases for the current session.</span></span>

## <span data-ttu-id="04209-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="04209-106">SYNTAX</span></span>

### <span data-ttu-id="04209-107">Standard (Standard)</span><span class="sxs-lookup"><span data-stu-id="04209-107">Default (Default)</span></span>

```
Get-Alias [[-Name] <String[]>] [-Exclude <String[]>] [-Scope <String>] [<CommonParameters>]
```

### <span data-ttu-id="04209-108">Definition</span><span class="sxs-lookup"><span data-stu-id="04209-108">Definition</span></span>

```
Get-Alias [-Exclude <String[]>] [-Scope <String>] [-Definition <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="04209-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="04209-109">DESCRIPTION</span></span>

<span data-ttu-id="04209-110">Das **Get-Alias-** Cmdlet ruft die Aliase in der aktuellen Sitzung ab.</span><span class="sxs-lookup"><span data-stu-id="04209-110">The **Get-Alias** cmdlet gets the aliases in the current session.</span></span>
<span data-ttu-id="04209-111">Dies umfasst integrierte Aliase, Aliase, die Sie festgelegt oder importiert haben, und Aliase, die Sie Ihrem PowerShell-Profil hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="04209-111">This includes built-in aliases, aliases that you have set or imported, and aliases that you have added to your PowerShell profile.</span></span>

<span data-ttu-id="04209-112">Standardmäßig nimmt **Get-Alias** einen Alias an und gibt den Befehlsnamen zurück.</span><span class="sxs-lookup"><span data-stu-id="04209-112">By default, **Get-Alias** takes an alias and returns the command name.</span></span>
<span data-ttu-id="04209-113">Wenn Sie den *Definition* -Parameter verwenden, nimmt **Get-Alias** einen Befehlsnamen an und gibt dessen Aliase zurück.</span><span class="sxs-lookup"><span data-stu-id="04209-113">When you use the *Definition* parameter, **Get-Alias** takes a command name and returns its aliases.</span></span>

<span data-ttu-id="04209-114">Ab Windows PowerShell 3,0 zeigt **Get-Alias** nicht-hyphenated-Alias Namen in einem `<alias> -> <definition>` Format an, um die Suche nach benötigten Informationen noch einfacher zu gestalten.</span><span class="sxs-lookup"><span data-stu-id="04209-114">Beginning in Windows PowerShell 3.0, **Get-Alias** displays non-hyphenated alias names in an `<alias> -> <definition>` format to make it even easier to find the information that you need.</span></span>

## <span data-ttu-id="04209-115">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="04209-115">EXAMPLES</span></span>

### <span data-ttu-id="04209-116">Beispiel 1: alle Aliase in der aktuellen Sitzung erhalten</span><span class="sxs-lookup"><span data-stu-id="04209-116">Example 1: Get all aliases in the current session</span></span>

```
PS C:\> Get-Alias

CommandType     Name
-----------     ----
Alias           % -> ForEach-Object
Alias           ? -> Where-Object
Alias           ac -> Add-Content
Alias           asnp -> Add-PSSnapin
Alias           cat -> Get-Content
Alias           cd -> Set-Location
Alias           chdir -> Set-Location
Alias           clc -> Clear-Content
Alias           clear -> Clear-Host
Alias           clhy -> Clear-History
...
```

<span data-ttu-id="04209-117">Dieser Befehl ruft alle Aliase in der aktuellen Sitzung ab.</span><span class="sxs-lookup"><span data-stu-id="04209-117">This command gets all aliases in the current session.</span></span>

<span data-ttu-id="04209-118">Die Ausgabe zeigt das `<alias> -> <definition>` Format an, das in Windows PowerShell 3,0 eingeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="04209-118">The output shows the `<alias> -> <definition>` format that was introduced in Windows PowerShell 3.0.</span></span>
<span data-ttu-id="04209-119">Dieses Format wird nur für Aliase verwendet, die keine Bindestriche enthalten, weil Aliase mit Bindestrichen in der Regel bevorzugte Namen für Cmdlets und Funktionen und keine Spitznamen sind.</span><span class="sxs-lookup"><span data-stu-id="04209-119">This format is used only for aliases that do not include hyphens, because aliases with hyphens are typically preferred names for cmdlets and functions, rather than nicknames.</span></span>

### <span data-ttu-id="04209-120">Beispiel 2: erhalten von Aliasen nach Namen</span><span class="sxs-lookup"><span data-stu-id="04209-120">Example 2: Get aliases by name</span></span>

```powershell
Get-Alias -Name gp*, sp* -Exclude *ps
```

<span data-ttu-id="04209-121">Dieser Befehl ruft alle Aliase ab, die mit GP oder SP beginnen, mit Ausnahme der Aliase, die mit PS enden.</span><span class="sxs-lookup"><span data-stu-id="04209-121">This command gets all aliases that begin with gp or sp, except for aliases that end with ps.</span></span>

### <span data-ttu-id="04209-122">Beispiel 3: erhalten von Aliasen für ein Cmdlet</span><span class="sxs-lookup"><span data-stu-id="04209-122">Example 3: Get aliases for a cmdlet</span></span>

```powershell
Get-Alias -Definition Get-ChildItem
```

<span data-ttu-id="04209-123">Dieser Befehl ruft die Aliase für das Get-ChildItem-Cmdlet ab.</span><span class="sxs-lookup"><span data-stu-id="04209-123">This command gets the aliases for the Get-ChildItem cmdlet.</span></span>

<span data-ttu-id="04209-124">Standardmäßig ruft das **Get-Alias-** Cmdlet den Elementnamen ab, wenn Sie den Alias kennen.</span><span class="sxs-lookup"><span data-stu-id="04209-124">By default, the **Get-Alias** cmdlet gets the item name when you know the alias.</span></span>
<span data-ttu-id="04209-125">Der *Definition* -Parameter ruft den Alias ab, wenn Sie den Elementnamen kennen.</span><span class="sxs-lookup"><span data-stu-id="04209-125">The *Definition* parameter gets the alias when you know the item name.</span></span>

### <span data-ttu-id="04209-126">Beispiel 4: erhalten von Aliasen nach Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="04209-126">Example 4: Get aliases by property</span></span>

```powershell
Get-Alias | Where-Object {$_.Options -Match "ReadOnly"}
```

<span data-ttu-id="04209-127">Dieser Befehl ruft alle Aliase ab, in denen der Wert der Options-Eigenschaft schreibgeschützt ist.</span><span class="sxs-lookup"><span data-stu-id="04209-127">This command gets all aliases in which the value of the Options property is ReadOnly.</span></span>
<span data-ttu-id="04209-128">Dieser Befehl bietet eine schnelle Möglichkeit, die in PowerShell integrierten Aliase zu finden, da Sie über die Option "schreibgeschützt" verfügen.</span><span class="sxs-lookup"><span data-stu-id="04209-128">This command provides a quick way to find the aliases that are built into PowerShell, because they have the ReadOnly option.</span></span>

<span data-ttu-id="04209-129">"Options" ist nur eine Eigenschaft der AliasInfo-Objekte, die von **Get-Alias abgerufen werden** .</span><span class="sxs-lookup"><span data-stu-id="04209-129">Options is just one property of the AliasInfo objects that **Get-Alias** gets.</span></span>
<span data-ttu-id="04209-130">Um alle Eigenschaften und Methoden von AliasInfo-Objekten zu suchen, geben Sie ein `Get-Alias | get-member` .</span><span class="sxs-lookup"><span data-stu-id="04209-130">To find all properties and methods of AliasInfo objects, type `Get-Alias | get-member`.</span></span>

### <span data-ttu-id="04209-131">Beispiel 5: erhalten von Aliasen nach Name und Filtern nach dem Anfangsbuchstaben</span><span class="sxs-lookup"><span data-stu-id="04209-131">Example 5: Get aliases by name and filter by beginning letter</span></span>

```powershell
Get-Alias -Definition "*-PSSession" -Exclude e* -Scope Global
```

<span data-ttu-id="04209-132">In diesem Beispiel werden Aliase für Befehle abgerufen, deren Namen mit „-PSSession“ enden, mit Ausnahme der Aliase, die mit „e“ beginnen.</span><span class="sxs-lookup"><span data-stu-id="04209-132">This example gets aliases for commands that have names that end in "-PSSession", except for those that begin with "e".</span></span>

<span data-ttu-id="04209-133">Der Befehl verwendet den *Scope* -Parameter, um den Befehl im globalen Gültigkeitsbereich anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="04209-133">The command uses the *Scope* parameter to apply the command in the global scope.</span></span>
<span data-ttu-id="04209-134">Dies empfiehlt sich in Skripts, wenn Sie die Aliase in der Sitzung abrufen möchten.</span><span class="sxs-lookup"><span data-stu-id="04209-134">This is useful in scripts when you want to get the aliases in the session.</span></span>

## <span data-ttu-id="04209-135">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="04209-135">PARAMETERS</span></span>

### <span data-ttu-id="04209-136">-Definition</span><span class="sxs-lookup"><span data-stu-id="04209-136">-Definition</span></span>

<span data-ttu-id="04209-137">Ruft die Aliase für das angegebene Element ab.</span><span class="sxs-lookup"><span data-stu-id="04209-137">Gets the aliases for the specified item.</span></span>
<span data-ttu-id="04209-138">Geben Sie den Namen eines Cmdlets, einer Funktion, eines Skripts, einer Datei oder einer ausführbaren Datei ein.</span><span class="sxs-lookup"><span data-stu-id="04209-138">Enter the name of a cmdlet, function, script, file, or executable file.</span></span>

<span data-ttu-id="04209-139">Dieser Parameter wird als " *Definition* " bezeichnet, da er in der Definition-Eigenschaft des Alias Objekts nach dem Elementnamen sucht.</span><span class="sxs-lookup"><span data-stu-id="04209-139">This parameter is called *Definition* , because it searches for the item name in the Definition property of the alias object.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Definition
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="04209-140">-Ausschließen</span><span class="sxs-lookup"><span data-stu-id="04209-140">-Exclude</span></span>

<span data-ttu-id="04209-141">Lässt die angegebenen Elemente aus.</span><span class="sxs-lookup"><span data-stu-id="04209-141">Omits the specified items.</span></span>
<span data-ttu-id="04209-142">Der Wert dieses Parameters qualifiziert die Name- und Definition-Parameter.</span><span class="sxs-lookup"><span data-stu-id="04209-142">The value of this parameter qualifies the Name and Definition parameters.</span></span>
<span data-ttu-id="04209-143">Geben Sie einen Namen, eine Definition oder ein Muster wie z. B. „s\*“ ein.</span><span class="sxs-lookup"><span data-stu-id="04209-143">Enter a name, a definition, or a pattern, such as "s\*".</span></span>
<span data-ttu-id="04209-144">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="04209-144">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="04209-145">-Name</span><span class="sxs-lookup"><span data-stu-id="04209-145">-Name</span></span>

<span data-ttu-id="04209-146">Gibt die Aliase an, die dieses Cmdlet abruft.</span><span class="sxs-lookup"><span data-stu-id="04209-146">Specifies the aliases that this cmdlet gets.</span></span>
<span data-ttu-id="04209-147">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="04209-147">Wildcards are permitted.</span></span>
<span data-ttu-id="04209-148">Standardmäßig `Get-Alias` Ruft alle Aliase ab, die für die aktuelle Sitzung definiert sind.</span><span class="sxs-lookup"><span data-stu-id="04209-148">By default, `Get-Alias` retrieves all aliases defined for the current session.</span></span>
<span data-ttu-id="04209-149">Der Parameter Name **Name** ist optional.</span><span class="sxs-lookup"><span data-stu-id="04209-149">The parameter name **Name** is optional.</span></span>
<span data-ttu-id="04209-150">Sie können Aliasnamen auch über die Pipeline an senden `Get-Alias` .</span><span class="sxs-lookup"><span data-stu-id="04209-150">You can also pipe alias names to `Get-Alias`.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Default
Aliases:

Required: False
Position: 0
Default value: All aliases
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="04209-151">-Bereich</span><span class="sxs-lookup"><span data-stu-id="04209-151">-Scope</span></span>

<span data-ttu-id="04209-152">Gibt den Bereich an, für den dieses Cmdlet Aliase abrufen soll.</span><span class="sxs-lookup"><span data-stu-id="04209-152">Specifies the scope for which this cmdlet gets aliases.</span></span>
<span data-ttu-id="04209-153">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="04209-153">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="04209-154">Global</span><span class="sxs-lookup"><span data-stu-id="04209-154">Global</span></span>
- <span data-ttu-id="04209-155">Lokal</span><span class="sxs-lookup"><span data-stu-id="04209-155">Local</span></span>
- <span data-ttu-id="04209-156">Skript</span><span class="sxs-lookup"><span data-stu-id="04209-156">Script</span></span>
- <span data-ttu-id="04209-157">Eine Zahl relativ zum aktuellen Bereich (0 bis zur Anzahl der Bereiche, wobei 0 der aktuelle Bereich und 1 der übergeordnete Bereich ist)</span><span class="sxs-lookup"><span data-stu-id="04209-157">A number relative to the current scope (0 through the number of scopes, where 0 is the current scope and 1 is its parent)</span></span>

<span data-ttu-id="04209-158">Local ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="04209-158">Local is the default.</span></span>
<span data-ttu-id="04209-159">Weitere Informationen finden Sie unter „about_Scopes“.</span><span class="sxs-lookup"><span data-stu-id="04209-159">For more information, see about_Scopes.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Local
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="04209-160">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="04209-160">CommonParameters</span></span>

<span data-ttu-id="04209-161">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="04209-161">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="04209-162">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="04209-162">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="04209-163">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="04209-163">INPUTS</span></span>

### <span data-ttu-id="04209-164">System.String</span><span class="sxs-lookup"><span data-stu-id="04209-164">System.String</span></span>

<span data-ttu-id="04209-165">Sie können Aliasnamen an **Get-Alias** übergeben.</span><span class="sxs-lookup"><span data-stu-id="04209-165">You can pipe alias names to **Get-Alias** .</span></span>

## <span data-ttu-id="04209-166">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="04209-166">OUTPUTS</span></span>

### <span data-ttu-id="04209-167">System. Management. Automation. AliasInfo</span><span class="sxs-lookup"><span data-stu-id="04209-167">System.Management.Automation.AliasInfo</span></span>

<span data-ttu-id="04209-168">**Get-Alias** gibt ein Objekt zurück, das jeden Alias darstellt.</span><span class="sxs-lookup"><span data-stu-id="04209-168">**Get-Alias** returns an object that represents each alias.</span></span>
<span data-ttu-id="04209-169">**Get-Alias** gibt das gleiche Objekt für jeden Alias zurück, aber PowerShell verwendet ein Pfeil basiertes Format, um die Namen der nicht-Bindestriche anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="04209-169">**Get-Alias** returns the same object for every alias, but PowerShell uses an arrow-based format to display the names of non-hyphenated aliases.</span></span>

## <span data-ttu-id="04209-170">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="04209-170">NOTES</span></span>

- <span data-ttu-id="04209-171">Um einen neuen Alias zu erstellen, verwenden Sie Set-Alias oder New-Alias.</span><span class="sxs-lookup"><span data-stu-id="04209-171">To create a new alias, use Set-Alias or New-Alias.</span></span> <span data-ttu-id="04209-172">Verwenden Sie zum Löschen eines Alias Remove-Item.</span><span class="sxs-lookup"><span data-stu-id="04209-172">To delete an alias, use Remove-Item.</span></span>
- <span data-ttu-id="04209-173">Das pfeilbasierte Aliasnamensformat wird nicht für Aliase verwendet, die einen Bindestrich enthalten.</span><span class="sxs-lookup"><span data-stu-id="04209-173">The arrow-based alias name format is not used for aliases that include a hyphen.</span></span> <span data-ttu-id="04209-174">Dabei handelt es sich wahrscheinlich um bevorzugte Ersatznamen für Cmdlets und Funktionen anstelle der üblichen Abkürzungen und Spitznamen.</span><span class="sxs-lookup"><span data-stu-id="04209-174">These are likely to be preferred substitute names for cmdlets and functions, instead of typical abbreviations or nicknames.</span></span>

## <span data-ttu-id="04209-175">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="04209-175">RELATED LINKS</span></span>

[<span data-ttu-id="04209-176">Export-Alias</span><span class="sxs-lookup"><span data-stu-id="04209-176">Export-Alias</span></span>](Export-Alias.md)

[<span data-ttu-id="04209-177">Import-Alias</span><span class="sxs-lookup"><span data-stu-id="04209-177">Import-Alias</span></span>](Import-Alias.md)

[<span data-ttu-id="04209-178">New-Alias</span><span class="sxs-lookup"><span data-stu-id="04209-178">New-Alias</span></span>](New-Alias.md)

[<span data-ttu-id="04209-179">Set-Alias</span><span class="sxs-lookup"><span data-stu-id="04209-179">Set-Alias</span></span>](Set-Alias.md)

[<span data-ttu-id="04209-180">Aliasanbieter</span><span class="sxs-lookup"><span data-stu-id="04209-180">Alias Provider</span></span>](../Microsoft.PowerShell.Core/About/about_Alias_Provider.md)

[<span data-ttu-id="04209-181">about_Aliases</span><span class="sxs-lookup"><span data-stu-id="04209-181">about_Aliases</span></span>](../Microsoft.PowerShell.Core/About/about_Aliases.md)
