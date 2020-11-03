---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PackageManagement
ms.date: 04/03/2019
online version: https://docs.microsoft.com/powershell/module/packagemanagement/set-packagesource?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-PackageSource
ms.openlocfilehash: a8dc659d3ffdfcd296660f64f7b7cbd0bb132217
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213271"
---
# <span data-ttu-id="7f4f2-103">Set-PackageSource</span><span class="sxs-lookup"><span data-stu-id="7f4f2-103">Set-PackageSource</span></span>

## <span data-ttu-id="7f4f2-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="7f4f2-104">SYNOPSIS</span></span>
<span data-ttu-id="7f4f2-105">Ersetzt eine Paketquelle für einen angegebenen Paketanbieter.</span><span class="sxs-lookup"><span data-stu-id="7f4f2-105">Replaces a package source for a specified package provider.</span></span>

## <span data-ttu-id="7f4f2-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="7f4f2-106">SYNTAX</span></span>

### <span data-ttu-id="7f4f2-107">Sourcebysearch (Standard)</span><span class="sxs-lookup"><span data-stu-id="7f4f2-107">SourceBySearch (Default)</span></span>

```
Set-PackageSource [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-Credential <PSCredential>]
 [[-Name] <String>] [-Location <String>] [-NewLocation <String>] [-NewName <String>] [-Trusted]
 [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-ProviderName <String>] [<CommonParameters>]
```

### <span data-ttu-id="7f4f2-108">Sourcebyinputobject</span><span class="sxs-lookup"><span data-stu-id="7f4f2-108">SourceByInputObject</span></span>

```
Set-PackageSource [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-Credential <PSCredential>]
 [-NewLocation <String>] [-NewName <String>] [-Trusted] -InputObject <PackageSource> [-Force]
 [-ForceBootstrap] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="7f4f2-109">Nuget: sourcebyinputobject</span><span class="sxs-lookup"><span data-stu-id="7f4f2-109">NuGet:SourceByInputObject</span></span>

```
Set-PackageSource [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-Credential <PSCredential>]
 [-NewLocation <String>] [-NewName <String>] [-Trusted] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-ConfigFile <String>] [-SkipValidate] [<CommonParameters>]
```

### <span data-ttu-id="7f4f2-110">Nuget: sourcebysearch</span><span class="sxs-lookup"><span data-stu-id="7f4f2-110">NuGet:SourceBySearch</span></span>

```
Set-PackageSource [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-Credential <PSCredential>]
 [-NewLocation <String>] [-NewName <String>] [-Trusted] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-ConfigFile <String>] [-SkipValidate] [<CommonParameters>]
```

### <span data-ttu-id="7f4f2-111">PowerShellGet: sourcebyinputobject</span><span class="sxs-lookup"><span data-stu-id="7f4f2-111">PowerShellGet:SourceByInputObject</span></span>

```
Set-PackageSource [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-Credential <PSCredential>]
 [-NewLocation <String>] [-NewName <String>] [-Trusted] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-PackageManagementProvider <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>] [<CommonParameters>]
```

### <span data-ttu-id="7f4f2-112">PowerShellGet: sourcebysearch</span><span class="sxs-lookup"><span data-stu-id="7f4f2-112">PowerShellGet:SourceBySearch</span></span>

```
Set-PackageSource [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-Credential <PSCredential>]
 [-NewLocation <String>] [-NewName <String>] [-Trusted] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-PackageManagementProvider <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>] [<CommonParameters>]
