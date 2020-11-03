---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PackageManagement
ms.date: 03/29/2019
online version: https://docs.microsoft.com/powershell/module/packagemanagement/get-packagesource?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PackageSource
ms.openlocfilehash: 81b6f94be6293733ec75d48b1f9dd7ac4f4f8d96
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212863"
---
# <span data-ttu-id="c5669-103">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="c5669-103">Get-PackageSource</span></span>

## <span data-ttu-id="c5669-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="c5669-104">SYNOPSIS</span></span>
<span data-ttu-id="c5669-105">Ruft eine Liste der Paketquellen ab, die für einen Paketanbieter registriert sind.</span><span class="sxs-lookup"><span data-stu-id="c5669-105">Gets a list of package sources that are registered for a package provider.</span></span>

## <span data-ttu-id="c5669-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c5669-106">SYNTAX</span></span>

### <span data-ttu-id="c5669-107">NuGet</span><span class="sxs-lookup"><span data-stu-id="c5669-107">NuGet</span></span>

```
Get-PackageSource [[-Name] <String>] [-Location <String>] [-Force] [-ForceBootstrap]
 [-ProviderName <String[]>] [-ConfigFile <String>] [-SkipValidate] [<CommonParameters>]
```

### <span data-ttu-id="c5669-108">PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="c5669-108">PowerShellGet</span></span>

```
Get-PackageSource [[-Name] <String>] [-Location <String>] [-Force] [-ForceBootstrap]
 [-ProviderName <String[]>] [-PackageManagementProvider <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>] [<CommonParameters>]
```

## <span data-ttu-id="c5669-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="c5669-109">DESCRIPTION</span></span>

<span data-ttu-id="c5669-110">Mit dem- `Get-PackageSource` Cmdlet wird eine Liste der Paketquellen abgerufen, die bei **packagemanagement** auf dem lokalen Computer registriert sind.</span><span class="sxs-lookup"><span data-stu-id="c5669-110">The `Get-PackageSource` cmdlet gets a list of package sources that are registered with **PackageManagement** on the local computer.</span></span> <span data-ttu-id="c5669-111">Wenn Sie einen Paketanbieter angeben, werden `Get-PackageSource` von nur die Quellen abgerufen, die dem angegebenen Anbieter zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="c5669-111">If you specify a package provider, `Get-PackageSource` gets only those sources that are associated with the specified provider.</span></span> <span data-ttu-id="c5669-112">Andernfalls gibt der Befehl alle Paketquellen zurück, die bei **packagemanagement** registriert sind.</span><span class="sxs-lookup"><span data-stu-id="c5669-112">Otherwise, the command returns all package sources that are registered with **PackageManagement** .</span></span>

## <span data-ttu-id="c5669-113">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="c5669-113">EXAMPLES</span></span>

### <span data-ttu-id="c5669-114">Beispiel 1: alle Paketquellen erhalten</span><span class="sxs-lookup"><span data-stu-id="c5669-114">Example 1: Get all package sources</span></span>

<span data-ttu-id="c5669-115">Mit dem- `Get-PackageSource` Cmdlet werden alle Paketquellen abgerufen, die bei **packagemanagement** auf dem lokalen Computer registriert sind.</span><span class="sxs-lookup"><span data-stu-id="c5669-115">The `Get-PackageSource` cmdlet gets all package sources that are registered with **PackageManagement** on the local computer.</span></span>

```powershell
Get-PackageSource
```

```Output
Name                 ProviderName     IsTrusted  Location
----                 ------------     ---------  --------
LocalPackages        NuGet            False      C:\LocalPkg\
MyNuget              NuGet            False      https://www.nuget.org/api/v2
PSGallery            PowerShellGet    False      https://www.powershellgallery.com/api/v2
```

### <span data-ttu-id="c5669-116">Beispiel 2: alle Paketquellen für einen bestimmten Anbieter</span><span class="sxs-lookup"><span data-stu-id="c5669-116">Example 2: Get all package sources for a specific provider</span></span>

<span data-ttu-id="c5669-117">Mit diesem Befehl werden Paketquellen abgerufen, die für einen bestimmten Anbieter registriert sind.</span><span class="sxs-lookup"><span data-stu-id="c5669-117">This command gets package sources that are registered for a specific provider.</span></span>

```powershell
Get-PackageSource -ProviderName NuGet
```

