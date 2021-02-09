---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/25/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-date?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Date
ms.openlocfilehash: 6f5c76faafa2c68a6d9dfc604238c514489aa717
ms.sourcegitcommit: 3a1d80e27438976101f216b8c3d623c61b868db8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2021
ms.locfileid: "99975055"
---
# <span data-ttu-id="ce12e-102">Get-Date</span><span class="sxs-lookup"><span data-stu-id="ce12e-102">Get-Date</span></span>

## <span data-ttu-id="ce12e-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="ce12e-103">SYNOPSIS</span></span>
<span data-ttu-id="ce12e-104">Ruft das aktuelle Datum und die Uhrzeit ab.</span><span class="sxs-lookup"><span data-stu-id="ce12e-104">Gets the current date and time.</span></span>

## <span data-ttu-id="ce12e-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ce12e-105">SYNTAX</span></span>

### <span data-ttu-id="ce12e-106">Datum (Standard)</span><span class="sxs-lookup"><span data-stu-id="ce12e-106">Date (Default)</span></span>

```
Get-Date [[-Date] <DateTime>] [-Year <Int32>] [-Month <Int32>] [-Day <Int32>] [-Hour <Int32>]
 [-Minute <Int32>] [-Second <Int32>] [-Millisecond <Int32>] [-DisplayHint <DisplayHintType>]
 [-Format <String>] [-AsUTC] [<CommonParameters>]
```

### <span data-ttu-id="ce12e-107">Dateuformat</span><span class="sxs-lookup"><span data-stu-id="ce12e-107">DateUFormat</span></span>

```
Get-Date [[-Date] <DateTime>] [-Year <Int32>] [-Month <Int32>] [-Day <Int32>] [-Hour <Int32>]
 [-Minute <Int32>] [-Second <Int32>] [-Millisecond <Int32>] [-DisplayHint <DisplayHintType>]
 -UFormat <String> [<CommonParameters>]
```

### <span data-ttu-id="ce12e-108">Unixtimeseconds</span><span class="sxs-lookup"><span data-stu-id="ce12e-108">UnixTimeSeconds</span></span>

```
Get-Date -UnixTimeSeconds <Int64> [-Year <Int32>] [-Month <Int32>] [-Day <Int32>] [-Hour <Int32>]
 [-Minute <Int32>] [-Second <Int32>] [-Millisecond <Int32>] [-DisplayHint <DisplayHintType>]
 [-Format <String>] [-AsUTC] [<CommonParameters>]
```

### <span data-ttu-id="ce12e-109">Unixtimesecondsuformat</span><span class="sxs-lookup"><span data-stu-id="ce12e-109">UnixTimeSecondsUFormat</span></span>

```
Get-Date -UnixTimeSeconds <Int64> [-Year <Int32>] [-Month <Int32>] [-Day <Int32>] [-Hour <Int32>]
 [-Minute <Int32>] [-Second <Int32>] [-Millisecond <Int32>] [-DisplayHint <DisplayHintType>]
 -UFormat <String> [<CommonParameters>]
```

## <span data-ttu-id="ce12e-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="ce12e-110">DESCRIPTION</span></span>

<span data-ttu-id="ce12e-111">Mit dem- `Get-Date` Cmdlet wird ein **DateTime** -Objekt abgerufen, das das aktuelle Datum oder ein von Ihnen festgelegten Datum darstellt.</span><span class="sxs-lookup"><span data-stu-id="ce12e-111">The `Get-Date` cmdlet gets a **DateTime** object that represents the current date or a date that you specify.</span></span> <span data-ttu-id="ce12e-112">`Get-Date` das Datum und die Uhrzeit können in mehreren .net-und UNIX-Formaten formatiert werden.</span><span class="sxs-lookup"><span data-stu-id="ce12e-112">`Get-Date` can format the date and time in several .NET and UNIX formats.</span></span> <span data-ttu-id="ce12e-113">Sie können verwenden `Get-Date` , um eine Datums-oder Uhrzeit Zeichenfolge zu generieren, und die Zeichenfolge dann an andere Cmdlets oder Programme senden.</span><span class="sxs-lookup"><span data-stu-id="ce12e-113">You can use `Get-Date` to generate a date or time character string, and then send the string to other cmdlets or programs.</span></span>

<span data-ttu-id="ce12e-114">`Get-Date` verwendet die Kultur Einstellungen des Computers, um zu bestimmen, wie die Ausgabe formatiert wird.</span><span class="sxs-lookup"><span data-stu-id="ce12e-114">`Get-Date` uses the computer's culture settings to determine how the output is formatted.</span></span> <span data-ttu-id="ce12e-115">Verwenden Sie, um die Einstellungen des Computers anzuzeigen `(Get-Culture).DateTimeFormat` .</span><span class="sxs-lookup"><span data-stu-id="ce12e-115">To view your computer's settings, use `(Get-Culture).DateTimeFormat`.</span></span>

## <span data-ttu-id="ce12e-116">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="ce12e-116">EXAMPLES</span></span>

### <span data-ttu-id="ce12e-117">Beispiel 1: erhalten des aktuellen Datums und der aktuellen Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="ce12e-117">Example 1: Get the current date and time</span></span>

<span data-ttu-id="ce12e-118">In diesem Beispiel werden `Get-Date` das aktuelle Systemdatum und die aktuelle Systemzeit angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ce12e-118">In this example, `Get-Date` displays the current system date and time.</span></span> <span data-ttu-id="ce12e-119">Die Ausgabe erfolgt in den langen Datums-und lang Zeitformaten.</span><span class="sxs-lookup"><span data-stu-id="ce12e-119">The output is in the long-date and long-time formats.</span></span>

```powershell
Get-Date
```

```Output
Tuesday, June 25, 2019 14:53:32
```

### <span data-ttu-id="ce12e-120">Beispiel 2: erhalten von Elementen des aktuellen Datums und der aktuellen Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="ce12e-120">Example 2: Get elements of the current date and time</span></span>

<span data-ttu-id="ce12e-121">In diesem Beispiel wird gezeigt, wie verwendet wird `Get-Date` , um das Date-oder Time-Element zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="ce12e-121">This example shows how to use `Get-Date` to get either the date or time element.</span></span> <span data-ttu-id="ce12e-122">Der-Parameter verwendet die Argumente **Date**, **time** oder **DateTime**.</span><span class="sxs-lookup"><span data-stu-id="ce12e-122">The parameter uses the arguments **Date**, **Time**, or **DateTime**.</span></span>

```powershell
Get-Date -DisplayHint Date
```

```Output
Tuesday, June 25, 2019
```

<span data-ttu-id="ce12e-123">`Get-Date` verwendet den **displayhint** -Parameter mit dem **Date** -Argument, um nur das Datum zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="ce12e-123">`Get-Date` uses the **DisplayHint** parameter with the **Date** argument to get only the date.</span></span>

### <span data-ttu-id="ce12e-124">Beispiel 3: erhalten von Datum und Uhrzeit mit einem .NET-Format Bezeichner</span><span class="sxs-lookup"><span data-stu-id="ce12e-124">Example 3: Get the date and time with a .NET format specifier</span></span>

<span data-ttu-id="ce12e-125">In diesem Beispiel wird ein .net-Formatspezifizierer zum Anpassen des Ausgabeformats verwendet.</span><span class="sxs-lookup"><span data-stu-id="ce12e-125">In this example, a .NET format specifier is used to customize the output's format.</span></span> <span data-ttu-id="ce12e-126">Bei der Ausgabe handelt es sich um ein **Zeichen** folgen Objekt.</span><span class="sxs-lookup"><span data-stu-id="ce12e-126">The output is a **String** object.</span></span>

```powershell
Get-Date -Format "dddd MM/dd/yyyy HH:mm K"
```

```Output
Tuesday 06/25/2019 16:17 -07:00
```

