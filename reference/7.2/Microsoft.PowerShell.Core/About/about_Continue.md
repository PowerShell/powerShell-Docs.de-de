---
description: Beschreibt, wie die- `continue` Anweisung den Programmablauf sofort an den Anfang einer Programm Schleife, einer- `switch` Anweisung oder einer-Anweisung zurückgibt `trap` .
Locale: en-US
ms.date: 06/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_continue?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Continue
ms.openlocfilehash: 618ebee65d0407751e443fd957ab008d35c5375b
ms.sourcegitcommit: 71173a89c4f05b5283ccd1e885a780773c13fa47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2021
ms.locfileid: "103195610"
---
# <a name="about-continue"></a><span data-ttu-id="20613-103">Informationen zum Fortfahren</span><span class="sxs-lookup"><span data-stu-id="20613-103">About Continue</span></span>

## <a name="short-description"></a><span data-ttu-id="20613-104">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="20613-104">Short description</span></span>

<span data-ttu-id="20613-105">Beschreibt, wie die- `continue` Anweisung den Programmablauf sofort an den Anfang einer Programm Schleife, einer- `switch` Anweisung oder einer-Anweisung zurückgibt `trap` .</span><span class="sxs-lookup"><span data-stu-id="20613-105">Describes how the `continue` statement immediately returns the program flow to the top of a program loop, a `switch` statement, or a `trap` statement.</span></span>

## <a name="long-description"></a><span data-ttu-id="20613-106">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="20613-106">Long description</span></span>

<span data-ttu-id="20613-107">Die- `continue` Anweisung bietet eine Möglichkeit, den aktuellen Kontroll Block zu beenden und die Ausführung fortzusetzen, anstatt vollständig zu beenden.</span><span class="sxs-lookup"><span data-stu-id="20613-107">The `continue` statement provides a way to exit the current control block but continue execution, rather than exit completely.</span></span> <span data-ttu-id="20613-108">Die-Anweisung unterstützt Bezeichnungen.</span><span class="sxs-lookup"><span data-stu-id="20613-108">The statement supports labels.</span></span>
<span data-ttu-id="20613-109">Eine Bezeichnung ist ein Name, den Sie einer Anweisung in einem Skript zuweisen.</span><span class="sxs-lookup"><span data-stu-id="20613-109">A label is a name you assign to a statement in a script.</span></span>

## <a name="using-continue-in-loops"></a><span data-ttu-id="20613-110">Verwenden von Continue in Schleifen</span><span class="sxs-lookup"><span data-stu-id="20613-110">Using continue in loops</span></span>

<span data-ttu-id="20613-111">Eine unbezeichnete `continue` Anweisung gibt den Programmfluss sofort an den Anfang der innersten Schleife zurück, der von einer-,-,-oder-Anweisung gesteuert wird `for` `foreach` `do` `while` .</span><span class="sxs-lookup"><span data-stu-id="20613-111">An unlabeled `continue` statement immediately returns the program flow to the top of the innermost loop that is controlled by a `for`, `foreach`, `do`, or `while` statement.</span></span> <span data-ttu-id="20613-112">Die aktuelle Iterations Schleife wird beendet, und die Schleife wird mit der nächsten Iterations Phase fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="20613-112">The current iteration of the loop is terminated and the loop continues with the next iteration.</span></span>

<span data-ttu-id="20613-113">Im folgenden Beispiel kehrt der Programmfluss an den Anfang der Schleife zurück, `while` Wenn die `$ctr` Variable gleich 5 ist.</span><span class="sxs-lookup"><span data-stu-id="20613-113">In the following example, program flow returns to the top of the `while` loop if the `$ctr` variable is equal to 5.</span></span> <span data-ttu-id="20613-114">Folglich werden alle Zahlen zwischen 1 und 10 mit Ausnahme von 5 angezeigt:</span><span class="sxs-lookup"><span data-stu-id="20613-114">As a result, all the numbers between 1 and 10 are displayed except for 5:</span></span>

```powershell
while ($ctr -lt 10)
{
    $ctr += 1
    if ($ctr -eq 5)
    {
        continue
    }

    Write-Host -Object $ctr
}
```

