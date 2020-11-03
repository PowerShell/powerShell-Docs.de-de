---
external help file: PSDesiredStateConfiguration-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 07/23/2020
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/get-dscresource?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DscResource
ms.openlocfilehash: 4a46e3b78ae9db4ea58f97daf37dca399c925549
ms.sourcegitcommit: 9dddf1d2e91ebcd347fcfb7bf6ef670d49a12ab7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2020
ms.locfileid: "93218927"
---
# <span data-ttu-id="9a6e6-103">Get-DscResource</span><span class="sxs-lookup"><span data-stu-id="9a6e6-103">Get-DscResource</span></span>

## <span data-ttu-id="9a6e6-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="9a6e6-104">SYNOPSIS</span></span>
<span data-ttu-id="9a6e6-105">Ruft DSC-Ressourcen auf dem Computer ab.</span><span class="sxs-lookup"><span data-stu-id="9a6e6-105">Gets Desired State Configuration (DSC) resources present on the computer.</span></span>

## <span data-ttu-id="9a6e6-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9a6e6-106">SYNTAX</span></span>

```
Get-DscResource [[-Name] <String[]>] [[-Module] <Object>] [-Syntax] [<CommonParameters>]
```

## <span data-ttu-id="9a6e6-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9a6e6-107">DESCRIPTION</span></span>

<span data-ttu-id="9a6e6-108">Mit dem- `Get-DscResource` Cmdlet werden die auf dem Computer vorhandenen PowerShell DSC-Ressourcen abgerufen.</span><span class="sxs-lookup"><span data-stu-id="9a6e6-108">The `Get-DscResource` cmdlet retrieves the PowerShell DSC resources present on the computer.</span></span> <span data-ttu-id="9a6e6-109">Dieses Cmdlet ermittelt nur die Ressourcen, die in psmodulepath installiert sind.</span><span class="sxs-lookup"><span data-stu-id="9a6e6-109">This cmdlet discovers only the resources installed in the PSModulePath.</span></span> <span data-ttu-id="9a6e6-110">Es zeigt die Details über integrierte und benutzerdefinierte Anbieter, die vom Benutzer erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="9a6e6-110">It shows the details about built-in and custom providers, which are created by the user.</span></span> <span data-ttu-id="9a6e6-111">Dieses Cmdlet zeigt auch Details zu zusammengesetzten Ressourcen an, bei denen es sich um andere Konfigurationen handelt, die als Modul verpackt oder zur Laufzeit in der Sitzung erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="9a6e6-111">This cmdlet also shows details about composite resources, which are other configurations that are packaged as module or created at run time in the session.</span></span>

## <span data-ttu-id="9a6e6-112">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="9a6e6-112">EXAMPLES</span></span>

### <span data-ttu-id="9a6e6-113">Beispiel 1: alle Ressourcen auf dem lokalen Computer</span><span class="sxs-lookup"><span data-stu-id="9a6e6-113">Example 1: Get all resources on the local computer</span></span>

```powershell
Get-DscResource
```

<span data-ttu-id="9a6e6-114">Dieser Befehl ruft alle Ressourcen auf dem lokalen Computer ab.</span><span class="sxs-lookup"><span data-stu-id="9a6e6-114">This command gets all the resources on the local computer.</span></span>

### <span data-ttu-id="9a6e6-115">Beispiel 2: erhalten einer Ressource durch Angabe des Namens</span><span class="sxs-lookup"><span data-stu-id="9a6e6-115">Example 2: Get a resource by specifying the name</span></span>

```powershell
Get-DscResource -Name "WindowsFeature"
```

<span data-ttu-id="9a6e6-116">Dieser Befehl ruft die WindowsFeature-Ressource ab.</span><span class="sxs-lookup"><span data-stu-id="9a6e6-116">This command gets the WindowsFeature resource.</span></span>

### <span data-ttu-id="9a6e6-117">Beispiel 3: alle Ressourcen eines Moduls</span><span class="sxs-lookup"><span data-stu-id="9a6e6-117">Example 3: Get all the resources from a module</span></span>

```powershell
Get-DscResource -Module "xHyper-V"
```

<span data-ttu-id="9a6e6-118">Mit diesem Befehl werden alle Ressourcen aus dem xhyper-V-Modul abgerufen.</span><span class="sxs-lookup"><span data-stu-id="9a6e6-118">This command gets all the resources from the xHyper-V module.</span></span>

### <span data-ttu-id="9a6e6-119">Beispiel 4: erhalten einer Ressource mithilfe von Platzhalter Zeichen</span><span class="sxs-lookup"><span data-stu-id="9a6e6-119">Example 4: Get a resource by using wildcard characters</span></span>

```powershell
Get-DscResource -Name P*,r*
```

<span data-ttu-id="9a6e6-120">Mit diesem Befehl werden alle Ressourcen abgerufen, die dem durch den **Name** -Parameter angegebenen Platzhalter Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="9a6e6-120">This command gets all resources that match the wildcard pattern specified by the **Name** parameter.</span></span>

### <span data-ttu-id="9a6e6-121">Beispiel 5: erhalten einer Ressourcen Syntax</span><span class="sxs-lookup"><span data-stu-id="9a6e6-121">Example 5: Get a resource syntax</span></span>

```powershell
Get-DscResource -Name "WindowsFeature" -Syntax
```

