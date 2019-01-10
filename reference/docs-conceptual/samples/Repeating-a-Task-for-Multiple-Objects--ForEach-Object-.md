---
ms.date: 06/05/2017
keywords: powershell,cmdlet
title: Wiederholen einer Aufgabe für mehrere Objekte
ms.assetid: 6697a12d-2470-4ed6-b5bb-c35e5d525eb6
ms.openlocfilehash: 64d85edad4a6931b2376b95b6d1f5b4d5194399f
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MTE95
ms.contentlocale: de-DE
ms.lasthandoff: 12/14/2018
ms.locfileid: "53402001"
---
# <a name="repeating-a-task-for-multiple-objects-foreach-object"></a><span data-ttu-id="d2d03-103">Wiederholen einer Aufgabe für mehrere Objekte (ForEach-Object)</span><span class="sxs-lookup"><span data-stu-id="d2d03-103">Repeating a Task for Multiple Objects (ForEach-Object)</span></span>

<span data-ttu-id="d2d03-104">Das Cmdlet **ForEach-Object** verwendet Skriptblöcke und den Deskriptor `$_` für das aktuelle Pipelineobjekt, um Ihnen das Ausführen eines Befehls für jedes Objekt in der Pipeline zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="d2d03-104">The **ForEach-Object** cmdlet uses script blocks and the `$_` descriptor for the current pipeline object to let you run a command on each object in the pipeline.</span></span> <span data-ttu-id="d2d03-105">Damit können Sie einige komplizierte Aufgaben ausführen.</span><span class="sxs-lookup"><span data-stu-id="d2d03-105">This can be used to perform some complicated tasks.</span></span>

<span data-ttu-id="d2d03-106">Besonders nützlich kann dies sein, wenn Sie Daten bearbeiten möchten, um sie besser nutzen zu können.</span><span class="sxs-lookup"><span data-stu-id="d2d03-106">One situation where this can be useful is manipulating data to make it more useful.</span></span> <span data-ttu-id="d2d03-107">Beispielsweise kann die Klasse „Win32_LogicalDisk“ aus WMI verwendet werden, um für jeden lokalen Datenträger Informationen zum freien Speicherplatz zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="d2d03-107">For example, the Win32_LogicalDisk class from WMI can be used to return free space information for each local disk.</span></span> <span data-ttu-id="d2d03-108">Die Daten werden als Bytes zurückgegeben, sind daher schwierig zu lesen:</span><span class="sxs-lookup"><span data-stu-id="d2d03-108">The data is returned in terms of bytes, however, which makes it difficult to read:</span></span>

```
PS> Get-WmiObject -Class Win32_LogicalDisk

DeviceID     : C:
DriveType    : 3
ProviderName :
FreeSpace    : 50665070592
Size         : 203912880128
VolumeName   : Local Disk
```

<span data-ttu-id="d2d03-109">Sie können den Wert von „FreeSpace in MB konvertieren, indem Sie jeden Wert zweimal durch 1024 dividieren. Mit der ersten Division werden die Daten in KB umgerechnet, bei der zweiten in MB.</span><span class="sxs-lookup"><span data-stu-id="d2d03-109">We can convert the FreeSpace value to megabytes by dividing each value by 1024 twice; after the first division, the data is in kilobytes, and after the second division it is megabytes.</span></span> <span data-ttu-id="d2d03-110">Sie können dazu einen ForEach-Object-Skriptblock verwenden, indem Sie Folgendes eingeben:</span><span class="sxs-lookup"><span data-stu-id="d2d03-110">You can do that in a ForEach-Object script block by typing:</span></span>

```
PS> Get-WmiObject -Class Win32_LogicalDisk | ForEach-Object -Process {($_.FreeSpace)/1024.0/1024.0}
48318.01171875
```

<span data-ttu-id="d2d03-111">Leider erhalten Sie als Ausgabe nun Daten ohne zugeordnete Bezeichnung.</span><span class="sxs-lookup"><span data-stu-id="d2d03-111">Unfortunately, the output is now data with no associated label.</span></span> <span data-ttu-id="d2d03-112">Da WMI-Eigenschaften wie diese schreibgeschützt sind, kann FreeSpace nicht direkt konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="d2d03-112">Because WMI properties such as this are read-only, you cannot directly convert FreeSpace.</span></span> <span data-ttu-id="d2d03-113">Wenn Sie Folgendes eingeben:</span><span class="sxs-lookup"><span data-stu-id="d2d03-113">If you type this:</span></span>

```powershell
Get-WmiObject -Class Win32_LogicalDisk | ForEach-Object -Process {$_.FreeSpace = ($_.FreeSpace)/1024.0/1024.0}
```

<span data-ttu-id="d2d03-114">Erhalten Sie eine Fehlermeldung:</span><span class="sxs-lookup"><span data-stu-id="d2d03-114">You get an error message:</span></span>

```output
"FreeSpace" is a ReadOnly property.
At line:1 char:70
+ Get-WmiObject -Class Win32_LogicalDisk | ForEach-Object -Process {$_.F <<<< r
eeSpace = ($_.FreeSpace)/1024.0/1024.0}
```

<span data-ttu-id="d2d03-115">Sie könnten die Daten mithilfe bestimmter erweiterter Techniken neu anordnen, ein einfacherer Ansatz ist jedoch die Erstellung ein neues Objekts mit **Select-Object**.</span><span class="sxs-lookup"><span data-stu-id="d2d03-115">You could reorganize the data by using some advanced techniques, but a simpler approach is to create a new object, by using **Select-Object**.</span></span>