<span data-ttu-id="ce12e-127">`Get-Date` verwendet den **Format** -Parameter, um mehrere Format Bearbeiter anzugeben.</span><span class="sxs-lookup"><span data-stu-id="ce12e-127">`Get-Date` uses the **Format** parameter to specify several format specifiers.</span></span>

<span data-ttu-id="ce12e-128">Die in diesem Beispiel verwendeten .net-Formatspezifizierer sind wie folgt definiert:</span><span class="sxs-lookup"><span data-stu-id="ce12e-128">The .NET format specifiers used in this example are defined as follows:</span></span>

| <span data-ttu-id="ce12e-129">Bezeichner</span><span class="sxs-lookup"><span data-stu-id="ce12e-129">Specifier</span></span> |                      <span data-ttu-id="ce12e-130">Definition</span><span class="sxs-lookup"><span data-stu-id="ce12e-130">Definition</span></span>                       |
| --------- | ----------------------------------------------------- |
| `dddd`    | <span data-ttu-id="ce12e-131">Wochentag-vollständiger Name</span><span class="sxs-lookup"><span data-stu-id="ce12e-131">Day of the week - full name</span></span>                           |
| `MM`      | <span data-ttu-id="ce12e-132">Monatsnummer</span><span class="sxs-lookup"><span data-stu-id="ce12e-132">Month number</span></span>                                          |
| `dd`      | <span data-ttu-id="ce12e-133">Tag des Monats-2 Ziffern</span><span class="sxs-lookup"><span data-stu-id="ce12e-133">Day of the month - 2 digits</span></span>                           |
| `yyyy`    | <span data-ttu-id="ce12e-134">Jahr im vierstelligen Format</span><span class="sxs-lookup"><span data-stu-id="ce12e-134">Year in 4-digit format</span></span>                                |
| `HH:mm`   | <span data-ttu-id="ce12e-135">Uhrzeit im 24-Stunden-Format-keine Sekunden</span><span class="sxs-lookup"><span data-stu-id="ce12e-135">Time in 24-hour format - no seconds</span></span>                    |
| `K`       | <span data-ttu-id="ce12e-136">Zeit Zonen Offset von universeller Zeit Koordinate (UTC)</span><span class="sxs-lookup"><span data-stu-id="ce12e-136">Time zone offset from Universal Time Coordinate (UTC)</span></span> |

<span data-ttu-id="ce12e-137">Weitere Informationen zu .NET-Format Bezeichnerzeichen finden Sie unter benutzerdefinierte Format Zeichenfolgen für [Datum und Uhrzeit](/dotnet/standard/base-types/custom-date-and-time-format-strings?view=netframework-4.8).</span><span class="sxs-lookup"><span data-stu-id="ce12e-137">For more information about .NET format specifiers, see [Custom date and time format strings](/dotnet/standard/base-types/custom-date-and-time-format-strings?view=netframework-4.8).</span></span>

### <span data-ttu-id="ce12e-138">Beispiel 4: Holen Sie sich das Datum und die Uhrzeit mit einem Uformat-Spezifizierer.</span><span class="sxs-lookup"><span data-stu-id="ce12e-138">Example 4: Get the date and time with a UFormat specifier</span></span>

<span data-ttu-id="ce12e-139">In diesem Beispiel werden mehrere **Uformat** -Formatspezifizierer verwendet, um das Format der Ausgabe anzupassen.</span><span class="sxs-lookup"><span data-stu-id="ce12e-139">In this example, several **UFormat** format specifiers are used to customize the output's format.</span></span>
<span data-ttu-id="ce12e-140">Bei der Ausgabe handelt es sich um ein **Zeichen** folgen Objekt.</span><span class="sxs-lookup"><span data-stu-id="ce12e-140">The output is a **String** object.</span></span>

```powershell
Get-Date -UFormat "%A %m/%d/%Y %R %Z"
```

```Output
Tuesday 06/25/2019 16:19 -07
```

<span data-ttu-id="ce12e-141">`Get-Date` verwendet den **Uformat** -Parameter, um mehrere Format Bearbeiter anzugeben.</span><span class="sxs-lookup"><span data-stu-id="ce12e-141">`Get-Date` uses the **UFormat** parameter to specify several format specifiers.</span></span>

<span data-ttu-id="ce12e-142">Die in diesem Beispiel verwendeten **Uformat** -Format Bearbeiter werden wie folgt definiert:</span><span class="sxs-lookup"><span data-stu-id="ce12e-142">The **UFormat** format specifiers used in this example are defined as follows:</span></span>

| <span data-ttu-id="ce12e-143">Bezeichner</span><span class="sxs-lookup"><span data-stu-id="ce12e-143">Specifier</span></span> |                      <span data-ttu-id="ce12e-144">Definition</span><span class="sxs-lookup"><span data-stu-id="ce12e-144">Definition</span></span>                       |
| --------- | ----------------------------------------------------- |
| `%A`      | <span data-ttu-id="ce12e-145">Wochentag-vollständiger Name</span><span class="sxs-lookup"><span data-stu-id="ce12e-145">Day of the week - full name</span></span>                           |
| `%m`      | <span data-ttu-id="ce12e-146">Monatsnummer</span><span class="sxs-lookup"><span data-stu-id="ce12e-146">Month number</span></span>                                          |
| `%d`      | <span data-ttu-id="ce12e-147">Tag des Monats-2 Ziffern</span><span class="sxs-lookup"><span data-stu-id="ce12e-147">Day of the month - 2 digits</span></span>                           |
| `%Y`      | <span data-ttu-id="ce12e-148">Jahr im vierstelligen Format</span><span class="sxs-lookup"><span data-stu-id="ce12e-148">Year in 4-digit format</span></span>                                |
| `%R`      | <span data-ttu-id="ce12e-149">Uhrzeit im 24-Stunden-Format-keine Sekunden</span><span class="sxs-lookup"><span data-stu-id="ce12e-149">Time in 24-hour format - no seconds</span></span>                    |
| `%Z`      | <span data-ttu-id="ce12e-150">Zeit Zonen Offset von universeller Zeit Koordinate (UTC)</span><span class="sxs-lookup"><span data-stu-id="ce12e-150">Time zone offset from Universal Time Coordinate (UTC)</span></span> |

