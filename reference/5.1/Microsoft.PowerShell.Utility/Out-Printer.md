---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/out-printer?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Out-Printer
ms.openlocfilehash: ec8d080da133310270d022b00f7f92d08ea3ca41
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213780"
---
# <span data-ttu-id="755c4-103">Out-Printer</span><span class="sxs-lookup"><span data-stu-id="755c4-103">Out-Printer</span></span>

## <span data-ttu-id="755c4-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="755c4-104">SYNOPSIS</span></span>
<span data-ttu-id="755c4-105">Sendet die Ausgabe an einen Drucker.</span><span class="sxs-lookup"><span data-stu-id="755c4-105">Sends output to a printer.</span></span>

## <span data-ttu-id="755c4-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="755c4-106">SYNTAX</span></span>

```
Out-Printer [[-Name] <String>] [-InputObject <PSObject>] [<CommonParameters>]
```

## <span data-ttu-id="755c4-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="755c4-107">DESCRIPTION</span></span>

<span data-ttu-id="755c4-108">Das- `Out-Printer` Cmdlet sendet die Ausgabe an den Standarddrucker oder an einen alternativen Drucker, sofern ein solcher angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="755c4-108">The `Out-Printer` cmdlet sends output to the default printer or to an alternate printer, if one is specified.</span></span>

> [!NOTE]
> <span data-ttu-id="755c4-109">Dieses Cmdlet wurde in PowerShell 7 erneut eingeführt.</span><span class="sxs-lookup"><span data-stu-id="755c4-109">This cmdlet was reintroduced in PowerShell 7.</span></span> <span data-ttu-id="755c4-110">Dieses Cmdlet ist nur auf Windows-Systemen verfügbar, die den Windows-Desktop unterstützen.</span><span class="sxs-lookup"><span data-stu-id="755c4-110">This cmdlet is only available on Windows systems that support the Windows Desktop.</span></span>

## <span data-ttu-id="755c4-111">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="755c4-111">EXAMPLES</span></span>

### <span data-ttu-id="755c4-112">Beispiel 1: Senden einer Datei, die auf dem Standarddrucker gedruckt werden soll</span><span class="sxs-lookup"><span data-stu-id="755c4-112">Example 1 - Send a file to be printed on the default printer</span></span>

<span data-ttu-id="755c4-113">In diesem Beispiel wird gezeigt, wie Sie eine Datei drucken, obwohl `Out-Printer` nicht über einen **path** -Parameter verfügt.</span><span class="sxs-lookup"><span data-stu-id="755c4-113">This example shows how to print a file, even though `Out-Printer` does not have a **Path** parameter.</span></span>

```powershell
Get-Content -Path ./readme.txt | Out-Printer
```

<span data-ttu-id="755c4-114">`Get-Content`Ruft den Inhalt der `readme.txt` Datei im aktuellen Verzeichnis ab und leitet ihn an `Out-Printer` , wodurch der Inhalt an den Standarddrucker gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="755c4-114">`Get-Content`gets the contents of the `readme.txt` file in the current directory and pipes it to `Out-Printer`, which sends it to the default printer.</span></span>

### <span data-ttu-id="755c4-115">Beispiel 2: Drucken einer Zeichenfolge auf einem Remote Drucker</span><span class="sxs-lookup"><span data-stu-id="755c4-115">Example 2: Print a string to a remote printer</span></span>

<span data-ttu-id="755c4-116">In diesem Beispiel wird `Hello, World` der **PRT-6B-Farb** Drucker auf Server01 gedruckt.</span><span class="sxs-lookup"><span data-stu-id="755c4-116">This example prints `Hello, World` to the **Prt-6B Color** printer on Server01.</span></span>

```powershell
"Hello, World" | Out-Printer -Name "\\Server01\Prt-6B Color"
```

<span data-ttu-id="755c4-117">Mit dem **Name** -Parameter wird anstelle der Standardeinstellung ein bestimmter Drucker ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="755c4-117">The **Name** parameter selects a specific printer, rather than the default.</span></span>

### <span data-ttu-id="755c4-118">Beispiel 3: Drucken eines Hilfe Themas für den Standarddrucker</span><span class="sxs-lookup"><span data-stu-id="755c4-118">Example 3 - Print a help topic to the default printer</span></span>

<span data-ttu-id="755c4-119">In diesem Beispiel wird die vollständige Version des Hilfe Themas für gedruckt `Get-CimInstance` .</span><span class="sxs-lookup"><span data-stu-id="755c4-119">This example prints the full version of the Help topic for `Get-CimInstance`.</span></span>

```powershell
$H = Get-Help -Full Get-CimInstance
Out-Printer -InputObject $H
```

