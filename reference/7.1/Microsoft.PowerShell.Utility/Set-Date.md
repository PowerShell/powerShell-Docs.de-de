---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 4/30/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/set-date?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Date
ms.openlocfilehash: 1c2a029a20b80826f74662a2b68d4a5f32276b00
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93211820"
---
# <span data-ttu-id="2c468-103">Set-Date</span><span class="sxs-lookup"><span data-stu-id="2c468-103">Set-Date</span></span>

## <span data-ttu-id="2c468-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="2c468-104">SYNOPSIS</span></span>
<span data-ttu-id="2c468-105">Ändert die Systemzeit auf dem Computer in eine von Ihnen angegebene Uhrzeit.</span><span class="sxs-lookup"><span data-stu-id="2c468-105">Changes the system time on the computer to a time that you specify.</span></span>

## <span data-ttu-id="2c468-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2c468-106">SYNTAX</span></span>

### <span data-ttu-id="2c468-107">Datum (Standard)</span><span class="sxs-lookup"><span data-stu-id="2c468-107">Date (Default)</span></span>

```
Set-Date [-Date] <DateTime> [-DisplayHint <DisplayHintType>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="2c468-108">Anpassen</span><span class="sxs-lookup"><span data-stu-id="2c468-108">Adjust</span></span>

```
Set-Date [-Adjust] <TimeSpan> [-DisplayHint <DisplayHintType>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="2c468-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2c468-109">DESCRIPTION</span></span>

<span data-ttu-id="2c468-110">Das- `Set-Date` Cmdlet ändert das Systemdatum und die Uhrzeit auf dem Computer in eine von Ihnen angegebene Datums-und uhrzeitanzeit.</span><span class="sxs-lookup"><span data-stu-id="2c468-110">The `Set-Date` cmdlet changes the system date and time on the computer to a date and time that you specify.</span></span>
<span data-ttu-id="2c468-111">Sie können ein neues Datum und/oder eine Uhrzeit angeben, indem Sie eine Zeichenfolge eingeben oder ein **DateTime** -oder **TimeSpan** -Objekt an übergeben `Set-Date` .</span><span class="sxs-lookup"><span data-stu-id="2c468-111">You can specify a new date and/or time by typing a string or by passing a **DateTime** or **TimeSpan** object to `Set-Date`.</span></span> <span data-ttu-id="2c468-112">Um ein neues Datum oder eine Uhrzeit anzugeben, verwenden Sie den **Date** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="2c468-112">To specify a new date or time, use the **Date** parameter.</span></span>
<span data-ttu-id="2c468-113">Verwenden Sie den Parameter " **Anpassen** ", um ein Änderungs Intervall anzugeben.</span><span class="sxs-lookup"><span data-stu-id="2c468-113">To specify a change interval, use the **Adjust** parameter.</span></span>

## <span data-ttu-id="2c468-114">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="2c468-114">EXAMPLES</span></span>

### <span data-ttu-id="2c468-115">Beispiel 1: Hinzufügen von drei Tagen zum Systemdatum</span><span class="sxs-lookup"><span data-stu-id="2c468-115">Example 1: Add three days to the system date</span></span>

<span data-ttu-id="2c468-116">Mit diesem Befehl werden dem aktuellen Datum drei Tage hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="2c468-116">This command adds three days to the current system date.</span></span>
<span data-ttu-id="2c468-117">Er wirkt sich nicht auf die Uhrzeit aus.</span><span class="sxs-lookup"><span data-stu-id="2c468-117">It does not affect the time.</span></span>
<span data-ttu-id="2c468-118">Der Befehl verwendet den **Date** -Parameter, um das Datum anzugeben.</span><span class="sxs-lookup"><span data-stu-id="2c468-118">The command uses the **Date** parameter to specify the date.</span></span>

<span data-ttu-id="2c468-119">Mit dem- `Get-Date` Cmdlet wird das aktuelle Datum als **DateTime** -Objekt zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="2c468-119">The `Get-Date` cmdlet returns the current date as a **DateTime** object.</span></span> <span data-ttu-id="2c468-120">Die **addDays** -Methode des **DateTime** -Objekts fügt dem aktuellen **DateTime** -Objekt eine angegebene Anzahl von Tagen (3) hinzu.</span><span class="sxs-lookup"><span data-stu-id="2c468-120">The **DateTime** object's **AddDays** method adds a specified number of days (3) to the current **DateTime** object.</span></span>

```powershell
Set-Date -Date (Get-Date).AddDays(3)
```

### <span data-ttu-id="2c468-121">Beispiel 2: Festlegen der Systemuhr auf 10 Minuten</span><span class="sxs-lookup"><span data-stu-id="2c468-121">Example 2: Set the system clock back 10 minutes</span></span>

<span data-ttu-id="2c468-122">In diesem Beispiel wird die aktuelle Systemzeit um 10 Minuten zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="2c468-122">This example sets the current system time back by 10 minutes.</span></span>

<span data-ttu-id="2c468-123">Mit dem Parameter " **Anpassen** " können Sie ein Änderungs Intervall (abzüglich zehn Minuten) im Standardzeit Format für das Gebiets Schema angeben.</span><span class="sxs-lookup"><span data-stu-id="2c468-123">The **Adjust** parameter allows you to specify an interval of change (minus ten minutes) in the standard time format for the locale.</span></span>

<span data-ttu-id="2c468-124">Der **displayhint** -Parameter weist PowerShell an, nur die Uhrzeit anzuzeigen, wirkt sich jedoch nicht auf das **DateTime** -Objekt aus, das `Set-Date` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="2c468-124">The **DisplayHint** parameter tells PowerShell to display only the time, but it does not affect the **DateTime** object that `Set-Date` returns.</span></span>

```powershell
Set-Date -Adjust -0:10:0 -DisplayHint Time
```

### <span data-ttu-id="2c468-125">Beispiel 3: Festlegen des Datums und der Uhrzeit auf einen variablen Wert</span><span class="sxs-lookup"><span data-stu-id="2c468-125">Example 3: Set the date and time to a variable value</span></span>

<span data-ttu-id="2c468-126">Diese Befehle ändern das Systemdatum und die Uhrzeit auf dem lokalen Computer in das Datum und die Uhrzeit, die in der Variablen gespeichert sind `$T` .</span><span class="sxs-lookup"><span data-stu-id="2c468-126">These commands change the system date and time on local computer to the date and time saved in the variable `$T`.</span></span> <span data-ttu-id="2c468-127">Der erste Befehl ruft das Datum ab und speichert es in `$T` .</span><span class="sxs-lookup"><span data-stu-id="2c468-127">The first command gets the date and stores it in `$T`.</span></span>

<span data-ttu-id="2c468-128">Der zweite Befehl verwendet den **Date** -Parameter, um das **DateTime** -Objekt in an `$T` das `Set-Date` Cmdlet zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="2c468-128">The second command uses the **Date** parameter to pass the **DateTime** object in `$T` to the `Set-Date` cmdlet.</span></span>

```powershell
$T = Get-Date
Set-Date -Date $T
```

### <span data-ttu-id="2c468-129">Beispiel 4: Hinzufügen von 90 Minuten zur Systemuhr</span><span class="sxs-lookup"><span data-stu-id="2c468-129">Example 4: Add 90 minutes to the system clock</span></span>

<span data-ttu-id="2c468-130">Diese Befehle stellen die Systemzeit auf dem lokalen Computer um 90 Minuten vor.</span><span class="sxs-lookup"><span data-stu-id="2c468-130">These commands advance the system time on the local computer by 90 minutes.</span></span>

<span data-ttu-id="2c468-131">Der erste Befehl verwendet das `New-TimeSpan` Cmdlet, um ein **TimeSpan** -Objekt mit einem Intervall von 90 Minuten zu erstellen, und speichert es in der `$90mins` Variablen.</span><span class="sxs-lookup"><span data-stu-id="2c468-131">The first command uses the `New-TimeSpan` cmdlet to create a **TimeSpan** object with a 90-minute interval, and saves it in the `$90mins` variable.</span></span>

<span data-ttu-id="2c468-132">Der zweite Befehl verwendet den **Adjust** -Parameter von `Set-Date` , um das Datum mit dem Wert des **TimeSpan** -Objekts in der `$90mins` Variablen anzupassen.</span><span class="sxs-lookup"><span data-stu-id="2c468-132">The second command uses the **Adjust** parameter of `Set-Date` to adjust the date by the value of the **TimeSpan** object in the `$90mins` variable.</span></span>

```powershell
$90mins = New-TimeSpan -Minutes 90
Set-Date -Adjust $90mins
```

## <span data-ttu-id="2c468-133">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2c468-133">PARAMETERS</span></span>

### <span data-ttu-id="2c468-134">-Anpassen</span><span class="sxs-lookup"><span data-stu-id="2c468-134">-Adjust</span></span>

<span data-ttu-id="2c468-135">Gibt den Wert an, den dieses Cmdlet dem aktuellen Datum und der aktuellen Uhrzeit hinzufügt oder von diesem subtrahiert.</span><span class="sxs-lookup"><span data-stu-id="2c468-135">Specifies the value for which this cmdlet adds or subtracts from the current date and time.</span></span>
<span data-ttu-id="2c468-136">kann eine Anpassung im Standard Datums-und-Uhrzeit Format für Ihr Gebiets Schema eingeben, oder verwenden Sie den **Adjust** -Parameter, um ein **TimeSpan** -Objekt von `New-TimeSpan` an zu übergeben `Set-Date` .</span><span class="sxs-lookup"><span data-stu-id="2c468-136">can type an adjustment in standard date and time format for your locale or use the **Adjust** parameter to pass a **TimeSpan** object from `New-TimeSpan` to `Set-Date`.</span></span>

```yaml
Type: System.TimeSpan
Parameter Sets: Adjust
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="2c468-137">-Datum</span><span class="sxs-lookup"><span data-stu-id="2c468-137">-Date</span></span>

<span data-ttu-id="2c468-138">Ändert das Datum und die Uhrzeit in die angegebenen Werte.</span><span class="sxs-lookup"><span data-stu-id="2c468-138">Changes the date and time to the specified values.</span></span>
<span data-ttu-id="2c468-139">Sie können ein neues Datum im kurzen Datumsformat und eine Uhrzeit im Standardzeitformat für Ihr Gebietsschema eingeben.</span><span class="sxs-lookup"><span data-stu-id="2c468-139">You can type a new date in the short date format and a time in the standard time format for your locale.</span></span> <span data-ttu-id="2c468-140">Oder Sie können ein **DateTime** -Objekt von übergeben `Get-Date` .</span><span class="sxs-lookup"><span data-stu-id="2c468-140">Or, you can pass a **DateTime** object from `Get-Date`.</span></span>

<span data-ttu-id="2c468-141">Wenn Sie ein Datum, aber keine Uhrzeit angeben, wird `Set-Date` die Uhrzeit am angegebenen Datum auf Mitternacht geändert.</span><span class="sxs-lookup"><span data-stu-id="2c468-141">If you specify a date, but not a time, `Set-Date` changes the time to midnight on the specified date.</span></span> <span data-ttu-id="2c468-142">Wenn Sie nur eine Uhrzeit angeben, wird das Datum nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="2c468-142">If you specify only a time, it does not change the date.</span></span>

```yaml
Type: System.DateTime
Parameter Sets: Date
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="2c468-143">-Displayhint</span><span class="sxs-lookup"><span data-stu-id="2c468-143">-DisplayHint</span></span>

<span data-ttu-id="2c468-144">Gibt an, welche Elemente von Datum und Uhrzeit angezeigt werden. Die zulässigen Werte für diesen Parameter sind:</span><span class="sxs-lookup"><span data-stu-id="2c468-144">Specifies which elements of the date and time are displayed.The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="2c468-145">das Datum</span><span class="sxs-lookup"><span data-stu-id="2c468-145">Date.</span></span>
  <span data-ttu-id="2c468-146">zeigt nur das Datum an.</span><span class="sxs-lookup"><span data-stu-id="2c468-146">displays only the date.</span></span>
- <span data-ttu-id="2c468-147">Zeit.</span><span class="sxs-lookup"><span data-stu-id="2c468-147">Time.</span></span>
  <span data-ttu-id="2c468-148">zeigt nur die Uhrzeit an.</span><span class="sxs-lookup"><span data-stu-id="2c468-148">displays only the time.</span></span>
- <span data-ttu-id="2c468-149">DateTime.</span><span class="sxs-lookup"><span data-stu-id="2c468-149">DateTime.</span></span>
  <span data-ttu-id="2c468-150">zeigt das Datum und die Uhrzeit an.</span><span class="sxs-lookup"><span data-stu-id="2c468-150">displays the date and time.</span></span>

<span data-ttu-id="2c468-151">Dieser Parameter betrifft nur die Anzeige.</span><span class="sxs-lookup"><span data-stu-id="2c468-151">This parameter affects only the display.</span></span>
<span data-ttu-id="2c468-152">Dies wirkt sich nicht auf das **DateTime** -Objekt aus, das `Get-Date` abruft.</span><span class="sxs-lookup"><span data-stu-id="2c468-152">It does not affect the **DateTime** object that `Get-Date` retrieves.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.DisplayHintType
Parameter Sets: (All)
Aliases:
Accepted values: Date, Time, DateTime

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2c468-153">-Confirm</span><span class="sxs-lookup"><span data-stu-id="2c468-153">-Confirm</span></span>

<span data-ttu-id="2c468-154">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="2c468-154">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="2c468-155">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="2c468-155">-WhatIf</span></span>

<span data-ttu-id="2c468-156">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="2c468-156">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="2c468-157">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="2c468-157">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="2c468-158">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="2c468-158">CommonParameters</span></span>

<span data-ttu-id="2c468-159">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="2c468-159">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2c468-160">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="2c468-160">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="2c468-161">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="2c468-161">INPUTS</span></span>

### <span data-ttu-id="2c468-162">System.DateTime</span><span class="sxs-lookup"><span data-stu-id="2c468-162">System.DateTime</span></span>

<span data-ttu-id="2c468-163">Sie können ein Datum an die Pipeline übergeben `Set-Date` .</span><span class="sxs-lookup"><span data-stu-id="2c468-163">You can pipe a date to `Set-Date`.</span></span>

## <span data-ttu-id="2c468-164">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="2c468-164">OUTPUTS</span></span>

### <span data-ttu-id="2c468-165">System.DateTime</span><span class="sxs-lookup"><span data-stu-id="2c468-165">System.DateTime</span></span>

<span data-ttu-id="2c468-166">`Set-Date` Gibt ein-Objekt zurück, das das von ihm festgelegte Datum darstellt.</span><span class="sxs-lookup"><span data-stu-id="2c468-166">`Set-Date` returns an object that represents the date that it set.</span></span>

## <span data-ttu-id="2c468-167">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="2c468-167">NOTES</span></span>

- <span data-ttu-id="2c468-168">Verwenden Sie dieses Cmdlet vorsichtig, wenn Sie das Datum und die Uhrzeit auf dem Computer ändern.</span><span class="sxs-lookup"><span data-stu-id="2c468-168">Use this cmdlet cautiously when changing the date and time on the computer.</span></span> <span data-ttu-id="2c468-169">Die Änderung kann möglicherweise verhindern, dass der Computer systemweite Ereignisse und Updates erhält, die durch einen Datums- oder Uhrzeitwert ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="2c468-169">The change might prevent the computer from receiving system-wide events and updates that are triggered by a date or time.</span></span> <span data-ttu-id="2c468-170">Verwenden Sie die Parameter **WhatIf** und **Confirm** , um Fehler zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="2c468-170">Use the **WhatIf** and **Confirm** parameters to avoid errors.</span></span>
- <span data-ttu-id="2c468-171">Sie können .net-Standardmethoden mit den **DateTime** -und **TimeSpan** -Objekten verwenden, die mit verwendet werden `Set-Date` , z. b. **addDays** , **addmonate** und **FromFileTime** .</span><span class="sxs-lookup"><span data-stu-id="2c468-171">You can use standard .NET methods with the **DateTime** and **TimeSpan** objects used with `Set-Date`, such as **AddDays** , **AddMonths** , and **FromFileTime** .</span></span> <span data-ttu-id="2c468-172">Weitere Informationen finden Sie unter [DateTime-Methoden](/dotnet/api/system.datetime) und</span><span class="sxs-lookup"><span data-stu-id="2c468-172">For more information, see [DateTime Methods](/dotnet/api/system.datetime) and</span></span>

  <span data-ttu-id="2c468-173">[TimeSpan-Methoden](/dotnet/api/system.timespan) in der MSDN Library.</span><span class="sxs-lookup"><span data-stu-id="2c468-173">[TimeSpan Methods](/dotnet/api/system.timespan) in the MSDN library.</span></span>

## <span data-ttu-id="2c468-174">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="2c468-174">RELATED LINKS</span></span>

[<span data-ttu-id="2c468-175">Get-Date</span><span class="sxs-lookup"><span data-stu-id="2c468-175">Get-Date</span></span>](Get-Date.md)

[<span data-ttu-id="2c468-176">New-TimeSpan</span><span class="sxs-lookup"><span data-stu-id="2c468-176">New-TimeSpan</span></span>](New-TimeSpan.md)
