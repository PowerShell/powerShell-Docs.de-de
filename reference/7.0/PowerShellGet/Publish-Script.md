---
external help file: PSModule-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 03/27/2020
online version: https://docs.microsoft.com/powershell/module/powershellget/publish-script?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Publish-Script
ms.openlocfilehash: a67610fdbee8a138eb0f4e37016cdf142248e3c3
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93211087"
---
# <span data-ttu-id="4e54c-103">Publish-Script</span><span class="sxs-lookup"><span data-stu-id="4e54c-103">Publish-Script</span></span>

## <span data-ttu-id="4e54c-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="4e54c-104">SYNOPSIS</span></span>
<span data-ttu-id="4e54c-105">Veröffentlicht ein Skript.</span><span class="sxs-lookup"><span data-stu-id="4e54c-105">Publishes a script.</span></span>

## <span data-ttu-id="4e54c-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4e54c-106">SYNTAX</span></span>

### <span data-ttu-id="4e54c-107">Pathparameterset (Standard)</span><span class="sxs-lookup"><span data-stu-id="4e54c-107">PathParameterSet (Default)</span></span>

```
Publish-Script -Path <String> [-NuGetApiKey <String>] [-Repository <String>]
 [-Credential <PSCredential>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="4e54c-108">Literalpathparameterset</span><span class="sxs-lookup"><span data-stu-id="4e54c-108">LiteralPathParameterSet</span></span>

```
Publish-Script -LiteralPath <String> [-NuGetApiKey <String>] [-Repository <String>]
 [-Credential <PSCredential>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="4e54c-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="4e54c-109">DESCRIPTION</span></span>

<span data-ttu-id="4e54c-110">`Publish-Script`Mit dem-Cmdlet wird das angegebene Skript im Onlinekatalog veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="4e54c-110">The `Publish-Script` cmdlet publishes the specified script to the online gallery.</span></span>

## <span data-ttu-id="4e54c-111">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="4e54c-111">EXAMPLES</span></span>

### <span data-ttu-id="4e54c-112">Beispiel 1: Erstellen einer Skriptdatei, Hinzufügen von Inhalt zu dieser und veröffentlichen</span><span class="sxs-lookup"><span data-stu-id="4e54c-112">Example 1: Create a script file, add content to it, and publish it</span></span>

<span data-ttu-id="4e54c-113">Das- `New-ScriptFileInfo` Cmdlet erstellt eine Skriptdatei mit dem Namen `Demo-Script.ps1` .</span><span class="sxs-lookup"><span data-stu-id="4e54c-113">The `New-ScriptFileInfo` cmdlet creates a script file named `Demo-Script.ps1`.</span></span> <span data-ttu-id="4e54c-114">`Get-Content` zeigt den Inhalt von an `Demo-Script.ps1` .</span><span class="sxs-lookup"><span data-stu-id="4e54c-114">`Get-Content` displays the content of `Demo-Script.ps1`.</span></span> <span data-ttu-id="4e54c-115">`Add-Content`Mit dem-Cmdlet werden eine Funktion und ein Workflow zu hinzugefügt `Demo-Script.ps1` .</span><span class="sxs-lookup"><span data-stu-id="4e54c-115">The `Add-Content` cmdlet adds a function and a workflow to `Demo-Script.ps1`.</span></span>

```powershell
$newScriptInfo = @{
  Path = 'D:\ScriptSharingDemo\Demo-Script.ps1'
  Version = '1.0'
  Author = 'author@contoso.com'
  Description = "my test script file description goes here"
}
New-ScriptFileInfo @newScriptInfo
Get-Content -Path $newScriptInfo.Path
```

```Output
<#PSScriptInfo

.VERSION 1.0

.AUTHOR pattif@microsoft.com

.COMPANYNAME

.COPYRIGHT

.TAGS

.LICENSEURI

.PROJECTURI

.ICONURI

.EXTERNALMODULEDEPENDENCIES

.REQUIREDSCRIPTS

.EXTERNALSCRIPTDEPENDENCIES

.RELEASENOTES
#>

<#
.DESCRIPTION
 my test script file description goes here
#>
Param()
```

```powershell
Add-Content -Path D:\ScriptSharingDemo\Demo-Script.ps1 -Value @"

Function Demo-ScriptFunction { 'Demo-ScriptFunction' }

Workflow Demo-ScriptWorkflow { 'Demo-ScriptWorkflow' }

Demo-ScriptFunction
Demo-ScriptWorkflow
"@
Test-ScriptFileInfo -Path D:\ScriptSharingDemo\Demo-Script.ps1
```

```Output
Version    Name                 Author                   Description
-------    ----                 ------                   -----------
1.0        Demo-Script          author@contoso.com       my test script file description goes here
```

```powershell
Publish-Script -Path D:\ScriptSharingDemo\Demo-Script.ps1 -Repository LocalRepo1
Find-Script -Repository LocalRepo1 -Name "Demo-Script"
```

```Output
Version    Name                 Type       Repository    Description
-------    ----                 ----       ----------    -----------
1.0        Demo-Script          Script     LocalRepo1    my test script file description goes here
```

<span data-ttu-id="4e54c-116">Das- `Test-ScriptFileInfo` Cmdlet überprüft `Demo-Script.ps1` .</span><span class="sxs-lookup"><span data-stu-id="4e54c-116">The `Test-ScriptFileInfo` cmdlet validates `Demo-Script.ps1`.</span></span> <span data-ttu-id="4e54c-117">Das- `Publish-Script` Cmdlet veröffentlicht das Skript im **LocalRepo1** -Repository.</span><span class="sxs-lookup"><span data-stu-id="4e54c-117">The `Publish-Script` cmdlet publishes the script to the **LocalRepo1** repository.</span></span> <span data-ttu-id="4e54c-118">Die letzte Collection</span><span class="sxs-lookup"><span data-stu-id="4e54c-118">Finally.</span></span> <span data-ttu-id="4e54c-119">`Find-Script` wird verwendet, um `Demo-Script.ps1` im **LocalRepo1** -Repository nach zu suchen.</span><span class="sxs-lookup"><span data-stu-id="4e54c-119">`Find-Script` is used to search for `Demo-Script.ps1` in the **LocalRepo1** repository.</span></span>

## <span data-ttu-id="4e54c-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4e54c-120">PARAMETERS</span></span>

### <span data-ttu-id="4e54c-121">-Confirm</span><span class="sxs-lookup"><span data-stu-id="4e54c-121">-Confirm</span></span>

<span data-ttu-id="4e54c-122">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="4e54c-122">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4e54c-123">-Credential</span><span class="sxs-lookup"><span data-stu-id="4e54c-123">-Credential</span></span>

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

### <span data-ttu-id="4e54c-124">-Force</span><span class="sxs-lookup"><span data-stu-id="4e54c-124">-Force</span></span>

<span data-ttu-id="4e54c-125">Erzwingt die Ausführung des Befehls ohne Aufforderung zur Bestätigung durch den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="4e54c-125">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="4e54c-126">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="4e54c-126">-LiteralPath</span></span>

<span data-ttu-id="4e54c-127">Gibt einen Pfad zu einem oder mehreren Speicherorten an.</span><span class="sxs-lookup"><span data-stu-id="4e54c-127">Specifies a path to one or more locations.</span></span> <span data-ttu-id="4e54c-128">Im Gegensatz zum **path** -Parameter wird der Wert des **literalpath** -Parameters genau so verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="4e54c-128">Unlike the **Path** parameter, the value of the **LiteralPath** parameter is used exactly as entered.</span></span> <span data-ttu-id="4e54c-129">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="4e54c-129">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="4e54c-130">Wenn der Pfad Escapezeichen enthält, schließen Sie Sie in einfache Anführungszeichen ein.</span><span class="sxs-lookup"><span data-stu-id="4e54c-130">If the path includes escape characters, enclose them in single quotation marks.</span></span> <span data-ttu-id="4e54c-131">Einfache Anführungszeichen veranlassen Windows PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="4e54c-131">Single quotation marks tell Windows PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String
Parameter Sets: LiteralPathParameterSet
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="4e54c-132">-Nugetapikey</span><span class="sxs-lookup"><span data-stu-id="4e54c-132">-NuGetApiKey</span></span>

<span data-ttu-id="4e54c-133">Gibt den API-Schlüssel an, den Sie zum Veröffentlichen eines Skripts im Onlinekatalog verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="4e54c-133">Specifies the API key that you want to use to publish a script to the online gallery.</span></span> <span data-ttu-id="4e54c-134">Der API-Schlüssel ist Teil Ihres Profils im Onlinekatalog.</span><span class="sxs-lookup"><span data-stu-id="4e54c-134">The API key is part of your profile in the online gallery.</span></span> <span data-ttu-id="4e54c-135">Weitere Informationen finden Sie unter [Verwalten von API-Schlüsseln](/powershell/scripting/gallery/how-to/managing-profile/creating-apikeys).</span><span class="sxs-lookup"><span data-stu-id="4e54c-135">For more information see [Managing API keys](/powershell/scripting/gallery/how-to/managing-profile/creating-apikeys).</span></span>

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

### <span data-ttu-id="4e54c-136">-Path</span><span class="sxs-lookup"><span data-stu-id="4e54c-136">-Path</span></span>

<span data-ttu-id="4e54c-137">Gibt einen Pfad zu einem oder mehreren Speicherorten an.</span><span class="sxs-lookup"><span data-stu-id="4e54c-137">Specifies a path to one or more locations.</span></span> <span data-ttu-id="4e54c-138">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="4e54c-138">Wildcards are permitted.</span></span> <span data-ttu-id="4e54c-139">Der Standardspeicherort ist das aktuelle Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="4e54c-139">The default location is the current directory.</span></span>

```yaml
Type: System.String
Parameter Sets: PathParameterSet
Aliases:

Required: True
Position: Named
Default value: <Current location>
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="4e54c-140">-Repository</span><span class="sxs-lookup"><span data-stu-id="4e54c-140">-Repository</span></span>

<span data-ttu-id="4e54c-141">Gibt den anzeigen Amen eines Repository an, das durch Ausführen von registriert wurde `Register-PSRepository` .</span><span class="sxs-lookup"><span data-stu-id="4e54c-141">Specifies the friendly name of a repository that has been registered by running `Register-PSRepository`.</span></span>

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

### <span data-ttu-id="4e54c-142">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="4e54c-142">-WhatIf</span></span>

<span data-ttu-id="4e54c-143">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="4e54c-143">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="4e54c-144">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="4e54c-144">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4e54c-145">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="4e54c-145">CommonParameters</span></span>

<span data-ttu-id="4e54c-146">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="4e54c-146">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="4e54c-147">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="4e54c-147">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="4e54c-148">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="4e54c-148">INPUTS</span></span>

### <span data-ttu-id="4e54c-149">System.String</span><span class="sxs-lookup"><span data-stu-id="4e54c-149">System.String</span></span>

### <span data-ttu-id="4e54c-150">System. Management. Automation. PSCredential</span><span class="sxs-lookup"><span data-stu-id="4e54c-150">System.Management.Automation.PSCredential</span></span>

## <span data-ttu-id="4e54c-151">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="4e54c-151">OUTPUTS</span></span>

### <span data-ttu-id="4e54c-152">System.Object</span><span class="sxs-lookup"><span data-stu-id="4e54c-152">System.Object</span></span>

## <span data-ttu-id="4e54c-153">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="4e54c-153">NOTES</span></span>

## <span data-ttu-id="4e54c-154">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="4e54c-154">RELATED LINKS</span></span>

[<span data-ttu-id="4e54c-155">Find-Script</span><span class="sxs-lookup"><span data-stu-id="4e54c-155">Find-Script</span></span>](Find-Script.md)

[<span data-ttu-id="4e54c-156">Install-Script</span><span class="sxs-lookup"><span data-stu-id="4e54c-156">Install-Script</span></span>](Install-Script.md)

[<span data-ttu-id="4e54c-157">Publish-Script</span><span class="sxs-lookup"><span data-stu-id="4e54c-157">Publish-Script</span></span>](Publish-Script.md)

[<span data-ttu-id="4e54c-158">Save-Script</span><span class="sxs-lookup"><span data-stu-id="4e54c-158">Save-Script</span></span>](Save-Script.md)

[<span data-ttu-id="4e54c-159">Update-Script</span><span class="sxs-lookup"><span data-stu-id="4e54c-159">Update-Script</span></span>](Update-Script.md)