<span data-ttu-id="20613-115">Bei Verwendung einer- `for` Schleife wird die Ausführung bei der Anweisung fortgesetzt `<Repeat>` , gefolgt vom `<Condition>` Test.</span><span class="sxs-lookup"><span data-stu-id="20613-115">When using a `for` loop, execution continues at the `<Repeat>` statement, followed by the `<Condition>` test.</span></span> <span data-ttu-id="20613-116">Im folgenden Beispiel kommt es nicht zu einer Endlosschleife, da der Dekrement von `$i` nach dem- `continue` Schlüsselwort auftritt.</span><span class="sxs-lookup"><span data-stu-id="20613-116">In the example below, an infinite loop will not occur because the decrement of `$i` occurs after the `continue` keyword.</span></span>

```powershell
#   <Init>  <Condition> <Repeat>
for ($i = 0; $i -lt 10; $i++)
{
    Write-Host -Object $i
    if ($i -eq 5)
    {
        continue
        # Will not result in an infinite loop.
        $i--
    }
}
```

### <a name="using-a-labeled-continue-in-a-loop"></a><span data-ttu-id="20613-117">Verwenden eines gekennzeichneten Continue in einer Schleife</span><span class="sxs-lookup"><span data-stu-id="20613-117">Using a labeled continue in a loop</span></span>

<span data-ttu-id="20613-118">Eine bezeichnete `continue` Anweisung beendet die Ausführung der Iterationen und überträgt die Steuerung an die zielschließende einschließende Iterations-oder `switch` Anweisungsbezeichnung.</span><span class="sxs-lookup"><span data-stu-id="20613-118">A labeled `continue` statement terminates execution of the iteration and transfers control to the targeted enclosing iteration or `switch` statement label.</span></span>

<span data-ttu-id="20613-119">Im folgenden Beispiel wird die innerste beendet, wenn den Wert `for` `$condition` **true** hat und die Iterationen mit der zweiten Schleife bei fortgesetzt werden `for` `labelB` .</span><span class="sxs-lookup"><span data-stu-id="20613-119">In the following example, the innermost `for` is terminated when `$condition` is **True** and iteration continues with the second `for` loop at `labelB`.</span></span>

```powershell
:labelA for ($i = 1; $i -le 10; $i++) {
    :labelB for ($j = 1; $j -le 10; $j++) {
        :labelC for ($k = 1; $k -le 10; $k++) {
            if ($condition) {
                continue labelB
            } else {
                $condition = Update-Condition
            }
        }
    }
}
```

## <a name="using-continue-in-a-switch-statement"></a><span data-ttu-id="20613-120">Verwenden von Continue in einer Switch-Anweisung</span><span class="sxs-lookup"><span data-stu-id="20613-120">Using continue in a switch statement</span></span>

<span data-ttu-id="20613-121">Eine unbezeichnete `continue` Anweisung in der `switch` beendet die Ausführung der aktuellen `switch` Iterationen und überträgt die Steuerung an den Anfang des `switch` , um das nächste Eingabe Element zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="20613-121">An unlabeled `continue` statement within a `switch` terminates execution of the current `switch` iteration and transfers control to the top of the `switch` to get the next input item.</span></span>

<span data-ttu-id="20613-122">Wenn ein einzelnes Eingabe Element vorhanden ist, wird `continue` die gesamte- `switch` Anweisung beendet.</span><span class="sxs-lookup"><span data-stu-id="20613-122">When there is a single input item `continue` exits the entire `switch` statement.</span></span>
<span data-ttu-id="20613-123">Wenn `switch` es sich bei der Eingabe um eine Auflistung handelt, `switch` testet jedes Element der Auflistung.</span><span class="sxs-lookup"><span data-stu-id="20613-123">When the `switch` input is a collection, the `switch` tests each element of the collection.</span></span> <span data-ttu-id="20613-124">Der `continue` beendet die aktuelle Iterations-und `switch` setzt mit dem nächsten Element fort.</span><span class="sxs-lookup"><span data-stu-id="20613-124">The `continue` exits the current iteration and the `switch` continues with the next element.</span></span>

```powershell
switch (1,2,3) {
  2 { continue }  # moves on to the next element, 3
  default { $_ }
}
```