<span data-ttu-id="9a6e6-122">Dieser Befehl ruft die WindowsFeature-Ressource ab und zeigt die Syntax für die Ressource.</span><span class="sxs-lookup"><span data-stu-id="9a6e6-122">This command gets the WindowsFeature resource, and shows the syntax for the resource.</span></span>

### <span data-ttu-id="9a6e6-123">Beispiel 6: alle Eigenschaften für eine Ressource</span><span class="sxs-lookup"><span data-stu-id="9a6e6-123">Example 6: Get all the properties for a resource</span></span>

```powershell
Get-DscResource -Name "User" | Select-Object -ExpandProperty Properties
```

<span data-ttu-id="9a6e6-124">Dieser Befehl ruft die User-Ressource ab und verwendet dann den Pipeline-Operator, um alle Eigenschaften für die User-Ressource zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="9a6e6-124">This command gets the User resource, and then uses the pipeline operator to return all the properties for the User resource.</span></span>

### <span data-ttu-id="9a6e6-125">Beispiel 7: alle Ressourcen aus einem angegebenen Modul mit einer bestimmten Version</span><span class="sxs-lookup"><span data-stu-id="9a6e6-125">Example 7: Get all the resources from a specified module with a specified version</span></span>

```powershell
Get-DscResource -Module @{ModuleName='xHyper-V';RequiredVersion='3.0.0.0'}
```

<span data-ttu-id="9a6e6-126">Mit diesem Befehl werden alle Ressourcen aus dem xhyper-V-Modul mit der Version 3.0.0.0 abgerufen.</span><span class="sxs-lookup"><span data-stu-id="9a6e6-126">This command gets all the resources from xHyper-V module with version 3.0.0.0.</span></span>

## <span data-ttu-id="9a6e6-127">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9a6e6-127">PARAMETERS</span></span>

### <span data-ttu-id="9a6e6-128">-Modul</span><span class="sxs-lookup"><span data-stu-id="9a6e6-128">-Module</span></span>

<span data-ttu-id="9a6e6-129">Gibt den Namen oder den voll qualifizierten Namen des Moduls an, für das die DSC-Ressource angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="9a6e6-129">Specifies the name or fully qualified name of the module for which to view the DSC resource.</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="9a6e6-130">-Name</span><span class="sxs-lookup"><span data-stu-id="9a6e6-130">-Name</span></span>

<span data-ttu-id="9a6e6-131">Gibt ein Array von Namen der DSC-Ressource an, die angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="9a6e6-131">Specifies an array of names of the DSC resource to view.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="9a6e6-132">-Syntax</span><span class="sxs-lookup"><span data-stu-id="9a6e6-132">-Syntax</span></span>

<span data-ttu-id="9a6e6-133">Gibt an, dass das Cmdlet die Syntax Ansicht der angegebenen DSC-Ressourcen zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="9a6e6-133">Indicates that the cmdlet returns the syntax view of the specified DSC resources.</span></span> <span data-ttu-id="9a6e6-134">Die zurückgegebene Syntax zeigt, wie die Ressourcen in einem PowerShell-Skript verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9a6e6-134">The returned syntax shows how to use the resources in a PowerShell script.</span></span>

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

### <span data-ttu-id="9a6e6-135">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="9a6e6-135">CommonParameters</span></span>

<span data-ttu-id="9a6e6-136">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="9a6e6-136">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="9a6e6-137">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="9a6e6-137">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="9a6e6-138">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="9a6e6-138">INPUTS</span></span>

### <span data-ttu-id="9a6e6-139">System.String[]</span><span class="sxs-lookup"><span data-stu-id="9a6e6-139">System.String[]</span></span>

### <span data-ttu-id="9a6e6-140">System.Object</span><span class="sxs-lookup"><span data-stu-id="9a6e6-140">System.Object</span></span>

## <span data-ttu-id="9a6e6-141">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="9a6e6-141">OUTPUTS</span></span>

### <span data-ttu-id="9a6e6-142">Microsoft. PowerShell. desiredStatus econfiguration. dscresourceinfo []</span><span class="sxs-lookup"><span data-stu-id="9a6e6-142">Microsoft.PowerShell.DesiredStateConfiguration.DscResourceInfo[]</span></span>

### <span data-ttu-id="9a6e6-143">string[]</span><span class="sxs-lookup"><span data-stu-id="9a6e6-143">string[]</span></span>

## <span data-ttu-id="9a6e6-144">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="9a6e6-144">NOTES</span></span>

- <span data-ttu-id="9a6e6-145">`Get-DscResource` in PowerShell-Versionen unter 7,0 finden Sie keine klassenbasierten DSC-Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="9a6e6-145">`Get-DscResource` does not find Class based DSC resources in PowerShell versions below 7.0.</span></span>

## <span data-ttu-id="9a6e6-146">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="9a6e6-146">RELATED LINKS</span></span>

[<span data-ttu-id="9a6e6-147">PowerShell-Konfiguration des gewünschten Zustands (Übersicht)</span><span class="sxs-lookup"><span data-stu-id="9a6e6-147">PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/overview)

[<span data-ttu-id="9a6e6-148">Invoke-DscResource</span><span class="sxs-lookup"><span data-stu-id="9a6e6-148">Invoke-DscResource</span></span>](Invoke-DscResource.md)