```

## <span data-ttu-id="7f4f2-113">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7f4f2-113">DESCRIPTION</span></span>

<span data-ttu-id="7f4f2-114">`Set-PackageSource`Ersetzt eine Paketquelle für einen angegebenen Paketanbieter.</span><span class="sxs-lookup"><span data-stu-id="7f4f2-114">The `Set-PackageSource` replaces a package source for a specified package provider.</span></span> <span data-ttu-id="7f4f2-115">Paketquellen werden immer von einem Paketanbieter verwaltet.</span><span class="sxs-lookup"><span data-stu-id="7f4f2-115">Package sources are always managed by a package provider.</span></span>

## <span data-ttu-id="7f4f2-116">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="7f4f2-116">EXAMPLES</span></span>

### <span data-ttu-id="7f4f2-117">Beispiel 1: Ändern einer Paketquelle</span><span class="sxs-lookup"><span data-stu-id="7f4f2-117">Example 1: Change a package source</span></span>

<span data-ttu-id="7f4f2-118">Mit diesem Befehl wird der vorhandene Name einer Paketquelle geändert.</span><span class="sxs-lookup"><span data-stu-id="7f4f2-118">This command changes the existing name of a package source.</span></span> <span data-ttu-id="7f4f2-119">Die Quelle ist auf " **vertrauenswürdig** " festgelegt. Dadurch werden Aufforderungen zum Überprüfen der Quelle beim Installieren von Paketen beseitigt.</span><span class="sxs-lookup"><span data-stu-id="7f4f2-119">The source is set to **Trusted** , which eliminates prompts to verify the source when packages are installed.</span></span>

```
PS C:\> Set-PackageSource -Name MyNuget -NewName NewNuGet -Trusted -ProviderName NuGet
```

## <span data-ttu-id="7f4f2-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="7f4f2-120">PARAMETERS</span></span>

### <span data-ttu-id="7f4f2-121">-Configfile</span><span class="sxs-lookup"><span data-stu-id="7f4f2-121">-ConfigFile</span></span>

<span data-ttu-id="7f4f2-122">Gibt eine Konfigurationsdatei an.</span><span class="sxs-lookup"><span data-stu-id="7f4f2-122">Specifies a configuration file.</span></span>

```yaml
Type: System.String
Parameter Sets: NuGet:SourceByInputObject, NuGet:SourceBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7f4f2-123">-Credential</span><span class="sxs-lookup"><span data-stu-id="7f4f2-123">-Credential</span></span>

<span data-ttu-id="7f4f2-124">Gibt ein Benutzerkonto an, das über die Berechtigung zum Installieren von Paket Anbietern verfügt.</span><span class="sxs-lookup"><span data-stu-id="7f4f2-124">Specifies a user account that has permission to install package providers.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7f4f2-125">-Force</span><span class="sxs-lookup"><span data-stu-id="7f4f2-125">-Force</span></span>

<span data-ttu-id="7f4f2-126">Erzwingt die Ausführung des Befehls ohne Aufforderung zur Bestätigung durch den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="7f4f2-126">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="7f4f2-127">-Forcebootstrap</span><span class="sxs-lookup"><span data-stu-id="7f4f2-127">-ForceBootstrap</span></span>

<span data-ttu-id="7f4f2-128">Gibt an, dass `Set-PackageSource` **packagemanagement** zwingt, den Paketanbieter automatisch zu installieren.</span><span class="sxs-lookup"><span data-stu-id="7f4f2-128">Indicates that `Set-PackageSource` forces **PackageManagement** to automatically install the package provider.</span></span>

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

### <span data-ttu-id="7f4f2-129">-InputObject</span><span class="sxs-lookup"><span data-stu-id="7f4f2-129">-InputObject</span></span>

<span data-ttu-id="7f4f2-130">Gibt ein Paketquellen-ID-Objekt an, das das zu ändernde Paket darstellt.</span><span class="sxs-lookup"><span data-stu-id="7f4f2-130">Specifies a package source ID object that represents the package that you want to change.</span></span> <span data-ttu-id="7f4f2-131">Paket Quell-IDs sind Teil der Ergebnisse des `Get-PackageSource` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="7f4f2-131">Package source IDs are part of the results of the `Get-PackageSource` cmdlet.</span></span>