```Output
Name                 ProviderName     IsTrusted  Location
----                 ------------     ---------  --------
LocalPackages        NuGet            False      C:\LocalPkg\
MyNuget              NuGet            False      https://www.nuget.org/api/v2
```

<span data-ttu-id="c5669-118">`Get-PackageSource` verwendet den **providerName** -Parameter, um Paketquellen zu erhalten, die für den **nuget** -Anbieter registriert sind.</span><span class="sxs-lookup"><span data-stu-id="c5669-118">`Get-PackageSource` uses the **ProviderName** parameter to get package sources that are registered for the **NuGet** provider.</span></span>

### <span data-ttu-id="c5669-119">Beispiel 3: Quellen von einem Paketanbieter beziehen</span><span class="sxs-lookup"><span data-stu-id="c5669-119">Example 3: Get sources from a package provider</span></span>

<span data-ttu-id="c5669-120">Dieser Befehl verwendet einen Paketanbieter, um Paketquellen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="c5669-120">This command uses a package provider to get package sources.</span></span>

```powershell
Get-PackageProvider -Name NuGet | Get-PackageSource
```

```Output
Name                 ProviderName     IsTrusted  Location
----                 ------------     ---------  --------
LocalPackages        NuGet            False      C:\LocalPkg\
MyNuget              NuGet            False      https://www.nuget.org/api/v2
```

<span data-ttu-id="c5669-121">`Get-PackageProvider` verwendet den **Name** -Parameter, um den Anbieter Namen ( **nuget** ) anzugeben.</span><span class="sxs-lookup"><span data-stu-id="c5669-121">`Get-PackageProvider` uses the **Name** parameter specify the provider name, **NuGet** .</span></span> <span data-ttu-id="c5669-122">Das Objekt wird über die Pipeline an gesendet `Get-PackageSource` .</span><span class="sxs-lookup"><span data-stu-id="c5669-122">The object is sent down the pipeline to `Get-PackageSource`.</span></span>

## <span data-ttu-id="c5669-123">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c5669-123">PARAMETERS</span></span>

### <span data-ttu-id="c5669-124">-Configfile</span><span class="sxs-lookup"><span data-stu-id="c5669-124">-ConfigFile</span></span>

<span data-ttu-id="c5669-125">Gibt eine Konfigurationsdatei an.</span><span class="sxs-lookup"><span data-stu-id="c5669-125">Specifies a configuration file.</span></span>