```Output
1
3
```

## <a name="using-continue-in-a-trap-statement"></a><span data-ttu-id="20613-125">Verwenden von Continue in einer Trap-Anweisung</span><span class="sxs-lookup"><span data-stu-id="20613-125">Using continue in a trap statement</span></span>

<span data-ttu-id="20613-126">Wenn die letzte im Text einer-Anweisung ausgeführte Anweisung `trap` ist `continue` , wird der aufgefangenen Fehler automatisch ignoriert, und die Ausführung wird mit der-Anweisung fortgesetzt, die den Fehler verursacht hat `trap` .</span><span class="sxs-lookup"><span data-stu-id="20613-126">If the final statement executed in the body a `trap` statement is `continue`, the trapped error is silently ignored and execution continues with the statement immediately following the one that caused `trap` to occur.</span></span>

## <a name="do-not-use-continue-outside-of-a-loop-switch-or-trap"></a><span data-ttu-id="20613-127">Nicht weiter außerhalb einer Schleife, eines Schalters oder eines Trap verwenden</span><span class="sxs-lookup"><span data-stu-id="20613-127">Do not use continue outside of a loop, switch, or trap</span></span>

<span data-ttu-id="20613-128">Wenn `continue` außerhalb eines Konstrukts verwendet wird, das es direkt unterstützt (Schleifen, `switch` , `trap` ), sucht PowerShell _die-aufrufsstapel_ nach einem einschließenden Konstrukt.</span><span class="sxs-lookup"><span data-stu-id="20613-128">When `continue` is used outside of a construct that directly supports it (loops, `switch`, `trap`), PowerShell looks _up the call stack_ for an enclosing construct.</span></span> <span data-ttu-id="20613-129">Wenn kein einschließendes Konstrukt gefunden werden kann, wird der aktuelle Runspace ruhig beendet.</span><span class="sxs-lookup"><span data-stu-id="20613-129">If it can't find an enclosing construct, the current runspace is quietly terminated.</span></span>

<span data-ttu-id="20613-130">Dies bedeutet, dass Funktionen und Skripts, die versehentlich einen `continue` außerhalb eines einschließenden Konstrukts verwenden, das es unter stützt, ihre Aufrufer versehentlich beenden können.</span><span class="sxs-lookup"><span data-stu-id="20613-130">This means that functions and scripts that inadvertently use a `continue` outside of an enclosing construct that supports it, can inadvertently terminate their _callers_.</span></span>

<span data-ttu-id="20613-131">Durch die Verwendung von `continue` in einer Pipeline, wie z. b. einem `ForEach-Object` Skriptblock, wird die Pipeline nicht nur beendet, sondern der gesamte Runspace wird möglicherweise beendet.</span><span class="sxs-lookup"><span data-stu-id="20613-131">Using `continue` inside a pipeline, such as a `ForEach-Object` script block, not only exits the pipeline, it potentially terminates the entire runspace.</span></span>

## <a name="see-also"></a><span data-ttu-id="20613-132">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="20613-132">See also</span></span>

[<span data-ttu-id="20613-133">about_Break</span><span class="sxs-lookup"><span data-stu-id="20613-133">about_Break</span></span>](about_Break.md)

[<span data-ttu-id="20613-134">about_For</span><span class="sxs-lookup"><span data-stu-id="20613-134">about_For</span></span>](about_For.md)

[<span data-ttu-id="20613-135">about_Comparison_Operators</span><span class="sxs-lookup"><span data-stu-id="20613-135">about_Comparison_Operators</span></span>](about_Comparison_Operators.md)

[<span data-ttu-id="20613-136">about_Throw</span><span class="sxs-lookup"><span data-stu-id="20613-136">about_Throw</span></span>](about_Throw.md)

[<span data-ttu-id="20613-137">about_Trap</span><span class="sxs-lookup"><span data-stu-id="20613-137">about_Trap</span></span>](about_Trap.md)

[<span data-ttu-id="20613-138">about_Try_Catch_Finally</span><span class="sxs-lookup"><span data-stu-id="20613-138">about_Try_Catch_Finally</span></span>](about_Try_Catch_Finally.md)