```yaml
Type: Microsoft.PackageManagement.Packaging.PackageSource
Parameter Sets: SourceByInputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="7f4f2-132">-Location</span><span class="sxs-lookup"><span data-stu-id="7f4f2-132">-Location</span></span>

<span data-ttu-id="7f4f2-133">Gibt den Quell Speicherort des aktuellen Pakets an.</span><span class="sxs-lookup"><span data-stu-id="7f4f2-133">Specifies the current package source location.</span></span> <span data-ttu-id="7f4f2-134">Der Wert kann ein URI, ein Dateipfad oder ein beliebiges anderes Zielformat sein, das vom Paketanbieter unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="7f4f2-134">The value can be a URI, a file path, or any other destination format supported by the package provider.</span></span>

```yaml
Type: System.String
Parameter Sets: SourceBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7f4f2-135">-Name</span><span class="sxs-lookup"><span data-stu-id="7f4f2-135">-Name</span></span>

<span data-ttu-id="7f4f2-136">Gibt den Namen einer Paketquelle an.</span><span class="sxs-lookup"><span data-stu-id="7f4f2-136">Specifies a package source's name.</span></span>

```yaml
Type: System.String
Parameter Sets: SourceBySearch
Aliases: SourceName

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7f4f2-137">-NewLocation</span><span class="sxs-lookup"><span data-stu-id="7f4f2-137">-NewLocation</span></span>

<span data-ttu-id="7f4f2-138">Gibt den neuen Speicherort für eine Paketquelle an.</span><span class="sxs-lookup"><span data-stu-id="7f4f2-138">Specifies the new location for a package source.</span></span> <span data-ttu-id="7f4f2-139">Der Wert kann ein URI, ein Dateipfad oder ein beliebiges anderes Zielformat sein, das vom Paketanbieter unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="7f4f2-139">The value can be a URI, a file path, or any other destination format supported by the package provider.</span></span>

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

### <span data-ttu-id="7f4f2-140">-Newname</span><span class="sxs-lookup"><span data-stu-id="7f4f2-140">-NewName</span></span>

<span data-ttu-id="7f4f2-141">Gibt den neuen Namen an, den Sie einer Paketquelle zuweisen.</span><span class="sxs-lookup"><span data-stu-id="7f4f2-141">Specifies the new name you assign to a package source.</span></span>

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

### <span data-ttu-id="7f4f2-142">-Packagemanagementprovider</span><span class="sxs-lookup"><span data-stu-id="7f4f2-142">-PackageManagementProvider</span></span>

<span data-ttu-id="7f4f2-143">Gibt einen Paket Verwaltungs Anbieter an.</span><span class="sxs-lookup"><span data-stu-id="7f4f2-143">Specifies a package management provider.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:SourceByInputObject, PowerShellGet:SourceBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7f4f2-144">-ProviderName</span><span class="sxs-lookup"><span data-stu-id="7f4f2-144">-ProviderName</span></span>

<span data-ttu-id="7f4f2-145">Gibt einen Anbieter Namen an.</span><span class="sxs-lookup"><span data-stu-id="7f4f2-145">Specifies a provider name.</span></span>

```yaml
Type: System.String
Parameter Sets: SourceBySearch
Aliases: Provider
Accepted values: Bootstrap, NuGet, PowerShellGet

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="7f4f2-146">-Proxy</span><span class="sxs-lookup"><span data-stu-id="7f4f2-146">-Proxy</span></span>

<span data-ttu-id="7f4f2-147">Gibt einen Proxy Server für die Anforderung an, anstatt eine direkte Verbindung mit der Internet Ressource herzustellen.</span><span class="sxs-lookup"><span data-stu-id="7f4f2-147">Specifies a proxy server for the request, rather than connecting directly to the Internet resource.</span></span>

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7f4f2-148">-Proxy Credential</span><span class="sxs-lookup"><span data-stu-id="7f4f2-148">-ProxyCredential</span></span>

<span data-ttu-id="7f4f2-149">Gibt ein Benutzerkonto an, das über die Berechtigung zur Verwendung des Proxyservers verfügt, der durch den **Proxy** -Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="7f4f2-149">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7f4f2-150">-Publishlocation</span><span class="sxs-lookup"><span data-stu-id="7f4f2-150">-PublishLocation</span></span>

<span data-ttu-id="7f4f2-151">Gibt den Veröffentlichungs Speicherort an.</span><span class="sxs-lookup"><span data-stu-id="7f4f2-151">Specifies the publish location.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:SourceByInputObject, PowerShellGet:SourceBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7f4f2-152">-Scriptpublishlocation</span><span class="sxs-lookup"><span data-stu-id="7f4f2-152">-ScriptPublishLocation</span></span>