```yaml
Type: System.String
Parameter Sets: NuGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c5669-126">-Force</span><span class="sxs-lookup"><span data-stu-id="c5669-126">-Force</span></span>

<span data-ttu-id="c5669-127">Erzwingt die Ausführung des Befehls ohne Aufforderung zur Bestätigung durch den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="c5669-127">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="c5669-128">-Forcebootstrap</span><span class="sxs-lookup"><span data-stu-id="c5669-128">-ForceBootstrap</span></span>

<span data-ttu-id="c5669-129">Gibt an, dass mit diesem Cmdlet **packagemanagement** gezwungen wird, einen Paketanbieter automatisch zu installieren.</span><span class="sxs-lookup"><span data-stu-id="c5669-129">Indicates that this cmdlet forces **PackageManagement** to automatically install a package provider.</span></span>

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

### <span data-ttu-id="c5669-130">-Location</span><span class="sxs-lookup"><span data-stu-id="c5669-130">-Location</span></span>

<span data-ttu-id="c5669-131">Gibt den Speicherort einer Paket Verwaltungs Quelle oder eines Repository an.</span><span class="sxs-lookup"><span data-stu-id="c5669-131">Specifies the location of a package management source or repository.</span></span>

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

### <span data-ttu-id="c5669-132">-Name</span><span class="sxs-lookup"><span data-stu-id="c5669-132">-Name</span></span>

<span data-ttu-id="c5669-133">Gibt den Namen einer Paket Verwaltungs Quelle an.</span><span class="sxs-lookup"><span data-stu-id="c5669-133">Specifies the name of a package management source.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c5669-134">-Packagemanagementprovider</span><span class="sxs-lookup"><span data-stu-id="c5669-134">-PackageManagementProvider</span></span>

<span data-ttu-id="c5669-135">Gibt einen Paket Verwaltungs Anbieter an.</span><span class="sxs-lookup"><span data-stu-id="c5669-135">Specifies a package management provider.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c5669-136">-ProviderName</span><span class="sxs-lookup"><span data-stu-id="c5669-136">-ProviderName</span></span>

<span data-ttu-id="c5669-137">Gibt einen oder mehrere Paketanbieter Namen an.</span><span class="sxs-lookup"><span data-stu-id="c5669-137">Specifies one or more package provider names.</span></span> <span data-ttu-id="c5669-138">Trennen Sie mehrere Paketanbieter Namen durch Kommas.</span><span class="sxs-lookup"><span data-stu-id="c5669-138">Separate multiple package provider names with commas.</span></span>
<span data-ttu-id="c5669-139">Verwenden `Get-PackageProvider` Sie, um eine Liste der verfügbaren Paketanbieter zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="c5669-139">Use `Get-PackageProvider` to get a list of available package providers.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Provider
Accepted values: Bootstrap, NuGet, PowerShellGet

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="c5669-140">-Publishlocation</span><span class="sxs-lookup"><span data-stu-id="c5669-140">-PublishLocation</span></span>

<span data-ttu-id="c5669-141">Gibt den Veröffentlichungs Speicherort für die Paketquelle an.</span><span class="sxs-lookup"><span data-stu-id="c5669-141">Specifies the publish location for the package source.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c5669-142">-Scriptpublishlocation</span><span class="sxs-lookup"><span data-stu-id="c5669-142">-ScriptPublishLocation</span></span>

<span data-ttu-id="c5669-143">Gibt den Speicherort der Skript Veröffentlichung an.</span><span class="sxs-lookup"><span data-stu-id="c5669-143">Specifies the script publish location.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c5669-144">-Scriptsourcelokation</span><span class="sxs-lookup"><span data-stu-id="c5669-144">-ScriptSourceLocation</span></span>

<span data-ttu-id="c5669-145">Gibt den Quell Speicherort des Skripts an.</span><span class="sxs-lookup"><span data-stu-id="c5669-145">Specifies the script source location.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c5669-146">-Skipvalidate</span><span class="sxs-lookup"><span data-stu-id="c5669-146">-SkipValidate</span></span>

<span data-ttu-id="c5669-147">Ein Schalter, der die Validierung der Anmelde Informationen einer Paketquelle überspringt.</span><span class="sxs-lookup"><span data-stu-id="c5669-147">Switch that skips validating the credentials of a package source.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NuGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c5669-148">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="c5669-148">CommonParameters</span></span>

<span data-ttu-id="c5669-149">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="c5669-149">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c5669-150">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="c5669-150">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c5669-151">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="c5669-151">INPUTS</span></span>

## <span data-ttu-id="c5669-152">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="c5669-152">OUTPUTS</span></span>

### <span data-ttu-id="c5669-153">Packagesource []</span><span class="sxs-lookup"><span data-stu-id="c5669-153">PackageSource[]</span></span>

<span data-ttu-id="c5669-154">Gibt mindestens eine Paketquelle an.</span><span class="sxs-lookup"><span data-stu-id="c5669-154">Specifies one or more package sources.</span></span>

## <span data-ttu-id="c5669-155">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="c5669-155">NOTES</span></span>

## <span data-ttu-id="c5669-156">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="c5669-156">RELATED LINKS</span></span>

[<span data-ttu-id="c5669-157">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="c5669-157">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="c5669-158">Find-Package</span><span class="sxs-lookup"><span data-stu-id="c5669-158">Find-Package</span></span>](Find-Package.md)

[<span data-ttu-id="c5669-159">Get-Package</span><span class="sxs-lookup"><span data-stu-id="c5669-159">Get-Package</span></span>](Get-Package.md)

[<span data-ttu-id="c5669-160">Get-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="c5669-160">Get-PackageProvider</span></span>](Get-PackageProvider.md)

[<span data-ttu-id="c5669-161">Register-PackageSource</span><span class="sxs-lookup"><span data-stu-id="c5669-161">Register-PackageSource</span></span>](Register-PackageSource.md)

[<span data-ttu-id="c5669-162">Set-PackageSource</span><span class="sxs-lookup"><span data-stu-id="c5669-162">Set-PackageSource</span></span>](Set-PackageSource.md)

[<span data-ttu-id="c5669-163">Unregister-PackageSource</span><span class="sxs-lookup"><span data-stu-id="c5669-163">Unregister-PackageSource</span></span>](Unregister-PackageSource.md)
