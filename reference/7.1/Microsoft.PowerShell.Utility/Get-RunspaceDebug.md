---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 03/19/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-runspacedebug?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-RunspaceDebug
ms.openlocfilehash: 821b532dc44702af4243bf36ca7f5d4089a057d8
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213028"
---
# <span data-ttu-id="28909-103">Get-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="28909-103">Get-RunspaceDebug</span></span>

## <span data-ttu-id="28909-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="28909-104">SYNOPSIS</span></span>
<span data-ttu-id="28909-105">Zeigt die Runspace-Debugoptionen an.</span><span class="sxs-lookup"><span data-stu-id="28909-105">Shows runspace debugging options.</span></span>

## <span data-ttu-id="28909-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="28909-106">SYNTAX</span></span>

### <span data-ttu-id="28909-107">Runspacenameparameterset (Standard)</span><span class="sxs-lookup"><span data-stu-id="28909-107">RunspaceNameParameterSet (Default)</span></span>

```
Get-RunspaceDebug [[-RunspaceName] <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="28909-108">Runspaceparameterset</span><span class="sxs-lookup"><span data-stu-id="28909-108">RunspaceParameterSet</span></span>

```
Get-RunspaceDebug [-Runspace] <Runspace[]> [<CommonParameters>]
```

### <span data-ttu-id="28909-109">Runspaceidparameterset</span><span class="sxs-lookup"><span data-stu-id="28909-109">RunspaceIdParameterSet</span></span>

```
Get-RunspaceDebug [-RunspaceId] <Int32[]> [<CommonParameters>]
```

### <span data-ttu-id="28909-110">Runspaceinstanceidparameterset</span><span class="sxs-lookup"><span data-stu-id="28909-110">RunspaceInstanceIdParameterSet</span></span>

```
Get-RunspaceDebug [-RunspaceInstanceId] <Guid[]> [<CommonParameters>]
```

### <span data-ttu-id="28909-111">Processnameparameterset</span><span class="sxs-lookup"><span data-stu-id="28909-111">ProcessNameParameterSet</span></span>

```
Get-RunspaceDebug [[-ProcessName] <String>] [[-AppDomainName] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="28909-112">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="28909-112">DESCRIPTION</span></span>

<span data-ttu-id="28909-113">Das- `Get-RunspaceDebug` Cmdlet zeigt Runspace-Debugoptionen.</span><span class="sxs-lookup"><span data-stu-id="28909-113">The `Get-RunspaceDebug` cmdlet shows runspace debugging options.</span></span>

## <span data-ttu-id="28909-114">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="28909-114">EXAMPLES</span></span>

### <span data-ttu-id="28909-115">1: zeigt den Status des standardrunspace-Debuggers an.</span><span class="sxs-lookup"><span data-stu-id="28909-115">1: Show the state of the default runspace debugger</span></span>

```powershell
Get-RunspaceDebug
```

```Output
 Id Name                 Enabled    BreakAll
 -- ----                 -------    --------
  1 Runspace1            False      False
```

## <span data-ttu-id="28909-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="28909-116">PARAMETERS</span></span>

### <span data-ttu-id="28909-117">-Appdomainname</span><span class="sxs-lookup"><span data-stu-id="28909-117">-AppDomainName</span></span>

<span data-ttu-id="28909-118">Der Name der Anwendungsdomäne, die den PowerShell-Runspace hostet.</span><span class="sxs-lookup"><span data-stu-id="28909-118">The name of the application domain that hosts the PowerShell runspace.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ProcessNameParameterSet
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="28909-119">-ProcessName</span><span class="sxs-lookup"><span data-stu-id="28909-119">-ProcessName</span></span>

<span data-ttu-id="28909-120">Der Name des Prozesses, der den PowerShell-Runspace hostet.</span><span class="sxs-lookup"><span data-stu-id="28909-120">The name of the process that hosts the PowerShell runspace.</span></span>

```yaml
Type: System.String
Parameter Sets: ProcessNameParameterSet
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="28909-121">-Runspace</span><span class="sxs-lookup"><span data-stu-id="28909-121">-Runspace</span></span>

<span data-ttu-id="28909-122">Mindestens ein **Runspace** -Objekt, das deaktiviert werden soll.</span><span class="sxs-lookup"><span data-stu-id="28909-122">One or more **Runspace** objects to be disabled.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.Runspace[]
Parameter Sets: RunspaceParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="28909-123">-Runspaceid</span><span class="sxs-lookup"><span data-stu-id="28909-123">-RunspaceId</span></span>

<span data-ttu-id="28909-124">Mindestens eine zu deaktivier Ende **Runspace** -ID-Nummer.</span><span class="sxs-lookup"><span data-stu-id="28909-124">One or more **Runspace** Id numbers to be disabled.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: RunspaceIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="28909-125">-Runspaceinstanceid</span><span class="sxs-lookup"><span data-stu-id="28909-125">-RunspaceInstanceId</span></span>

<span data-ttu-id="28909-126">Mindestens eine **Runspace** -GUIDs, die deaktiviert werden soll.</span><span class="sxs-lookup"><span data-stu-id="28909-126">One or more **Runspace** GUIDs to be disabled.</span></span>

```yaml
Type: System.Guid[]
Parameter Sets: RunspaceInstanceIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="28909-127">-Runspacename</span><span class="sxs-lookup"><span data-stu-id="28909-127">-RunspaceName</span></span>

<span data-ttu-id="28909-128">Mindestens ein **Runspace** -Name, der deaktiviert werden soll.</span><span class="sxs-lookup"><span data-stu-id="28909-128">One or more **Runspace** names to be disabled.</span></span>

```yaml
Type: System.String[]
Parameter Sets: RunspaceNameParameterSet
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="28909-129">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="28909-129">CommonParameters</span></span>

<span data-ttu-id="28909-130">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="28909-130">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="28909-131">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="28909-131">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="28909-132">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="28909-132">INPUTS</span></span>

## <span data-ttu-id="28909-133">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="28909-133">OUTPUTS</span></span>

## <span data-ttu-id="28909-134">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="28909-134">NOTES</span></span>

## <span data-ttu-id="28909-135">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="28909-135">RELATED LINKS</span></span>

[<span data-ttu-id="28909-136">Disable-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="28909-136">Disable-RunspaceDebug</span></span>](Disable-RunspaceDebug.md)

[<span data-ttu-id="28909-137">Enable-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="28909-137">Enable-RunspaceDebug</span></span>](Enable-RunspaceDebug.md)