<span data-ttu-id="7f4f2-153">Gibt den Speicherort der Skript Veröffentlichung an.</span><span class="sxs-lookup"><span data-stu-id="7f4f2-153">Specifies the script publish location.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:SourceByInputObject, PowerShellGet:SourceBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7f4f2-154">-Scriptsourcelokation</span><span class="sxs-lookup"><span data-stu-id="7f4f2-154">-ScriptSourceLocation</span></span>

<span data-ttu-id="7f4f2-155">Gibt den Quell Speicherort des Skripts an.</span><span class="sxs-lookup"><span data-stu-id="7f4f2-155">Specifies the script source location.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:SourceByInputObject, PowerShellGet:SourceBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7f4f2-156">-Skipvalidate</span><span class="sxs-lookup"><span data-stu-id="7f4f2-156">-SkipValidate</span></span>

<span data-ttu-id="7f4f2-157">Ein Schalter, der die Validierung der Anmelde Informationen einer Paketquelle überspringt.</span><span class="sxs-lookup"><span data-stu-id="7f4f2-157">Switch that skips validating the credentials of a package source.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NuGet:SourceByInputObject, NuGet:SourceBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7f4f2-158">-Vertrauenswürdig</span><span class="sxs-lookup"><span data-stu-id="7f4f2-158">-Trusted</span></span>

<span data-ttu-id="7f4f2-159">Gibt an, dass die Quelle ein vertrauenswürdiger Paketanbieter ist.</span><span class="sxs-lookup"><span data-stu-id="7f4f2-159">Indicates that the source is a trusted package provider.</span></span> <span data-ttu-id="7f4f2-160">Vertrauenswürdige Quellen werden nicht zur Überprüfung aufgefordert, um Pakete zu installieren.</span><span class="sxs-lookup"><span data-stu-id="7f4f2-160">Trusted sources don't prompt for verification to install packages.</span></span>

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

### <span data-ttu-id="7f4f2-161">-Confirm</span><span class="sxs-lookup"><span data-stu-id="7f4f2-161">-Confirm</span></span>

<span data-ttu-id="7f4f2-162">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="7f4f2-162">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="7f4f2-163">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="7f4f2-163">-WhatIf</span></span>

<span data-ttu-id="7f4f2-164">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="7f4f2-164">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="7f4f2-165">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="7f4f2-165">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="7f4f2-166">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="7f4f2-166">CommonParameters</span></span>

<span data-ttu-id="7f4f2-167">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="7f4f2-167">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="7f4f2-168">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="7f4f2-168">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="7f4f2-169">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="7f4f2-169">INPUTS</span></span>

### <span data-ttu-id="7f4f2-170">`Set-PackageSource` akzeptiert keine Pipeline Eingaben.</span><span class="sxs-lookup"><span data-stu-id="7f4f2-170">`Set-PackageSource` doesn't accept pipeline input.</span></span>

## <span data-ttu-id="7f4f2-171">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="7f4f2-171">OUTPUTS</span></span>

### <span data-ttu-id="7f4f2-172">Dieses Cmdlet generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="7f4f2-172">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="7f4f2-173">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="7f4f2-173">NOTES</span></span>

## <span data-ttu-id="7f4f2-174">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="7f4f2-174">RELATED LINKS</span></span>

[<span data-ttu-id="7f4f2-175">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="7f4f2-175">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="7f4f2-176">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="7f4f2-176">Get-PackageSource</span></span>](Get-PackageSource.md)

[<span data-ttu-id="7f4f2-177">Register-PackageSource</span><span class="sxs-lookup"><span data-stu-id="7f4f2-177">Register-PackageSource</span></span>](Register-PackageSource.md)

[<span data-ttu-id="7f4f2-178">Unregister-PackageSource</span><span class="sxs-lookup"><span data-stu-id="7f4f2-178">Unregister-PackageSource</span></span>](Unregister-PackageSource.md)