<span data-ttu-id="755c4-120">`Get-Help` Ruft die vollständige Version des Hilfe Themas für ab `Get-CimInstance` und speichert Sie in der `$H` Variablen.</span><span class="sxs-lookup"><span data-stu-id="755c4-120">`Get-Help` gets the full version of the Help topic for `Get-CimInstance` and stores it in the `$H` variable.</span></span> <span data-ttu-id="755c4-121">Der **Inputobject** -Parameter übergibt den Wert von `$H` an `Out-Printer` .</span><span class="sxs-lookup"><span data-stu-id="755c4-121">The **InputObject** parameter passes the value of `$H` to `Out-Printer`.</span></span>

## <span data-ttu-id="755c4-122">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="755c4-122">PARAMETERS</span></span>

### <span data-ttu-id="755c4-123">-InputObject</span><span class="sxs-lookup"><span data-stu-id="755c4-123">-InputObject</span></span>

<span data-ttu-id="755c4-124">Gibt die an den Drucker zu sendenden Objekte an.</span><span class="sxs-lookup"><span data-stu-id="755c4-124">Specifies the objects to be sent to the printer.</span></span> <span data-ttu-id="755c4-125">Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, mit dem die Objekte abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="755c4-125">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="755c4-126">-Name</span><span class="sxs-lookup"><span data-stu-id="755c4-126">-Name</span></span>

<span data-ttu-id="755c4-127">Sendet die Ausgabe an den angegebenen Drucker.</span><span class="sxs-lookup"><span data-stu-id="755c4-127">Sends the output to the specified printer.</span></span> <span data-ttu-id="755c4-128">Der Parameter Name **Name** ist optional.</span><span class="sxs-lookup"><span data-stu-id="755c4-128">The parameter name **Name** is optional.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PrinterName

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="755c4-129">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="755c4-129">CommonParameters</span></span>

<span data-ttu-id="755c4-130">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="755c4-130">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="755c4-131">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="755c4-131">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="755c4-132">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="755c4-132">INPUTS</span></span>

### <span data-ttu-id="755c4-133">System. Management. Automation. psobject</span><span class="sxs-lookup"><span data-stu-id="755c4-133">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="755c4-134">Sie können jedes beliebige Objekt an die Pipeline übergeben `Out-Printer` .</span><span class="sxs-lookup"><span data-stu-id="755c4-134">You can pipe any object to `Out-Printer`.</span></span>

## <span data-ttu-id="755c4-135">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="755c4-135">OUTPUTS</span></span>

### <span data-ttu-id="755c4-136">Keine</span><span class="sxs-lookup"><span data-stu-id="755c4-136">None</span></span>

<span data-ttu-id="755c4-137">`Out-Printer` gibt keine-Objekte zurück.</span><span class="sxs-lookup"><span data-stu-id="755c4-137">`Out-Printer` does not return any objects.</span></span>

## <span data-ttu-id="755c4-138">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="755c4-138">NOTES</span></span>

<span data-ttu-id="755c4-139">Mit den Cmdlets, die das Verb enthalten, werden `Out` Objekte nicht formatiert.</span><span class="sxs-lookup"><span data-stu-id="755c4-139">The cmdlets that contain the `Out` verb do not format objects.</span></span> <span data-ttu-id="755c4-140">Sie werden lediglich angezeigt und an das angegebene Anzeige Ziel gesendet.</span><span class="sxs-lookup"><span data-stu-id="755c4-140">They just render them and send them to the specified display destination.</span></span> <span data-ttu-id="755c4-141">Wenn Sie ein unformatiertes Objekt an ein `Out` Cmdlet senden, sendet das Cmdlet es vor dem Rendern an ein Formatierungs-Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="755c4-141">If you send an unformatted object to an `Out` cmdlet, the cmdlet sends it to a formatting cmdlet before rendering it.</span></span>

<span data-ttu-id="755c4-142">`Out-Printer` sendet Daten an den Drucker, gibt aber keine Ausgabe Objekte an die Pipeline aus.</span><span class="sxs-lookup"><span data-stu-id="755c4-142">`Out-Printer` sends data to the printer, but does not emit any output objects to the pipeline.</span></span> <span data-ttu-id="755c4-143">Wenn Sie die Ausgabe von `Out-Printer` an übergeben `Get-Member` , `Get-Member` meldet, dass keine Objekte angegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="755c4-143">If you pipe the output of `Out-Printer` to `Get-Member`, `Get-Member` reports that no objects have been specified.</span></span>

## <span data-ttu-id="755c4-144">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="755c4-144">RELATED LINKS</span></span>

[<span data-ttu-id="755c4-145">Out-File</span><span class="sxs-lookup"><span data-stu-id="755c4-145">Out-File</span></span>](Out-File.md)

[<span data-ttu-id="755c4-146">Out-String</span><span class="sxs-lookup"><span data-stu-id="755c4-146">Out-String</span></span>](Out-String.md)