<span data-ttu-id="ce12e-151">Eine Liste gültiger **Uformat** -Format Bearbeiter finden Sie im Abschnitt " [Hinweise](#notes) ".</span><span class="sxs-lookup"><span data-stu-id="ce12e-151">For a list of valid **UFormat** format specifiers, see the [Notes](#notes) section.</span></span>

### <span data-ttu-id="ce12e-152">Beispiel 5: Holen Sie sich den Tag des Jahres für einen Tag.</span><span class="sxs-lookup"><span data-stu-id="ce12e-152">Example 5: Get a date's day of the year</span></span>

<span data-ttu-id="ce12e-153">In diesem Beispiel wird eine-Eigenschaft verwendet, um den numerischen Tag des Jahres zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="ce12e-153">In this example, a property is used to get the numeric day of the year.</span></span>

<span data-ttu-id="ce12e-154">Der gregorianische Kalender hat 365 Tage, mit Ausnahme von Schaltjahren, die 366 Tage lang sind.</span><span class="sxs-lookup"><span data-stu-id="ce12e-154">The Gregorian calendar has 365 days, except for leap years that have 366 days.</span></span> <span data-ttu-id="ce12e-155">Beispielsweise ist der 31. Dezember 2020 der Tag 366.</span><span class="sxs-lookup"><span data-stu-id="ce12e-155">For example, December 31, 2020 is day 366.</span></span>

```powershell
(Get-Date -Year 2020 -Month 12 -Day 31).DayOfYear
```

```Output
366
```

<span data-ttu-id="ce12e-156">`Get-Date` verwendet drei Parameter, um das Datum anzugeben: **year**, **Month** und **Day**.</span><span class="sxs-lookup"><span data-stu-id="ce12e-156">`Get-Date` uses three parameters to specify the date: **Year**, **Month**, and **Day**.</span></span> <span data-ttu-id="ce12e-157">Der Befehl wird in Klammern eingeschlossen, sodass das Ergebnis von der **dayof Year** -Eigenschaft ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="ce12e-157">The command is wrapped with parentheses so that the result is evaluated by the **DayofYear** property.</span></span>

### <span data-ttu-id="ce12e-158">Beispiel 6: überprüfen, ob ein Datum für die Sommerzeit angepasst ist</span><span class="sxs-lookup"><span data-stu-id="ce12e-158">Example 6: Check if a date is adjusted for daylight savings time</span></span>

<span data-ttu-id="ce12e-159">In diesem Beispiel wird eine boolesche Methode verwendet, um zu überprüfen, ob ein Datum nach Sommerzeit angepasst wird.</span><span class="sxs-lookup"><span data-stu-id="ce12e-159">This example uses a boolean method to verify if a date is adjusted by daylight savings time.</span></span>

```powershell
$DST = Get-Date
$DST.IsDaylightSavingTime()
```

```Output
True
```

<span data-ttu-id="ce12e-160">Eine Variable, `$DST` die das Ergebnis von speichert `Get-Date` .</span><span class="sxs-lookup"><span data-stu-id="ce12e-160">A variable, `$DST` stores the result of `Get-Date`.</span></span> <span data-ttu-id="ce12e-161">`$DST` verwendet die **IsDaylightSavingTime** -Methode, um zu testen, ob das Datum für die Sommerzeit angepasst wird.</span><span class="sxs-lookup"><span data-stu-id="ce12e-161">`$DST` uses the **IsDaylightSavingTime** method to test if the date is adjusted for daylight savings time.</span></span>

### <span data-ttu-id="ce12e-162">Beispiel 7: Konvertieren der aktuellen Uhrzeit in die UTC-Zeit</span><span class="sxs-lookup"><span data-stu-id="ce12e-162">Example 7: Convert the current time to UTC time</span></span>

<span data-ttu-id="ce12e-163">In diesem Beispiel wird die aktuelle Uhrzeit in UTC-Zeit konvertiert.</span><span class="sxs-lookup"><span data-stu-id="ce12e-163">In this example, the current time is converted to UTC time.</span></span> <span data-ttu-id="ce12e-164">Der UTC-Offset für das Gebiets Schema des Systems wird zum Konvertieren der Zeit verwendet.</span><span class="sxs-lookup"><span data-stu-id="ce12e-164">The UTC offset for the system's locale is used to convert the time.</span></span> <span data-ttu-id="ce12e-165">Eine Tabelle im Abschnitt [Notes](#notes) listet die gültigen **Uformat** -Format Bearbeiter auf.</span><span class="sxs-lookup"><span data-stu-id="ce12e-165">A table in the [Notes](#notes) section lists the valid **UFormat** format specifiers.</span></span>

```powershell
Get-Date -UFormat "%A %B/%d/%Y %T %Z"
$Time = Get-Date
$Time.ToUniversalTime()
```

```Output
Wednesday June/26/2019 10:45:26 -07

Wednesday, June 26, 2019 17:45:26
```

<span data-ttu-id="ce12e-166">`Get-Date` verwendet den **Uformat** -Parameter mit Format Bezeichnerzeichen, um das aktuelle Systemdatum und die aktuelle Systemzeit anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ce12e-166">`Get-Date` uses the **UFormat** parameter with format specifiers to display the current system date and time.</span></span> <span data-ttu-id="ce12e-167">Der Format Bezeichner **% Z** stellt den UTC-Offset von **-07** dar.</span><span class="sxs-lookup"><span data-stu-id="ce12e-167">The format specifier **%Z** represents the UTC offset of **-07**.</span></span>

<span data-ttu-id="ce12e-168">Die `$Time` Variable speichert das aktuelle Systemdatum und die aktuelle Systemzeit.</span><span class="sxs-lookup"><span data-stu-id="ce12e-168">The `$Time` variable stores the current system date and time.</span></span> <span data-ttu-id="ce12e-169">`$Time` verwendet die **ToUniversalTime ()** -Methode, um die Zeit auf Grundlage des UTC-Offsets des Computers zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="ce12e-169">`$Time` uses the **ToUniversalTime()** method to convert the time based on the computer's UTC offset.</span></span>

### <span data-ttu-id="ce12e-170">Beispiel 8: Erstellen eines Zeitstempels</span><span class="sxs-lookup"><span data-stu-id="ce12e-170">Example 8: Create a timestamp</span></span>

<span data-ttu-id="ce12e-171">In diesem Beispiel erstellt ein Format Bezeichner ein Zeitstempel- **Zeichen** folgen Objekt für einen Verzeichnisnamen.</span><span class="sxs-lookup"><span data-stu-id="ce12e-171">In this example, a format specifier creates a timestamp **String** object for a directory name.</span></span> <span data-ttu-id="ce12e-172">Der Zeitstempel umfasst Datum, Uhrzeit und UTC-Offset.</span><span class="sxs-lookup"><span data-stu-id="ce12e-172">The timestamp includes the date, time, and UTC offset.</span></span>

```powershell
$timestamp = Get-Date -Format o | ForEach-Object { $_ -replace ":", "." }
New-Item -Path C:\Test\$timestamp -Type Directory
```

```Output
Directory: C:\Test

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----         6/27/2019    07:59                2019-06-27T07.59.24.4603750-07.00
```

<span data-ttu-id="ce12e-173">Die- `$timestamp` Variable speichert die Ergebnisse eines- `Get-Date` Befehls.</span><span class="sxs-lookup"><span data-stu-id="ce12e-173">The `$timestamp` variable stores the results of a `Get-Date` command.</span></span> <span data-ttu-id="ce12e-174">`Get-Date` verwendet den **Format** -Parameter mit dem Format Bezeichner "Kleinbuchstaben" `o` , um ein Zeitstempel- **Zeichen** folgen Objekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ce12e-174">`Get-Date` uses the **Format** parameter with the format specifier of lowercase `o` to create a timestamp **String** object.</span></span> <span data-ttu-id="ce12e-175">Das Objekt wird über die Pipeline an gesendet `ForEach-Object` .</span><span class="sxs-lookup"><span data-stu-id="ce12e-175">The object is sent down the pipeline to `ForEach-Object`.</span></span> <span data-ttu-id="ce12e-176">Ein **ScriptBlock** enthält die `$_` Variable, die das aktuelle Pipeline Objekt darstellt.</span><span class="sxs-lookup"><span data-stu-id="ce12e-176">A **ScriptBlock** contains the `$_` variable that represents the current pipeline object.</span></span> <span data-ttu-id="ce12e-177">Die Zeitstempel Zeichenfolge wird durch Doppelpunkte getrennt, die durch Zeiträume ersetzt werden.</span><span class="sxs-lookup"><span data-stu-id="ce12e-177">The timestamp string is delimited by colons that are replaced by periods.</span></span>

<span data-ttu-id="ce12e-178">`New-Item` verwendet den **path** -Parameter, um den Speicherort für ein neues Verzeichnis anzugeben.</span><span class="sxs-lookup"><span data-stu-id="ce12e-178">`New-Item` uses the **Path** parameter to specify the location for a new directory.</span></span> <span data-ttu-id="ce12e-179">Der Pfad enthält die `$timestamp` Variable als Verzeichnisnamen.</span><span class="sxs-lookup"><span data-stu-id="ce12e-179">The path includes the `$timestamp` variable as the directory name.</span></span> <span data-ttu-id="ce12e-180">Der **Typparameter** gibt an, dass ein Verzeichnis erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="ce12e-180">The **Type** parameter specifies that a directory is created.</span></span>

### <span data-ttu-id="ce12e-181">Beispiel 9: Konvertieren eines UNIX-Zeitstempels</span><span class="sxs-lookup"><span data-stu-id="ce12e-181">Example 9: Convert a Unix timestamp</span></span>

<span data-ttu-id="ce12e-182">In diesem Beispiel wird eine Unix-Zeitangabe (dargestellt durch die Anzahl von Sekunden seit dem 1970-01-01 0:00:00) in DateTime konvertiert.</span><span class="sxs-lookup"><span data-stu-id="ce12e-182">This example converts a Unix time (represented by the number of seconds since 1970-01-01 0:00:00) to DateTime.</span></span>

```powershell
Get-Date -UnixTimeSeconds 1577836800
```

```Output
Wednesday, January 01, 2020 12:00:00 AM
```

### <span data-ttu-id="ce12e-183">Beispiel 10: Zurückgeben eines als UTC interpretierten Datums Werts</span><span class="sxs-lookup"><span data-stu-id="ce12e-183">Example 10: Return a date value interpreted as UTC</span></span>

<span data-ttu-id="ce12e-184">Dieses Beispiel zeigt, wie ein Datumswert als UTC-Entsprechung interpretiert wird.</span><span class="sxs-lookup"><span data-stu-id="ce12e-184">This example shows how to interpret a date value as its UTC equivalent.</span></span> <span data-ttu-id="ce12e-185">In diesem Beispiel ist dieser Computer auf **Pacific Normalzeit** festgelegt.</span><span class="sxs-lookup"><span data-stu-id="ce12e-185">For the example, this machine is set to **Pacific Standard Time**.</span></span> <span data-ttu-id="ce12e-186">Standardmäßig `Get-Date` gibt Werte für diese Zeitzone zurück.</span><span class="sxs-lookup"><span data-stu-id="ce12e-186">By default, `Get-Date` returns values for that timezone.</span></span> <span data-ttu-id="ce12e-187">Verwenden Sie den **asutc** -Parameter, um den Wert in die entsprechende UTC-Zeit zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="ce12e-187">Use the **AsUTC** parameter to convert the value to the UTC equivalent time.</span></span>

```powershell
PS> Get-TimeZone

Id                         : Pacific Standard Time
DisplayName                : (UTC-08:00) Pacific Time (US & Canada)
StandardName               : Pacific Standard Time
DaylightName               : Pacific Daylight Time
BaseUtcOffset              : -08:00:00
SupportsDaylightSavingTime : True

PS> (Get-Date -Date "2020-01-01T00:00:00").Kind
Unspecified

PS> Get-Date -Date "2020-01-01T00:00:00"

Wednesday, January 1, 2020 12:00:00 AM

PS> (Get-Date -Date "2020-01-01T00:00:00" -AsUTC).Kind
Utc

PS> Get-Date -Date "2020-01-01T00:00:00" -AsUTC

Wednesday, January 1, 2020 8:00:00 AM
```

## <span data-ttu-id="ce12e-188">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ce12e-188">PARAMETERS</span></span>

### <span data-ttu-id="ce12e-189">-Asutc</span><span class="sxs-lookup"><span data-stu-id="ce12e-189">-AsUTC</span></span>

<span data-ttu-id="ce12e-190">Konvertiert den Datumswert in die entsprechende Zeit in UTC.</span><span class="sxs-lookup"><span data-stu-id="ce12e-190">Converts the date value to the equivalent time in UTC.</span></span>

<span data-ttu-id="ce12e-191">Dieser Parameter wurde in PowerShell 7,1 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="ce12e-191">This parameter was introduced in PowerShell 7.1.</span></span>

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

### <span data-ttu-id="ce12e-192">-Datum</span><span class="sxs-lookup"><span data-stu-id="ce12e-192">-Date</span></span>

<span data-ttu-id="ce12e-193">Gibt ein Datum und eine Uhrzeit an.</span><span class="sxs-lookup"><span data-stu-id="ce12e-193">Specifies a date and time.</span></span> <span data-ttu-id="ce12e-194">Time ist optional und gibt, wenn nicht angegeben, 00:00:00 zurück.</span><span class="sxs-lookup"><span data-stu-id="ce12e-194">Time is optional and if not specified, returns 00:00:00.</span></span>

<span data-ttu-id="ce12e-195">Geben Sie das Datum und die Uhrzeit in einem Standardformat für das Gebiets Schema des Systems ein.</span><span class="sxs-lookup"><span data-stu-id="ce12e-195">Enter the date and time in a format that is standard for the system locale.</span></span>

<span data-ttu-id="ce12e-196">Beispielsweise in Englisch (USA):</span><span class="sxs-lookup"><span data-stu-id="ce12e-196">For example, in US English:</span></span>

<span data-ttu-id="ce12e-197">`Get-Date -Date "6/25/2019 12:30:22"` Gibt den Dienstag, den 25. Juni 2019 12:30:22</span><span class="sxs-lookup"><span data-stu-id="ce12e-197">`Get-Date -Date "6/25/2019 12:30:22"` returns Tuesday, June 25, 2019 12:30:22</span></span>

```yaml
Type: System.DateTime
Parameter Sets: DateAndFormat, DateAndUFormat
Aliases: LastWriteTime

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="ce12e-198">-Tag</span><span class="sxs-lookup"><span data-stu-id="ce12e-198">-Day</span></span>

<span data-ttu-id="ce12e-199">Gibt den angezeigten Tag des Monats an.</span><span class="sxs-lookup"><span data-stu-id="ce12e-199">Specifies the day of the month that is displayed.</span></span> <span data-ttu-id="ce12e-200">Geben Sie einen Wert zwischen 1 und 31 ein.</span><span class="sxs-lookup"><span data-stu-id="ce12e-200">Enter a value from 1 to 31.</span></span>

<span data-ttu-id="ce12e-201">Wenn der angegebene Wert größer als die Anzahl der Tage in einem Monat ist, fügt PowerShell die Anzahl der Tage zum Monat hinzu.</span><span class="sxs-lookup"><span data-stu-id="ce12e-201">If the specified value is greater than the number of days in a month, PowerShell adds the number of days to the month.</span></span> <span data-ttu-id="ce12e-202">Zeigt beispielsweise `Get-Date -Month 2 -Day 31` den **3. März**, nicht den **31. Februar** an.</span><span class="sxs-lookup"><span data-stu-id="ce12e-202">For example, `Get-Date -Month 2 -Day 31` displays **March 3**, not **February 31**.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ce12e-203">-Displayhint</span><span class="sxs-lookup"><span data-stu-id="ce12e-203">-DisplayHint</span></span>

<span data-ttu-id="ce12e-204">Bestimmt, welche Elemente von Datum und Uhrzeit angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="ce12e-204">Determines which elements of the date and time are displayed.</span></span>

<span data-ttu-id="ce12e-205">Die zulässigen Werte lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="ce12e-205">The accepted values are as follows:</span></span>

- <span data-ttu-id="ce12e-206">**Date**: zeigt nur das Datum an.</span><span class="sxs-lookup"><span data-stu-id="ce12e-206">**Date**: displays only the date</span></span>
- <span data-ttu-id="ce12e-207">**Zeit**: zeigt nur die Uhrzeit an.</span><span class="sxs-lookup"><span data-stu-id="ce12e-207">**Time**: displays only the time</span></span>
- <span data-ttu-id="ce12e-208">**DateTime**: zeigt das Datum und die Uhrzeit an.</span><span class="sxs-lookup"><span data-stu-id="ce12e-208">**DateTime**: displays the date and time</span></span>

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

### <span data-ttu-id="ce12e-209">-Format</span><span class="sxs-lookup"><span data-stu-id="ce12e-209">-Format</span></span>

<span data-ttu-id="ce12e-210">Zeigt das Datum und die Uhrzeit im Microsoft .NET Framework-Format an, das durch den Formatbezeichner angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="ce12e-210">Displays the date and time in the Microsoft .NET Framework format indicated by the format specifier.</span></span>
<span data-ttu-id="ce12e-211">Der **Format** -Parameter gibt ein **String** -Objekt aus.</span><span class="sxs-lookup"><span data-stu-id="ce12e-211">The **Format** parameter outputs a **String** object.</span></span>

<span data-ttu-id="ce12e-212">Eine Liste der verfügbaren .net-Formatspezifizierer finden Sie unter benutzerdefinierte Format Zeichenfolgen für [Datum und Uhrzeit](/dotnet/standard/base-types/custom-date-and-time-format-strings?view=netframework-4.8).</span><span class="sxs-lookup"><span data-stu-id="ce12e-212">For a list of available .NET format specifiers, see [Custom date and time format strings](/dotnet/standard/base-types/custom-date-and-time-format-strings?view=netframework-4.8).</span></span>

<span data-ttu-id="ce12e-213">Wenn der **Format** -Parameter verwendet wird, ruft `Get-Date` nur die Eigenschaften des **DateTime** -Objekts ab, die zum Anzeigen des Datums erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="ce12e-213">When the **Format** parameter is used, `Get-Date` only gets the **DateTime** object's properties necessary to display the date.</span></span> <span data-ttu-id="ce12e-214">Folglich stehen einige der Eigenschaften und Methoden der **DateTime**-Objekte möglicherweise nicht zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="ce12e-214">As a result, some of the properties and methods of **DateTime** objects might not be available.</span></span>

<span data-ttu-id="ce12e-215">Ab PowerShell 5,0 können Sie die folgenden zusätzlichen Formate als Werte für den **Format** -Parameter verwenden.</span><span class="sxs-lookup"><span data-stu-id="ce12e-215">Starting in PowerShell 5.0, you can use the following additional formats as values for the **Format** parameter.</span></span>

- <span data-ttu-id="ce12e-216">**Filedate**.</span><span class="sxs-lookup"><span data-stu-id="ce12e-216">**FileDate**.</span></span> <span data-ttu-id="ce12e-217">Eine Datei-oder Pfad freundliche Darstellung des aktuellen Datums in der lokalen Zeit.</span><span class="sxs-lookup"><span data-stu-id="ce12e-217">A file or path-friendly representation of the current date in local time.</span></span> <span data-ttu-id="ce12e-218">Das Format ist `yyyyMMdd` (Unterscheidung nach Groß-/Kleinschreibung unter Berücksichtigung von vierstelligen Jahreszahlen, zweistelligen Ziffern und zweistelligen Tags).</span><span class="sxs-lookup"><span data-stu-id="ce12e-218">The format is `yyyyMMdd` (case-sensitive, using a 4-digit year, 2-digit month, and 2-digit day).</span></span> <span data-ttu-id="ce12e-219">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ce12e-219">For example:</span></span>
  20190627.

- <span data-ttu-id="ce12e-220">**Filedateuniversal**.</span><span class="sxs-lookup"><span data-stu-id="ce12e-220">**FileDateUniversal**.</span></span> <span data-ttu-id="ce12e-221">Eine Datei-oder Pfad freundliche Darstellung des aktuellen Datums in Weltzeit (UTC).</span><span class="sxs-lookup"><span data-stu-id="ce12e-221">A file or path-friendly representation of the current date in universal time (UTC).</span></span> <span data-ttu-id="ce12e-222">Das Format ist (Unterscheidung nach `yyyyMMddZ` Groß-/Kleinschreibung, mit einem vierstelligen Jahr, zweistelligen Ziffern und dem Buchstaben `Z` als UTC-Indikator).</span><span class="sxs-lookup"><span data-stu-id="ce12e-222">The format is `yyyyMMddZ` (case-sensitive, using a 4-digit year, 2-digit month, 2-digit day, and the letter `Z` as the UTC indicator).</span></span> <span data-ttu-id="ce12e-223">Beispiel: 20190627z.</span><span class="sxs-lookup"><span data-stu-id="ce12e-223">For example: 20190627Z.</span></span>

- <span data-ttu-id="ce12e-224">**FileDateTime**.</span><span class="sxs-lookup"><span data-stu-id="ce12e-224">**FileDateTime**.</span></span> <span data-ttu-id="ce12e-225">Eine Datei-oder Pfad freundliche Darstellung des aktuellen Datums und der aktuellen Uhrzeit in der Ortszeit im 24-Stunden-Format.</span><span class="sxs-lookup"><span data-stu-id="ce12e-225">A file or path-friendly representation of the current date and time in local time, in 24-hour format.</span></span> <span data-ttu-id="ce12e-226">Das Format ist (Unterscheidung nach Groß-/Kleinschreibung unter Berücksichtigung von vierstelligen Jahreszahlen, zweistelligen Ziffern, zweistelligen Ziffern, `yyyyMMddTHHmmssffff` dem Buchstaben `T` als Zeit Trennzeichen, zweistellige Stunden, zweistellige Minuten, zweistellige Sekunden und vierstellige Millisekunden).</span><span class="sxs-lookup"><span data-stu-id="ce12e-226">The format is `yyyyMMddTHHmmssffff` (case-sensitive, using a 4-digit year, 2-digit month, 2-digit day, the letter `T` as a time separator, 2-digit hour, 2-digit minute, 2-digit second, and 4-digit millisecond).</span></span> <span data-ttu-id="ce12e-227">Beispiel: 20190627t0840107271.</span><span class="sxs-lookup"><span data-stu-id="ce12e-227">For example: 20190627T0840107271.</span></span>

- <span data-ttu-id="ce12e-228">**Filedatetimeuniversal**.</span><span class="sxs-lookup"><span data-stu-id="ce12e-228">**FileDateTimeUniversal**.</span></span> <span data-ttu-id="ce12e-229">Eine Datei-oder Pfad freundliche Darstellung des aktuellen Datums und der aktuellen Uhrzeit (UTC) im 24-Stunden-Format.</span><span class="sxs-lookup"><span data-stu-id="ce12e-229">A file or path-friendly representation of the current date and time in universal time (UTC), in 24-hour format.</span></span> <span data-ttu-id="ce12e-230">Das Format lautet (Unterscheidung nach Groß-/Kleinschreibung, Unterscheidung nach `yyyyMMddTHHmmssffffZ` einem vierstelligen Jahr, zweistelligen Ziffern, zweistelligen Ziffern, der Buchstabe `T` als Zeit Trennzeichen, zweistellige Stunden, zweistellige Minuten, zweistellige Sekunden, vierstellige Millisekunden und der Buchstabe `Z` als UTC-Indikator).</span><span class="sxs-lookup"><span data-stu-id="ce12e-230">The format is `yyyyMMddTHHmmssffffZ` (case-sensitive, using a 4-digit year, 2-digit month, 2-digit day, the letter `T` as a time separator, 2-digit hour, 2-digit minute, 2-digit second, 4-digit millisecond, and the letter `Z` as the UTC indicator).</span></span> <span data-ttu-id="ce12e-231">Beispiel: 20190627t1540500718z.</span><span class="sxs-lookup"><span data-stu-id="ce12e-231">For example: 20190627T1540500718Z.</span></span>

```yaml
Type: System.String
Parameter Sets: DateAndFormat, UnixTimeSecondsAndFormat
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ce12e-232">-Stunde</span><span class="sxs-lookup"><span data-stu-id="ce12e-232">-Hour</span></span>

<span data-ttu-id="ce12e-233">Gibt die angezeigte Stunde an.</span><span class="sxs-lookup"><span data-stu-id="ce12e-233">Specifies the hour that is displayed.</span></span> <span data-ttu-id="ce12e-234">Geben Sie einen Wert zwischen 0 und 23 ein.</span><span class="sxs-lookup"><span data-stu-id="ce12e-234">Enter a value from 0 to 23.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ce12e-235">-Millisekunde</span><span class="sxs-lookup"><span data-stu-id="ce12e-235">-Millisecond</span></span>

<span data-ttu-id="ce12e-236">Gibt die Millisekunden im Datum an.</span><span class="sxs-lookup"><span data-stu-id="ce12e-236">Specifies the milliseconds in the date.</span></span> <span data-ttu-id="ce12e-237">Geben Sie einen Wert zwischen 0 und 999 ein.</span><span class="sxs-lookup"><span data-stu-id="ce12e-237">Enter a value from 0 to 999.</span></span>

<span data-ttu-id="ce12e-238">Dieser Parameter wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="ce12e-238">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ce12e-239">-Minute</span><span class="sxs-lookup"><span data-stu-id="ce12e-239">-Minute</span></span>

<span data-ttu-id="ce12e-240">Gibt die angezeigte Minute an.</span><span class="sxs-lookup"><span data-stu-id="ce12e-240">Specifies the minute that is displayed.</span></span> <span data-ttu-id="ce12e-241">Geben Sie einen Wert zwischen 0 und 59 ein.</span><span class="sxs-lookup"><span data-stu-id="ce12e-241">Enter a value from 0 to 59.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ce12e-242">-Monat</span><span class="sxs-lookup"><span data-stu-id="ce12e-242">-Month</span></span>

<span data-ttu-id="ce12e-243">Gibt den angezeigten Monat an.</span><span class="sxs-lookup"><span data-stu-id="ce12e-243">Specifies the month that is displayed.</span></span> <span data-ttu-id="ce12e-244">Geben Sie einen Wert zwischen 1 und 12 ein.</span><span class="sxs-lookup"><span data-stu-id="ce12e-244">Enter a value from 1 to 12.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ce12e-245">-Sekunde</span><span class="sxs-lookup"><span data-stu-id="ce12e-245">-Second</span></span>

<span data-ttu-id="ce12e-246">Gibt die angezeigte Sekunde an.</span><span class="sxs-lookup"><span data-stu-id="ce12e-246">Specifies the second that is displayed.</span></span> <span data-ttu-id="ce12e-247">Geben Sie einen Wert zwischen 0 und 59 ein.</span><span class="sxs-lookup"><span data-stu-id="ce12e-247">Enter a value from 0 to 59.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ce12e-248">-Uformat</span><span class="sxs-lookup"><span data-stu-id="ce12e-248">-UFormat</span></span>

<span data-ttu-id="ce12e-249">Zeigt das Datum und die Uhrzeit im UNIX-Format an.</span><span class="sxs-lookup"><span data-stu-id="ce12e-249">Displays the date and time in UNIX format.</span></span> <span data-ttu-id="ce12e-250">Der **Uformat** -Parameter gibt ein String-Objekt aus.</span><span class="sxs-lookup"><span data-stu-id="ce12e-250">The **UFormat** parameter outputs a string object.</span></span>

<span data-ttu-id="ce12e-251">Den **Uformat** -Spezifizierer wird ein Prozentzeichen ( `%` ) vorangestellt, z `%m` . b., `%d` und `%Y` .</span><span class="sxs-lookup"><span data-stu-id="ce12e-251">**UFormat** specifiers are preceded by a percent sign (`%`), for example, `%m`, `%d`, and `%Y`.</span></span> <span data-ttu-id="ce12e-252">Der Abschnitt [Notes](#notes) enthält eine Tabelle gültiger **Uformat-Spezifizierer**.</span><span class="sxs-lookup"><span data-stu-id="ce12e-252">The [Notes](#notes) section contains a table of valid **UFormat specifiers**.</span></span>

<span data-ttu-id="ce12e-253">Wenn der **Uformat** -Parameter verwendet wird, ruft `Get-Date` nur die Eigenschaften des **DateTime** -Objekts ab, die zum Anzeigen des Datums erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="ce12e-253">When the **UFormat** parameter is used, `Get-Date` only gets the **DateTime** object's properties necessary to display the date.</span></span> <span data-ttu-id="ce12e-254">Folglich stehen einige der Eigenschaften und Methoden der **DateTime**-Objekte möglicherweise nicht zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="ce12e-254">As a result, some of the properties and methods of **DateTime** objects might not be available.</span></span>

```yaml
Type: System.String
Parameter Sets: DateAndUFormat, UnixTimeSecondsAndUFormat
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ce12e-255">-Unixtimeseconds</span><span class="sxs-lookup"><span data-stu-id="ce12e-255">-UnixTimeSeconds</span></span>

<span data-ttu-id="ce12e-256">Datums-und Uhrzeitangabe in Sekunden seit dem 1. Januar 1970, 0:00:00.</span><span class="sxs-lookup"><span data-stu-id="ce12e-256">Date and time represented in seconds since January 1, 1970, 0:00:00.</span></span>

<span data-ttu-id="ce12e-257">Dieser Parameter wurde in PowerShell 7,1 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="ce12e-257">This parameter was introduced in PowerShell 7.1.</span></span>

```yaml
Type: System.Int64
Parameter Sets: UnixTimeSecondsAndFormat, UnixTimeSecondsAndUFormat
Aliases: UnixTime

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ce12e-258">-Jahr</span><span class="sxs-lookup"><span data-stu-id="ce12e-258">-Year</span></span>

<span data-ttu-id="ce12e-259">Gibt das angezeigte Jahr an.</span><span class="sxs-lookup"><span data-stu-id="ce12e-259">Specifies the year that is displayed.</span></span> <span data-ttu-id="ce12e-260">Geben Sie einen Wert zwischen 1 und 9999 ein.</span><span class="sxs-lookup"><span data-stu-id="ce12e-260">Enter a value from 1 to 9999.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ce12e-261">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="ce12e-261">CommonParameters</span></span>

<span data-ttu-id="ce12e-262">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="ce12e-262">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ce12e-263">Weitere Informationen findest du unter [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="ce12e-263">For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ce12e-264">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="ce12e-264">INPUTS</span></span>

### <span data-ttu-id="ce12e-265">Pipeline Eingabe</span><span class="sxs-lookup"><span data-stu-id="ce12e-265">Pipeline input</span></span>

<span data-ttu-id="ce12e-266">`Get-Date` akzeptiert Pipeline Eingaben.</span><span class="sxs-lookup"><span data-stu-id="ce12e-266">`Get-Date` accepts pipeline input.</span></span> <span data-ttu-id="ce12e-267">Beispiel: `Get-ChildItem | Get-Date`.</span><span class="sxs-lookup"><span data-stu-id="ce12e-267">For example, `Get-ChildItem | Get-Date`.</span></span>

## <span data-ttu-id="ce12e-268">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="ce12e-268">OUTPUTS</span></span>

### <span data-ttu-id="ce12e-269">System. DateTime oder System. String</span><span class="sxs-lookup"><span data-stu-id="ce12e-269">System.DateTime or System.String</span></span>

<span data-ttu-id="ce12e-270">`Get-Date` Gibt ein **DateTime** -Objekt zurück, außer wenn das **Format** und die **Uformat** -Parameter verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ce12e-270">`Get-Date` returns a **DateTime** object except when the **Format** and **UFormat** parameters are used.</span></span> <span data-ttu-id="ce12e-271">Die **Format** -oder **Uformat** -Parameter geben **Zeichen** folgen Objekte zurück.</span><span class="sxs-lookup"><span data-stu-id="ce12e-271">The **Format** or **UFormat** parameters return **String** objects.</span></span>

<span data-ttu-id="ce12e-272">Wenn ein **DateTime** -Objekt über die Pipeline an ein Cmdlet gesendet wird, z `Add-Content` . b., das Zeichen folgen Eingaben erwartet, konvertiert PowerShell das Objekt in ein **Zeichen** folgen Objekt.</span><span class="sxs-lookup"><span data-stu-id="ce12e-272">When a **DateTime** object is sent down the pipeline to a cmdlet such as `Add-Content` that expects string input, PowerShell converts the object to a **String** object.</span></span>

<span data-ttu-id="ce12e-273">Die-Methode `(Get-Date).ToString()` konvertiert ein **DateTime** -Objekt in ein **String** -Objekt.</span><span class="sxs-lookup"><span data-stu-id="ce12e-273">The method `(Get-Date).ToString()` converts a **DateTime** object a **String** object.</span></span>

<span data-ttu-id="ce12e-274">Um die Eigenschaften und Methoden eines Objekts anzuzeigen, senden Sie das Objekt über die Pipeline an `Get-Member` .</span><span class="sxs-lookup"><span data-stu-id="ce12e-274">To display an object's properties and methods, send the object down the pipeline to `Get-Member`.</span></span>
<span data-ttu-id="ce12e-275">Beispiel: `Get-Date | Get-Member`.</span><span class="sxs-lookup"><span data-stu-id="ce12e-275">For example, `Get-Date | Get-Member`.</span></span>

## <span data-ttu-id="ce12e-276">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="ce12e-276">NOTES</span></span>

<span data-ttu-id="ce12e-277">**DateTime** -Objekte liegen in langen Datums-und lang Zeitformaten für das System Gebiets Schema vor.</span><span class="sxs-lookup"><span data-stu-id="ce12e-277">**DateTime** objects are in long-date and long-time formats for the system locale.</span></span>

<span data-ttu-id="ce12e-278">In der folgenden Tabelle werden die gültigen **Uformat-Spezifizierer** angezeigt:</span><span class="sxs-lookup"><span data-stu-id="ce12e-278">The valid **UFormat specifiers** are displayed in the following table:</span></span>

| <span data-ttu-id="ce12e-279">Formatbezeichner</span><span class="sxs-lookup"><span data-stu-id="ce12e-279">Format specifier</span></span> |                                 <span data-ttu-id="ce12e-280">Bedeutung</span><span class="sxs-lookup"><span data-stu-id="ce12e-280">Meaning</span></span>                     |         <span data-ttu-id="ce12e-281">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ce12e-281">Example</span></span>          |
| ---- | ----------------------------------------------------------------------- | ------------------------ |
| `%A` | <span data-ttu-id="ce12e-282">Wochentag-vollständiger Name</span><span class="sxs-lookup"><span data-stu-id="ce12e-282">Day of the week - full name</span></span>                                             | <span data-ttu-id="ce12e-283">Montag</span><span class="sxs-lookup"><span data-stu-id="ce12e-283">Monday</span></span>                   |
| `%a` | <span data-ttu-id="ce12e-284">Wochentag-abgekürzte Name</span><span class="sxs-lookup"><span data-stu-id="ce12e-284">Day of the week - abbreviated name</span></span>                                      | <span data-ttu-id="ce12e-285">Mon</span><span class="sxs-lookup"><span data-stu-id="ce12e-285">Mon</span></span>                      |
| `%B` | <span data-ttu-id="ce12e-286">Monats Name-vollständig</span><span class="sxs-lookup"><span data-stu-id="ce12e-286">Month name - full</span></span>                                                       | <span data-ttu-id="ce12e-287">January</span><span class="sxs-lookup"><span data-stu-id="ce12e-287">January</span></span>                  |
| `%b` | <span data-ttu-id="ce12e-288">Monats Name-gekürzt</span><span class="sxs-lookup"><span data-stu-id="ce12e-288">Month name - abbreviated</span></span>                                                | <span data-ttu-id="ce12e-289">Jan</span><span class="sxs-lookup"><span data-stu-id="ce12e-289">Jan</span></span>                      |
| `%C` | <span data-ttu-id="ce12e-290">Lang</span><span class="sxs-lookup"><span data-stu-id="ce12e-290">Century</span></span>                                                                 | <span data-ttu-id="ce12e-291">20 für 2019</span><span class="sxs-lookup"><span data-stu-id="ce12e-291">20 for 2019</span></span>              |
| `%c` | <span data-ttu-id="ce12e-292">Datum und Uhrzeit-gekürzt</span><span class="sxs-lookup"><span data-stu-id="ce12e-292">Date and time - abbreviated</span></span>                                             | <span data-ttu-id="ce12e-293">Do Jun 27 08:44:18 2019</span><span class="sxs-lookup"><span data-stu-id="ce12e-293">Thu Jun 27 08:44:18 2019</span></span> |
| `%D` | <span data-ttu-id="ce12e-294">Datum im Format mm/dd/yy</span><span class="sxs-lookup"><span data-stu-id="ce12e-294">Date in mm/dd/yy format</span></span>                                                 | <span data-ttu-id="ce12e-295">06/27/19</span><span class="sxs-lookup"><span data-stu-id="ce12e-295">06/27/19</span></span>                 |
| `%d` | <span data-ttu-id="ce12e-296">Tag des Monats-2 Ziffern</span><span class="sxs-lookup"><span data-stu-id="ce12e-296">Day of the month - 2 digits</span></span>                                             | <span data-ttu-id="ce12e-297">05</span><span class="sxs-lookup"><span data-stu-id="ce12e-297">05</span></span>                       |
| `%e` | <span data-ttu-id="ce12e-298">Tag des Monats, dem ein Leerzeichen vorangestellt ist, wenn nur eine einzelne Ziffer</span><span class="sxs-lookup"><span data-stu-id="ce12e-298">Day of the month - preceded by a space if only a single digit</span></span>           | <span data-ttu-id="ce12e-299">\<space\>5@@</span><span class="sxs-lookup"><span data-stu-id="ce12e-299">\<space\>5</span></span>               |
| `%F` | <span data-ttu-id="ce12e-300">Datum im Format yyyy-mm-dd, gleich% Y-% m-% d (ISO 8601-Datumsformat)</span><span class="sxs-lookup"><span data-stu-id="ce12e-300">Date in YYYY-mm-dd format, equal to %Y-%m-%d (the ISO 8601 date format)</span></span> | <span data-ttu-id="ce12e-301">2019-06-27</span><span class="sxs-lookup"><span data-stu-id="ce12e-301">2019-06-27</span></span>               |
| `%G` | <span data-ttu-id="ce12e-302">Identisch mit "Y"</span><span class="sxs-lookup"><span data-stu-id="ce12e-302">Same as 'Y'</span></span>                                                             |                          |
| `%g` | <span data-ttu-id="ce12e-303">Identisch mit "y"</span><span class="sxs-lookup"><span data-stu-id="ce12e-303">Same as 'y'</span></span>                                                             |                          |
| `%H` | <span data-ttu-id="ce12e-304">Stunde im 24-Stunden-Format</span><span class="sxs-lookup"><span data-stu-id="ce12e-304">Hour in 24-hour format</span></span>                                                  | <span data-ttu-id="ce12e-305">17</span><span class="sxs-lookup"><span data-stu-id="ce12e-305">17</span></span>                       |
| `%h` | <span data-ttu-id="ce12e-306">Identisch mit "b"</span><span class="sxs-lookup"><span data-stu-id="ce12e-306">Same as 'b'</span></span>                                                             |                          |
| `%I` | <span data-ttu-id="ce12e-307">Stunde im 12-Stunden-Format</span><span class="sxs-lookup"><span data-stu-id="ce12e-307">Hour in 12-hour format</span></span>                                                  | <span data-ttu-id="ce12e-308">05</span><span class="sxs-lookup"><span data-stu-id="ce12e-308">05</span></span>                       |
| `%j` | <span data-ttu-id="ce12e-309">Tag des Jahres</span><span class="sxs-lookup"><span data-stu-id="ce12e-309">Day of the year</span></span>                                                         | <span data-ttu-id="ce12e-310">1-366</span><span class="sxs-lookup"><span data-stu-id="ce12e-310">1-366</span></span>                    |
| `%k` | <span data-ttu-id="ce12e-311">Identisch mit "H"</span><span class="sxs-lookup"><span data-stu-id="ce12e-311">Same as 'H'</span></span>                                                             |                          |
| `%l` | <span data-ttu-id="ce12e-312">Identisch mit "i" (i-Großbuchstaben)</span><span class="sxs-lookup"><span data-stu-id="ce12e-312">Same as 'I' (Upper-case I)</span></span>                                              | <span data-ttu-id="ce12e-313">05</span><span class="sxs-lookup"><span data-stu-id="ce12e-313">05</span></span>                       |
| `%M` | <span data-ttu-id="ce12e-314">Minuten</span><span class="sxs-lookup"><span data-stu-id="ce12e-314">Minutes</span></span>                                                                 | <span data-ttu-id="ce12e-315">35</span><span class="sxs-lookup"><span data-stu-id="ce12e-315">35</span></span>                       |
| `%m` | <span data-ttu-id="ce12e-316">Monatsnummer</span><span class="sxs-lookup"><span data-stu-id="ce12e-316">Month number</span></span>                                                            | <span data-ttu-id="ce12e-317">06</span><span class="sxs-lookup"><span data-stu-id="ce12e-317">06</span></span>                       |
| `%n` | <span data-ttu-id="ce12e-318">Zeilen Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="ce12e-318">newline character</span></span>                                                       |                          |
| `%p` | <span data-ttu-id="ce12e-319">AM oder PM</span><span class="sxs-lookup"><span data-stu-id="ce12e-319">AM or PM</span></span>                                                                |                          |
| `%R` | <span data-ttu-id="ce12e-320">Uhrzeit im 24-Stunden-Format-keine Sekunden</span><span class="sxs-lookup"><span data-stu-id="ce12e-320">Time in 24-hour format -no seconds</span></span>                                      | <span data-ttu-id="ce12e-321">17:45</span><span class="sxs-lookup"><span data-stu-id="ce12e-321">17:45</span></span>                    |
| `%r` | <span data-ttu-id="ce12e-322">Uhrzeit im 12-Stunden-Format</span><span class="sxs-lookup"><span data-stu-id="ce12e-322">Time in 12-hour format</span></span>                                                  | <span data-ttu-id="ce12e-323">09:15:36 Uhr</span><span class="sxs-lookup"><span data-stu-id="ce12e-323">09:15:36 AM</span></span>              |
| `%S` | <span data-ttu-id="ce12e-324">Sekunden</span><span class="sxs-lookup"><span data-stu-id="ce12e-324">Seconds</span></span>                                                                 | <span data-ttu-id="ce12e-325">05</span><span class="sxs-lookup"><span data-stu-id="ce12e-325">05</span></span>                       |
| `%s` | <span data-ttu-id="ce12e-326">Seit dem 1. Januar 1970 00:00:00 Verstrichene Sekunden</span><span class="sxs-lookup"><span data-stu-id="ce12e-326">Seconds elapsed since January 1, 1970 00:00:00</span></span>                          | <span data-ttu-id="ce12e-327">1150451174</span><span class="sxs-lookup"><span data-stu-id="ce12e-327">1150451174</span></span>               |
| `%t` | <span data-ttu-id="ce12e-328">Horizontales Tabstopp Zeichen</span><span class="sxs-lookup"><span data-stu-id="ce12e-328">Horizontal tab character</span></span>                                                |                          |
| `%T` | <span data-ttu-id="ce12e-329">Uhrzeit im 24-Stunden-Format</span><span class="sxs-lookup"><span data-stu-id="ce12e-329">Time in 24-hour format</span></span>                                                  | <span data-ttu-id="ce12e-330">17:45:52</span><span class="sxs-lookup"><span data-stu-id="ce12e-330">17:45:52</span></span>                 |
| `%U` | <span data-ttu-id="ce12e-331">Identisch mit "W"</span><span class="sxs-lookup"><span data-stu-id="ce12e-331">Same as 'W'</span></span>                                                             |                          |
| `%u` | <span data-ttu-id="ce12e-332">Numerischer Tag der Woche (1-7)</span><span class="sxs-lookup"><span data-stu-id="ce12e-332">Numeric day of the week (1-7)</span></span>                                           | <span data-ttu-id="ce12e-333">Montag = 1, Sonntag = 7</span><span class="sxs-lookup"><span data-stu-id="ce12e-333">Monday = 1, Sunday = 7</span></span>   |
| `%V` | <span data-ttu-id="ce12e-334">Woche des Jahres</span><span class="sxs-lookup"><span data-stu-id="ce12e-334">Week of the year</span></span>                                                        | <span data-ttu-id="ce12e-335">01-53</span><span class="sxs-lookup"><span data-stu-id="ce12e-335">01-53</span></span>                    |
| `%w` | <span data-ttu-id="ce12e-336">Numerischer Tag der Woche (0-6)</span><span class="sxs-lookup"><span data-stu-id="ce12e-336">Numeric day of the week (0-6)</span></span>                                           | <span data-ttu-id="ce12e-337">Sonntag = 0, Samstag = 6</span><span class="sxs-lookup"><span data-stu-id="ce12e-337">Sunday = 0, Saturday = 6</span></span> |
| `%W` | <span data-ttu-id="ce12e-338">Woche des Jahres</span><span class="sxs-lookup"><span data-stu-id="ce12e-338">Week of the year</span></span>                                                        | <span data-ttu-id="ce12e-339">00-52</span><span class="sxs-lookup"><span data-stu-id="ce12e-339">00-52</span></span>                    |
| `%X` | <span data-ttu-id="ce12e-340">Identisch mit "'t"</span><span class="sxs-lookup"><span data-stu-id="ce12e-340">Same as 'T'</span></span>                                                             |                          |
| `%x` | <span data-ttu-id="ce12e-341">Datum im Standardformat für das Gebiets Schema</span><span class="sxs-lookup"><span data-stu-id="ce12e-341">Date in standard format for locale</span></span>                                      | <span data-ttu-id="ce12e-342">06/27/19 für Englisch-US</span><span class="sxs-lookup"><span data-stu-id="ce12e-342">06/27/19 for English-US</span></span>  |
| `%Y` | <span data-ttu-id="ce12e-343">Jahr im vierstelligen Format</span><span class="sxs-lookup"><span data-stu-id="ce12e-343">Year in 4-digit format</span></span>                                                  | <span data-ttu-id="ce12e-344">2019</span><span class="sxs-lookup"><span data-stu-id="ce12e-344">2019</span></span>                     |
| `%y` | <span data-ttu-id="ce12e-345">Jahr im zweistelligen Format</span><span class="sxs-lookup"><span data-stu-id="ce12e-345">Year in 2-digit format</span></span>                                                  | <span data-ttu-id="ce12e-346">19</span><span class="sxs-lookup"><span data-stu-id="ce12e-346">19</span></span>                       |
| `%Z` | <span data-ttu-id="ce12e-347">Zeit Zonen Offset von universeller Zeit Koordinate (UTC)</span><span class="sxs-lookup"><span data-stu-id="ce12e-347">Time zone offset from Universal Time Coordinate (UTC)</span></span>                   | <span data-ttu-id="ce12e-348">-07</span><span class="sxs-lookup"><span data-stu-id="ce12e-348">-07</span></span>                      |

## <span data-ttu-id="ce12e-349">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="ce12e-349">RELATED LINKS</span></span>

[<span data-ttu-id="ce12e-350">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="ce12e-350">ForEach-Object</span></span>](../Microsoft.PowerShell.Core/ForEach-Object.md)

[<span data-ttu-id="ce12e-351">Get-Culture</span><span class="sxs-lookup"><span data-stu-id="ce12e-351">Get-Culture</span></span>](Get-Culture.md)

[<span data-ttu-id="ce12e-352">Get-Member</span><span class="sxs-lookup"><span data-stu-id="ce12e-352">Get-Member</span></span>](Get-Member.md)

[<span data-ttu-id="ce12e-353">New-Item</span><span class="sxs-lookup"><span data-stu-id="ce12e-353">New-Item</span></span>](../Microsoft.PowerShell.Management/New-Item.md)

[<span data-ttu-id="ce12e-354">New-TimeSpan</span><span class="sxs-lookup"><span data-stu-id="ce12e-354">New-TimeSpan</span></span>](New-TimeSpan.md)

[<span data-ttu-id="ce12e-355">Set-Date</span><span class="sxs-lookup"><span data-stu-id="ce12e-355">Set-Date</span></span>](Set-Date.md)
