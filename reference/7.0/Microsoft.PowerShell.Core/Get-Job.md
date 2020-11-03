---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-job?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Job
ms.openlocfilehash: 76644dbf15d2bdabd7a365f4bd5910a50502e17d
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93211311"
---
# <span data-ttu-id="75d20-103">Get-Job</span><span class="sxs-lookup"><span data-stu-id="75d20-103">Get-Job</span></span>

## <span data-ttu-id="75d20-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="75d20-104">SYNOPSIS</span></span>
<span data-ttu-id="75d20-105">Ruft PowerShell-Hintergrund Aufträge ab, die in der aktuellen Sitzung ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="75d20-105">Gets PowerShell background jobs that are running in the current session.</span></span>

## <span data-ttu-id="75d20-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="75d20-106">SYNTAX</span></span>

### <span data-ttu-id="75d20-107">Sessionidparameterset (Standard)</span><span class="sxs-lookup"><span data-stu-id="75d20-107">SessionIdParameterSet (Default)</span></span>

```
Get-Job [-IncludeChildJob] [-ChildJobState <JobState>] [-HasMoreData <Boolean>] [-Before <DateTime>]
 [-After <DateTime>] [-Newest <Int32>] [[-Id] <Int32[]>] [<CommonParameters>]
```

### <span data-ttu-id="75d20-108">Instanceidparameterset</span><span class="sxs-lookup"><span data-stu-id="75d20-108">InstanceIdParameterSet</span></span>

```
Get-Job [-IncludeChildJob] [-ChildJobState <JobState>] [-HasMoreData <Boolean>] [-Before <DateTime>]
 [-After <DateTime>] [-Newest <Int32>] [-InstanceId] <Guid[]> [<CommonParameters>]
```

### <span data-ttu-id="75d20-109">Nameparameterset</span><span class="sxs-lookup"><span data-stu-id="75d20-109">NameParameterSet</span></span>

```
Get-Job [-IncludeChildJob] [-ChildJobState <JobState>] [-HasMoreData <Boolean>] [-Before <DateTime>]
 [-After <DateTime>] [-Newest <Int32>] [-Name] <String[]> [<CommonParameters>]
```

### <span data-ttu-id="75d20-110">Stateparameterset</span><span class="sxs-lookup"><span data-stu-id="75d20-110">StateParameterSet</span></span>

```
Get-Job [-IncludeChildJob] [-ChildJobState <JobState>] [-HasMoreData <Boolean>] [-Before <DateTime>]
 [-After <DateTime>] [-Newest <Int32>] [-State] <JobState> [<CommonParameters>]
```

### <span data-ttu-id="75d20-111">Commandparameterset</span><span class="sxs-lookup"><span data-stu-id="75d20-111">CommandParameterSet</span></span>

```
Get-Job [-IncludeChildJob] [-ChildJobState <JobState>] [-HasMoreData <Boolean>] [-Before <DateTime>]
 [-After <DateTime>] [-Newest <Int32>] [-Command <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="75d20-112">Filterparameterset</span><span class="sxs-lookup"><span data-stu-id="75d20-112">FilterParameterSet</span></span>

```
Get-Job [-Filter] <Hashtable> [<CommonParameters>]
```

## <span data-ttu-id="75d20-113">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="75d20-113">DESCRIPTION</span></span>

<span data-ttu-id="75d20-114">Das **Get-Job** -Cmdlet ruft Objekte ab, die die in der aktuellen Sitzung gestarteten Hintergrundaufträge darstellen.</span><span class="sxs-lookup"><span data-stu-id="75d20-114">The **Get-Job** cmdlet gets objects that represent the background jobs that were started in the current session.</span></span> <span data-ttu-id="75d20-115">Sie können **Get-Job** verwenden, um Aufträge zu erhalten, die mit dem Cmdlet "Start-Job" oder mit dem *AsJob* -Parameter eines beliebigen Cmdlets gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="75d20-115">You can use **Get-Job** to get jobs that were started by using the Start-Job cmdlet, or by using the *AsJob* parameter of any cmdlet.</span></span>

<span data-ttu-id="75d20-116">Ohne Parameter ruft ein **Get-Job-** Befehl alle Aufträge in der aktuellen Sitzung ab.</span><span class="sxs-lookup"><span data-stu-id="75d20-116">Without parameters, a **Get-Job** command gets all jobs in the current session.</span></span>
<span data-ttu-id="75d20-117">Mithilfe der Parameter von **Get-Job** können Sie bestimmte Aufträge abrufen.</span><span class="sxs-lookup"><span data-stu-id="75d20-117">You can use the parameters of **Get-Job** to get particular jobs.</span></span>

<span data-ttu-id="75d20-118">Das von **Get-Job** zurückgegebene Auftragsobjekt enthält nützliche Informationen zum Auftrag, aber keine Auftragsergebnisse.</span><span class="sxs-lookup"><span data-stu-id="75d20-118">The job object that **Get-Job** returns contains useful information about the job, but it does not contain the job results.</span></span> <span data-ttu-id="75d20-119">Verwenden Sie das Cmdlet "Receive-Job", um die Ergebnisse zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="75d20-119">To get the results, use the Receive-Job cmdlet.</span></span>

<span data-ttu-id="75d20-120">Ein PowerShell-Hintergrund Auftrag ist ein Befehl, der im Hintergrund ausgeführt wird, ohne mit der aktuellen Sitzung zu interagieren.</span><span class="sxs-lookup"><span data-stu-id="75d20-120">A PowerShell background job is a command that runs in the background without interacting with the current session.</span></span> <span data-ttu-id="75d20-121">In der Regel verwenden Sie einen Hintergrund Auftrag, um einen komplexen Befehl auszuführen, der lange Zeit in Anspruch nimmt.</span><span class="sxs-lookup"><span data-stu-id="75d20-121">Typically, you use a background job to run a complex command that takes a long time to finish.</span></span> <span data-ttu-id="75d20-122">Weitere Informationen zu Hintergrund Aufträgen in PowerShell finden Sie unter about_Jobs.</span><span class="sxs-lookup"><span data-stu-id="75d20-122">For more information about background jobs in PowerShell, see about_Jobs.</span></span>

<span data-ttu-id="75d20-123">Ab Windows PowerShell 3.0 ruft das **Get-Job** -Cmdlet auch benutzerdefinierte Auftragstypen ab, wie z. B. Workflowaufträge und Instanzen von geplanten Aufträgen.</span><span class="sxs-lookup"><span data-stu-id="75d20-123">Beginning in Windows PowerShell 3.0, the **Get-Job** cmdlet also gets custom job types, such as workflow jobs and instances of scheduled jobs.</span></span> <span data-ttu-id="75d20-124">Zum Ermitteln des Auftragstyps eines Auftrags verwenden Sie die **PSJobTypeName** -Eigenschaft des Auftrags.</span><span class="sxs-lookup"><span data-stu-id="75d20-124">To find the job type of a job, use the **PSJobTypeName** property of the job.</span></span>

<span data-ttu-id="75d20-125">Zum Aktivieren von **Get-Job** zum erhalten eines benutzerdefinierten Auftrags Typs importieren Sie das Modul, das den benutzerdefinierten Auftragstyp unterstützt, in die Sitzung, bevor Sie einen **Get-Job-** Befehl ausführen. verwenden Sie hierzu entweder das Cmdlet "Import-Module", oder verwenden Sie ein Cmdlet im Modul.</span><span class="sxs-lookup"><span data-stu-id="75d20-125">To enable **Get-Job** to get a custom job type, import the module that supports the custom job type into the session before you run a **Get-Job** command, either by using the Import-Module cmdlet or by using or getting a cmdlet in the module.</span></span> <span data-ttu-id="75d20-126">Informationen zu einem bestimmten benutzerdefinierten Auftragstyp finden Sie in der Dokumentation der Funktion „Benutzerdefinierte Auftragstypen“.</span><span class="sxs-lookup"><span data-stu-id="75d20-126">For information about a particular custom job type, see the documentation of the custom job type feature.</span></span>

## <span data-ttu-id="75d20-127">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="75d20-127">EXAMPLES</span></span>

### <span data-ttu-id="75d20-128">Beispiel 1: alle Hintergrund Aufträge, die in der aktuellen Sitzung gestartet wurden</span><span class="sxs-lookup"><span data-stu-id="75d20-128">Example 1: Get all background jobs started in the current session</span></span>

```powershell
Get-Job
```

<span data-ttu-id="75d20-129">Dieser Befehl ruft alle Hintergrundaufträge ab, die in der aktuellen Sitzung gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="75d20-129">This command gets all background jobs started in the current session.</span></span>
<span data-ttu-id="75d20-130">In anderen Sitzungen erstellte Aufträge sind nicht enthalten, auch wenn die Aufträge auf dem lokalen Computer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="75d20-130">It does not include jobs created in other sessions, even if the jobs run on the local computer.</span></span>

### <span data-ttu-id="75d20-131">Beispiel 2: Beenden eines Auftrags mit einer Instanz-ID</span><span class="sxs-lookup"><span data-stu-id="75d20-131">Example 2: Stop a job by using an instance ID</span></span>

<span data-ttu-id="75d20-132">Diese Befehle zeigen, wie die Instanz-ID eines Auftrags abgerufen und dann zum Beenden eines Auftrags verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="75d20-132">These commands show how to get the instance ID of a job and then use it to stop a job.</span></span>
<span data-ttu-id="75d20-133">Im Gegensatz zum Namen eines Auftrags, der nicht eindeutig ist, ist die Instanz-ID eindeutig.</span><span class="sxs-lookup"><span data-stu-id="75d20-133">Unlike the name of a job, which is not unique, the instance ID is unique.</span></span>

```powershell
$j = Get-Job -Name Job1
$ID = $j.InstanceID
$ID
```

```Output
Guid
----
03c3232e-1d23-453b-a6f4-ed73c9e29d55
```

```powershell
Stop-Job -InstanceId $ID
```

<span data-ttu-id="75d20-134">Der erste Befehl ruft mit dem **Get-Job** -Cmdlet einen Auftrag ab.</span><span class="sxs-lookup"><span data-stu-id="75d20-134">The first command uses the **Get-Job** cmdlet to get a job.</span></span> <span data-ttu-id="75d20-135">Er verwendet den *Name* -Parameter, um den Auftrag zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="75d20-135">It uses the *Name* parameter to identify the job.</span></span> <span data-ttu-id="75d20-136">Der Befehl speichert das von **Get-Job** zurückgegebene Auftragsobjekt in der $j-Variablen.</span><span class="sxs-lookup"><span data-stu-id="75d20-136">The command stores the job object that **Get-Job** returns in the $j variable.</span></span> <span data-ttu-id="75d20-137">In diesem Beispiel ist nur ein Auftrag mit dem angegebenen Namen vorhanden.</span><span class="sxs-lookup"><span data-stu-id="75d20-137">In this example, there is only one job with the specified name.</span></span>

<span data-ttu-id="75d20-138">Mit dem zweiten Befehl wird die **InstanceId** -Eigenschaft des Objekts in der $j-Variablen abgerufen und in der $ID-Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="75d20-138">The second command gets the **InstanceId** property of the object in the $j variable and stores it in the $ID variable.</span></span>

<span data-ttu-id="75d20-139">Der dritte Befehl zeigt den Wert der $ID-Variablen an.</span><span class="sxs-lookup"><span data-stu-id="75d20-139">The third command displays the value of the $ID variable.</span></span>

<span data-ttu-id="75d20-140">Der vierte Befehl verwendet Stop-Job Cmdlet, um den Auftrag zu unterbinden.</span><span class="sxs-lookup"><span data-stu-id="75d20-140">The fourth command uses Stop-Job cmdlet to stop the job.</span></span> <span data-ttu-id="75d20-141">Er verwendet den *InstanceId* -Parameter zum Identifizieren des Auftrags und die $ID-Variable, um die Instanz-ID des Auftrags darzustellen.</span><span class="sxs-lookup"><span data-stu-id="75d20-141">It uses the *InstanceId* parameter to identify the job and $ID variable to represent the instance ID of the job.</span></span>

### <span data-ttu-id="75d20-142">Beispiel 3: Get-Aufträge, die einen bestimmten Befehl enthalten</span><span class="sxs-lookup"><span data-stu-id="75d20-142">Example 3: Get jobs that include a specific command</span></span>

```powershell
Get-Job -Command "*get-process*"
```

<span data-ttu-id="75d20-143">Dieser Befehl ruft die Aufträge im System ab, die einen Get-Process Befehl enthalten.</span><span class="sxs-lookup"><span data-stu-id="75d20-143">This command gets the jobs on the system that include a Get-Process command.</span></span> <span data-ttu-id="75d20-144">Der Befehl verwendet den *Command* -Parameter von **Get-Job** , um die abgerufenen Aufträge einzuschränken.</span><span class="sxs-lookup"><span data-stu-id="75d20-144">The command uses the *Command* parameter of **Get-Job** to limit the jobs retrieved.</span></span> <span data-ttu-id="75d20-145">Der Befehl verwendet Platzhalter Zeichen (\*), um Aufträge zu erhalten, die in der Befehls Zeichenfolge einen **Get-Process-** Befehl enthalten.</span><span class="sxs-lookup"><span data-stu-id="75d20-145">The command uses wildcard characters (\*) to get jobs that include a **Get-Process** command anywhere in the command string.</span></span>

### <span data-ttu-id="75d20-146">Beispiel 4: Get-Aufträge, die einen bestimmten Befehl enthalten, mithilfe der Pipeline</span><span class="sxs-lookup"><span data-stu-id="75d20-146">Example 4: Get jobs that include a specific command by using the pipeline</span></span>

```powershell
"*get-process*" | Get-Job
```

<span data-ttu-id="75d20-147">Wie der Befehl im vorherigen Beispiel ruft dieser Befehl die Aufträge im System ab, die einen **Get-Process-** Befehl enthalten.</span><span class="sxs-lookup"><span data-stu-id="75d20-147">Like the command in the previous example, this command gets the jobs on the system that include a **Get-Process** command.</span></span> <span data-ttu-id="75d20-148">Der Befehl verwendet einen Pipeline Operator (|), um eine Zeichenfolge in Anführungszeichen an das **Get-Job-** Cmdlet zu senden.</span><span class="sxs-lookup"><span data-stu-id="75d20-148">The command uses a pipeline operator (|) to send a string, in quotation marks, to the **Get-Job** cmdlet.</span></span> <span data-ttu-id="75d20-149">Dies entspricht dem vorherigen Befehl.</span><span class="sxs-lookup"><span data-stu-id="75d20-149">It is the equivalent of the previous command.</span></span>

### <span data-ttu-id="75d20-150">Beispiel 5: Aufträge, die noch nicht gestartet wurden</span><span class="sxs-lookup"><span data-stu-id="75d20-150">Example 5: Get jobs that have not been started</span></span>

```powershell
Get-Job -State NotStarted
```

<span data-ttu-id="75d20-151">Mit diesem Befehl werden nur die Aufträge abgerufen, die erstellt, aber noch nicht gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="75d20-151">This command gets only those jobs that have been created but have not yet been started.</span></span>
<span data-ttu-id="75d20-152">Dazu gehören Aufträge, deren Ausführung für einen Zeitpunkt in der Zukunft geplant ist, und solche, die noch nicht geplant wurden.</span><span class="sxs-lookup"><span data-stu-id="75d20-152">This includes jobs that are scheduled to run in the future and those not yet scheduled.</span></span>

### <span data-ttu-id="75d20-153">Beispiel 6: Aufträge erhalten, denen kein Name zugewiesen wurde</span><span class="sxs-lookup"><span data-stu-id="75d20-153">Example 6: Get jobs that have not been assigned a name</span></span>

```powershell
Get-Job -Name Job*
```

<span data-ttu-id="75d20-154">Dieser Befehl ruft alle Aufträge ab, deren Auftrags Name mit "Job" beginnt.</span><span class="sxs-lookup"><span data-stu-id="75d20-154">This command gets all jobs that have job names that begin with job.</span></span>
<span data-ttu-id="75d20-155">Da Job \<number\> der Standardname für einen Auftrag ist, ruft dieser Befehl alle Aufträge ab, denen kein explizit zugewiesener Name zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="75d20-155">Because job\<number\> is the default name for a job, this command gets all jobs that do not have an explicitly assigned name.</span></span>

### <span data-ttu-id="75d20-156">Beispiel 7: Verwenden eines Auftrags Objekts zur Darstellung des Auftrags in einem Befehl</span><span class="sxs-lookup"><span data-stu-id="75d20-156">Example 7: Use a job object to represent the job in a command</span></span>

<span data-ttu-id="75d20-157">Dieses Beispiel veranschaulicht, wie Sie mit **Get-Job** ein Auftragsobjekt abrufen. Anschließend wird gezeigt, wie Sie mit dem Auftragsobjekt den Auftrag in einem Befehl darstellen.</span><span class="sxs-lookup"><span data-stu-id="75d20-157">This example shows how to use **Get-Job** to get a job object, and then it shows how to use the job object to represent the job in a command.</span></span>

```powershell
Start-Job -ScriptBlock {Get-Process} -Name MyJob
$j = Get-Job -Name MyJob
$j
```

```Output
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
6      MyJob           BackgroundJob   Completed     True            localhost            Get-Process
```

```powershell
Receive-Job -Job $j
```

```Output
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
    124       4    13572      12080    59            1140 audiodg
    783      16    11428      13636   100             548 CcmExec
     96       4     4252       3764    59            3856 ccmsetup
...
```

<span data-ttu-id="75d20-158">Der erste Befehl verwendet das **Start-Job-** Cmdlet, um einen Hintergrund Auftrag zu starten, der einen **Get-Process-** Befehl auf dem lokalen Computer ausführt.</span><span class="sxs-lookup"><span data-stu-id="75d20-158">The first command uses the **Start-Job** cmdlet to start a background job that runs a **Get-Process** command on the local computer.</span></span> <span data-ttu-id="75d20-159">Der Befehl verwendet den *Name* -Parameter von **Start-Job** , um dem Auftrag einen Anzeigenamen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="75d20-159">The command uses the *Name* parameter of **Start-Job** to assign a friendly name to the job.</span></span>

<span data-ttu-id="75d20-160">Im zweiten Befehl wird mit Get-Job der Auftrag abgerufen.</span><span class="sxs-lookup"><span data-stu-id="75d20-160">The second command uses Get-Job to get the job.</span></span> <span data-ttu-id="75d20-161">Mit dem *Name* -Parameter von **Get-Job** wird der Auftrag identifiziert.</span><span class="sxs-lookup"><span data-stu-id="75d20-161">It uses the *Name* parameter of **Get-Job** to identify the job.</span></span> <span data-ttu-id="75d20-162">Mit dem Befehl wird das resultierende Auftragsobjekt in der Variablen %%amp;quot;$j%%amp;quot; gespeichert.</span><span class="sxs-lookup"><span data-stu-id="75d20-162">The command saves the resulting job object in the $j variable.</span></span>

<span data-ttu-id="75d20-163">Der dritte Befehl zeigt den Wert des Auftragsobjekts in der $j-Variablen an.</span><span class="sxs-lookup"><span data-stu-id="75d20-163">The third command displays the value of the job object in the $j variable.</span></span> <span data-ttu-id="75d20-164">Der Wert der **State** -Eigenschaft zeigt an, dass der Auftrag abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="75d20-164">The value of the **State** property shows that the job is completed.</span></span> <span data-ttu-id="75d20-165">Der Wert der **HasMoreData** -Eigenschaft zeigt, dass Ergebnisse des Auftrags verfügbar sind, die noch nicht abgerufen wurden.</span><span class="sxs-lookup"><span data-stu-id="75d20-165">The value of the **HasMoreData** property shows that there are results available from the job that have not yet been retrieved.</span></span>

<span data-ttu-id="75d20-166">Der vierte Befehl verwendet das **Receive-Job-** Cmdlet, um die Ergebnisse des Auftrags zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="75d20-166">The fourth command uses the **Receive-Job** cmdlet to get the results of the job.</span></span> <span data-ttu-id="75d20-167">Der Auftrag wird durch das Auftragsobjekt in der $j-Variablen dargestellt.</span><span class="sxs-lookup"><span data-stu-id="75d20-167">It uses the job object in the $j variable to represent the job.</span></span> <span data-ttu-id="75d20-168">Sie können auch einen Pipeline Operator verwenden, um ein Auftrags Objekt an **Receive-Job** zu senden.</span><span class="sxs-lookup"><span data-stu-id="75d20-168">You can also use a pipeline operator to send a job object to **Receive-Job** .</span></span>

### <span data-ttu-id="75d20-169">Beispiel 8: alle Aufträge einschließlich der von einer anderen Methode gestarteten Aufträge</span><span class="sxs-lookup"><span data-stu-id="75d20-169">Example 8: Get all jobs including jobs started by a different method</span></span>

<span data-ttu-id="75d20-170">In diesem Beispiel wird veranschaulicht, dass das **Get-Job-** Cmdlet alle Aufträge, die in der aktuellen Sitzung gestartet wurden, auch dann erhalten kann, wenn Sie mit verschiedenen Methoden gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="75d20-170">This example demonstrates that the **Get-Job** cmdlet can get all of the jobs that were started in the current session, even if they were started by using different methods.</span></span>

```powershell
Start-Job -ScriptBlock {Get-EventLog System}
Invoke-Command -ComputerName S1 -ScriptBlock {Get-EventLog System} -AsJob
Invoke-Command -ComputerName S2 -ScriptBlock {Start-Job -ScriptBlock {Get-EventLog System}}
Get-Job
```

```Output
Id     Name       PSJobTypeName   State         HasMoreData     Location        Command
--     ----       -------------   -----         -----------     --------        -------
1      Job1       BackgroundJob   Running       True            localhost       Get-EventLog System
2      Job2       RemoteJob       Running       True            S1              Get-EventLog System
```

```powershell
Invoke-Command -ComputerName S2 -ScriptBlock {Start-Job -ScriptBlock {Get-EventLog System}}
```

```Output
Id    Name     PSJobTypeName  State      HasMoreData   Location   Command
--    ----     -------------  -----      -----------   -------    -------
4     Job4     BackgroundJob  Running    True          localhost  Get-Eventlog System
```

<span data-ttu-id="75d20-171">Der erste Befehl verwendet das **Start-Job-** Cmdlet, um einen Auftrag auf dem lokalen Computer zu starten.</span><span class="sxs-lookup"><span data-stu-id="75d20-171">The first command uses the **Start-Job** cmdlet to start a job on the local computer.</span></span>

<span data-ttu-id="75d20-172">Der zweite Befehl verwendet den *AsJob* -Parameter des Cmdlets " **Aufruf-Command** ", um einen Auftrag auf dem S1-Computer zu starten.</span><span class="sxs-lookup"><span data-stu-id="75d20-172">The second command uses the *AsJob* parameter of the **Invoke-Command** cmdlet to start a job on the S1 computer.</span></span> <span data-ttu-id="75d20-173">Obwohl die Befehle im Auftrag auf dem Remotecomputer ausgeführt werden, wird das Auftragsobjekt auf dem lokalen Computer erstellt; daher verwenden Sie lokale Befehle zum Verwalten des Auftrags.</span><span class="sxs-lookup"><span data-stu-id="75d20-173">Even though the commands in the job run on the remote computer, the job object is created on the local computer, so you use local commands to manage the job.</span></span>

<span data-ttu-id="75d20-174">Der dritte Befehl verwendet das **Invoke-Command** -Cmdlet zum Ausführen eines **Start-Job** -Befehls auf dem Computer S2.</span><span class="sxs-lookup"><span data-stu-id="75d20-174">The third command uses the **Invoke-Command** cmdlet to run a **Start-Job** command on the S2 computer.</span></span> <span data-ttu-id="75d20-175">Wenn diese Methode verwendet wird, wird das Auftrags Objekt auf dem Remote Computer erstellt, sodass Sie Remote Befehle verwenden, um den Auftrag zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="75d20-175">By using this method, the job object is created on the remote computer, so you use remote commands to manage the job.</span></span>

<span data-ttu-id="75d20-176">Der vierte Befehl ruft mit **Get-Job** die auf dem lokalen Computer gespeicherten Aufträge ab.</span><span class="sxs-lookup"><span data-stu-id="75d20-176">The fourth command uses **Get-Job** to get the jobs stored on the local computer.</span></span> <span data-ttu-id="75d20-177">Die **psjobtykame** -Eigenschaft von Aufträgen, die in Windows PowerShell 3,0 eingeführt wurde, zeigt, dass der lokale Auftrag, der mithilfe des Cmdlets **Start-Job** gestartet wurde, ein Hintergrund Auftrag ist und der Auftrag, der in einer Remote Sitzung mit dem Cmdlet "Start- **Command** " gestartet wurde, ein Remote Auftrag ist.</span><span class="sxs-lookup"><span data-stu-id="75d20-177">The **PSJobTypeName** property of jobs, introduced in Windows PowerShell 3.0, shows that the local job started by using the **Start-Job** cmdlet is a background job and the job started in a remote session by using the **Invoke-Command** cmdlet is a remote job.</span></span>

<span data-ttu-id="75d20-178">Der fünfte Befehl verwendet " **aufrufen-Command** " zum Ausführen eines **Get-Job-** Befehls auf dem Computer S2. Die Beispielausgabe zeigt die Ergebnisse des Get-Job-Befehls an.</span><span class="sxs-lookup"><span data-stu-id="75d20-178">The fifth command uses **Invoke-Command** to run a **Get-Job** command on the S2 computer.The sample output shows the results of the Get-Job command.</span></span> <span data-ttu-id="75d20-179">Auf dem Computer S2 scheint der Auftrag ein lokaler Auftrag zu sein.</span><span class="sxs-lookup"><span data-stu-id="75d20-179">On the S2 computer, the job appears to be a local job.</span></span> <span data-ttu-id="75d20-180">Der Computername ist "localhost", und der Auftragstyp ist ein Hintergrund Auftrag.</span><span class="sxs-lookup"><span data-stu-id="75d20-180">The computer name is localhost and the job type is a background job.</span></span>

<span data-ttu-id="75d20-181">Weitere Informationen zum Ausführen von Hintergrund Aufträgen auf Remote Computern finden Sie unter about_Remote_Jobs.</span><span class="sxs-lookup"><span data-stu-id="75d20-181">For more information about how to run background jobs on remote computers, see about_Remote_Jobs.</span></span>

### <span data-ttu-id="75d20-182">Beispiel 9: Untersuchen eines fehlgeschlagenen Auftrags</span><span class="sxs-lookup"><span data-stu-id="75d20-182">Example 9: Investigate a failed job</span></span>

```powershell
Start-Job -ScriptBlock {Get-Process}
```

```Output
Id     Name       PSJobTypeName   State       HasMoreData     Location             Command
--     ----       -------------   -----       -----------     --------             -------
1      Job1       BackgroundJob   Failed      False           localhost            Get-Process
```

```powershell
(Get-Job).JobStateInfo | Format-List -Property *
```

```Output
State  : Failed
Reason :
```

```powershell
Get-Job | Format-List -Property *
```

```Output
HasMoreData   : False
StatusMessage :
Location      : localhost
Command       : get-process
JobStateInfo  : Failed
Finished      : System.Threading.ManualReset
EventInstanceId    : fb792295-1318-4f5d-8ac8-8a89c5261507
Id            : 1
Name          : Job1
ChildJobs     : {Job2}
Output        : {}
Error         : {}
Progress      : {}
Verbose       : {}
Debug         : {}
Warning       : {}
StateChanged  :
```

```powershell
(Get-Job -Name job2).JobStateInfo.Reason
```

```Output
Connecting to remote server using WSManCreateShellEx api failed. The async callback gave the following error message: Access is denied.

For information about requirements for remoting in PowerShell, see about_Remote_Requirements. For
troubleshooting tips, see about_Remote_Troubleshooting.
```

<span data-ttu-id="75d20-183">Dieser Befehl zeigt, wie das von **Get-Job** zurückgegebene Auftrags Objekt verwendet wird, um zu untersuchen, warum ein Auftrag fehlgeschlagen ist.</span><span class="sxs-lookup"><span data-stu-id="75d20-183">This command shows how to use the job object that **Get-Job** returns to investigate why a job failed.</span></span>
<span data-ttu-id="75d20-184">Weiterhin wird gezeigt, wie die untergeordneten Aufträge der einzelnen Aufträge abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="75d20-184">It also shows how to get the child jobs of each job.</span></span>

<span data-ttu-id="75d20-185">Der erste Befehl verwendet das **Start-Job-** Cmdlet, um einen Auftrag auf dem lokalen Computer zu starten.</span><span class="sxs-lookup"><span data-stu-id="75d20-185">The first command uses the **Start-Job** cmdlet to start a job on the local computer.</span></span> <span data-ttu-id="75d20-186">Das von **Start-Job** zurückgegebene Auftragsobjekt zeigt, dass bei der Auftragsausführung ein Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="75d20-186">The job object that **Start-Job** returns shows that the job failed.</span></span> <span data-ttu-id="75d20-187">Der Wert der **State** -Eigenschaft ist fehlerhaft.</span><span class="sxs-lookup"><span data-stu-id="75d20-187">The value of the **State** property is Failed.</span></span>

<span data-ttu-id="75d20-188">Der zweite Befehl ruft mit dem **Get-Job** -Cmdlet den Auftrag ab.</span><span class="sxs-lookup"><span data-stu-id="75d20-188">The second command uses the **Get-Job** cmdlet to get the job.</span></span> <span data-ttu-id="75d20-189">Der Befehl verwendet die Punktmethode, um den Wert der **JobStateInfo** -Eigenschaft des Objekts abzurufen.</span><span class="sxs-lookup"><span data-stu-id="75d20-189">The command uses the dot method to get the value of the **JobStateInfo** property of the object.</span></span> <span data-ttu-id="75d20-190">Er verwendet einen Pipeline Operator, um das Objekt in der **jobstatueinfo** -Eigenschaft an das Format-List-Cmdlet zu senden, das alle Eigenschaften des Objekts (\*) in einer Liste formatiert. Das Ergebnis des Befehls " **Format-List** " zeigt, dass der Wert der **reason** -Eigenschaft des Auftrags leer ist.</span><span class="sxs-lookup"><span data-stu-id="75d20-190">It uses a pipeline operator to send the object in the **JobStateInfo** property to the Format-List cmdlet, which formats all of the properties of the object (\*) in a list.The result of the **Format-List** command shows that the value of the **Reason** property of the job is blank.</span></span>

<span data-ttu-id="75d20-191">Mit dem dritten Befehl werden weitere Informationen untersucht.</span><span class="sxs-lookup"><span data-stu-id="75d20-191">The third command investigates more.</span></span> <span data-ttu-id="75d20-192">Er verwendet einen **Get-Job-** Befehl, um den Auftrag zu erhalten, und verwendet dann einen Pipeline Operator, um das gesamte Auftrags Objekt an das Cmdlet " **Format-List** " zu senden, das alle Eigenschaften des Auftrags in einer Liste anzeigt. Die Anzeige aller Eigenschaften im Auftrags Objekt zeigt, dass der Auftrag einen untergeordneten Auftrag mit dem Namen Job2 enthält.</span><span class="sxs-lookup"><span data-stu-id="75d20-192">It uses a **Get-Job** command to get the job and then uses a pipeline operator to send the whole job object to the **Format-List** cmdlet, which displays all of the properties of the job in a list.The display of all properties in the job object shows that the job contains a child job named Job2.</span></span>

<span data-ttu-id="75d20-193">Im vierten Befehl wird mit **Get-Job** das Auftragsobjekt abgerufen, das den untergeordneten Auftrag Job2 darstellt.</span><span class="sxs-lookup"><span data-stu-id="75d20-193">The fourth command uses **Get-Job** to get the job object that represents the Job2 child job.</span></span> <span data-ttu-id="75d20-194">Dies ist der Auftrag, in dem der Befehl tatsächlich ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="75d20-194">This is the job in which the command actually ran.</span></span> <span data-ttu-id="75d20-195">Er verwendet die Punkt-Methode, um die **reason** -Eigenschaft der **Jobstatus Info** -Eigenschaft zu erhalten. Das Ergebnis zeigt, dass der Auftrag aufgrund eines Zugriffs Verweigerungs Fehlers fehlgeschlagen ist.</span><span class="sxs-lookup"><span data-stu-id="75d20-195">It uses the dot method to get the **Reason** property of the **JobStateInfo** property.The result shows that the job failed because of an Access Denied error.</span></span> <span data-ttu-id="75d20-196">In diesem Fall hat der Benutzer vergessen, beim Starten von PowerShell die Option als Administrator ausführen zu verwenden. da Hintergrund Aufträge die Remoting-Features von PowerShell verwenden, muss der Computer für Remoting konfiguriert werden, um einen Auftrag auszuführen, auch wenn der Auftrag auf dem lokalen Computer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="75d20-196">In this case, the user forgot to use the Run as administrator option when starting PowerShell.Because background jobs use the remoting features of PowerShell, the computer must be configured for remoting to run a job, even when the job runs on the local computer.</span></span>

### <span data-ttu-id="75d20-197">Beispiel 10: Filtern von gefilterten Ergebnissen</span><span class="sxs-lookup"><span data-stu-id="75d20-197">Example 10: Get filtered results</span></span>

<span data-ttu-id="75d20-198">Dieses Beispiel zeigt, wie Sie den *Filter* -Parameter zum Abrufen eines Workflowauftrags verwenden.</span><span class="sxs-lookup"><span data-stu-id="75d20-198">This example shows how to use the *Filter* parameter to get a workflow job.</span></span>
<span data-ttu-id="75d20-199">Der in Windows PowerShell 3.0 eingeführte *Filter* -Parameter ist nur für benutzerdefinierte Auftragstypen gültig, wie z. B. Workflowaufträge und geplante Aufträge.</span><span class="sxs-lookup"><span data-stu-id="75d20-199">The *Filter* parameter, introduced in Windows PowerShell 3.0 is valid only on custom job types, such as workflow jobs and scheduled jobs.</span></span>

```powershell
Workflow WFProcess {Get-Process}
WFProcess -AsJob -JobName WFProcessJob -PSPrivateMetadata @{MyCustomId = 92107}
Get-Job -Filter @{MyCustomId = 92107}
```

```Output
Id     Name            State         HasMoreData     Location             Command
--     ----            -----         -----------     --------             -------
1      WFProcessJob    Completed     True            localhost            WFProcess
```

<span data-ttu-id="75d20-200">Der erste Befehl verwendet das **Workflow** Schlüsselwort, um den WfProcess-Workflow zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="75d20-200">The first command uses the **Workflow** keyword to create the WFProcess workflow.</span></span>

<span data-ttu-id="75d20-201">Der zweite Befehl verwendet den *AsJob* -Parameter des WfProcess-Workflows, um den Workflow als Hintergrund Auftrag auszuführen.</span><span class="sxs-lookup"><span data-stu-id="75d20-201">The second command uses the *AsJob* parameter of the WFProcess workflow to run the workflow as a background job.</span></span> <span data-ttu-id="75d20-202">Mithilfe des *JobName* -Parameters des Workflows wird ein Name für den Auftrag angegeben und mithilfe des *PSPrivateMetadata* -Parameters des Workflows eine benutzerdefinierte ID.</span><span class="sxs-lookup"><span data-stu-id="75d20-202">It uses the *JobName* parameter of the workflow to specify a name for the job, and the *PSPrivateMetadata* parameter of the workflow to specify a custom ID.</span></span>

<span data-ttu-id="75d20-203">Der dritte Befehl verwendet den *Filter* -Parameter von **Get-Job** , um den Auftrag anhand der benutzerdefinierten ID abzurufen, die im *PSPrivateMetadata* -Parameter angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="75d20-203">The third command uses the *Filter* parameter of **Get-Job** to get the job by custom ID that was specified in the *PSPrivateMetadata* parameter.</span></span>

### <span data-ttu-id="75d20-204">Beispiel 11: erhalten von Informationen zu untergeordneten Aufträgen</span><span class="sxs-lookup"><span data-stu-id="75d20-204">Example 11: Get information about child jobs</span></span>

<span data-ttu-id="75d20-205">Dieses Beispiel zeigt die Auswirkungen der Verwendung der Parameter *IncludeChildJob* und *ChildJobState* des **Get-Job** -Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="75d20-205">This example shows the effect of using the *IncludeChildJob* and *ChildJobState* parameters of the **Get-Job** cmdlet.</span></span>

```powershell
Get-Job
```

```Output
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
2      Job2            BackgroundJob   Completed     True            localhost            .\Get-Archive.ps1
4      Job4            RemoteJob       Failed        True            Server01, Server02   .\Get-Archive.ps1
7      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
8      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
9      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
10     UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
```

```powershell
Get-Job -IncludeChildJob
```

```Output
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
2      Job2            BackgroundJob   Completed     True            localhost           .\Get-Archive.ps1
3      Job3                            Completed     True            localhost           .\Get-Archive.ps1
4      Job4            RemoteJob       Failed        True            Server01, Server02  .\Get-Archive.ps1
5      Job5                            Failed        False           Server01            .\Get-Archive.ps1
6      Job6                            Completed     True            Server02            .\Get-Archive.ps1
7      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
8      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
9      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
10     UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
```

```powershell
Get-Job -Name Job4 -ChildJobState Failed
```

```Output
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
2      Job2            BackgroundJob   Completed     True            localhost           .\Get-Archive.ps1
4      Job4            RemoteJob       Failed        True            Server01, Server02  .\Get-Archive.ps1
5      Job5                            Failed        False           Server01            .\Get-Archive.ps1
7      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
8      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
9      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
10     UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
```

```powershell
(Get-Job -Name Job5).JobStateInfo.Reason
```

```Output
Connecting to remote server Server01 failed with the following error message:
Access is denied.
For more information, see the about_Remote_Troubleshooting Help topic.
```

<span data-ttu-id="75d20-206">Der erste Befehl ruft die Aufträge in der aktuellen Sitzung ab.</span><span class="sxs-lookup"><span data-stu-id="75d20-206">The first command gets the jobs in the current session.</span></span> <span data-ttu-id="75d20-207">Die Ausgabe umfasst einen Hintergrundauftrag, einen Remoteauftrag und mehrere Instanzen eines geplanten Auftrags.</span><span class="sxs-lookup"><span data-stu-id="75d20-207">The output includes a background job, a remote job and several instances of a scheduled job.</span></span> <span data-ttu-id="75d20-208">Bei der Ausführung des Remoteauftrags (Job4) scheint ein Fehler aufgetreten zu sein.</span><span class="sxs-lookup"><span data-stu-id="75d20-208">The remote job, Job4, appears to have failed.</span></span>

<span data-ttu-id="75d20-209">Im zweiten Befehl wird der *IncludeChildJob* -Parameter von **Get-Job** verwendet.</span><span class="sxs-lookup"><span data-stu-id="75d20-209">The second command uses the *IncludeChildJob* parameter of **Get-Job** .</span></span> <span data-ttu-id="75d20-210">In der Ausgabe werden die untergeordneten Aufträge aller Aufträge hinzugefügt, die über untergeordnete Aufträge verfügen. In diesem Fall zeigt die überarbeitete Ausgabe an, dass nur der untergeordnete Job5-Auftrag von Job4 fehlgeschlagen ist.</span><span class="sxs-lookup"><span data-stu-id="75d20-210">The output adds the child jobs of all jobs that have child jobs.In this case, the revised output shows that only the Job5 child job of Job4 failed.</span></span>

<span data-ttu-id="75d20-211">Der dritte Befehl verwendet den *childjobstate* -Parameter mit dem Wert failed. die Ausgabe enthält alle übergeordneten Aufträge und nur die untergeordneten Aufträge, die fehlgeschlagen sind.</span><span class="sxs-lookup"><span data-stu-id="75d20-211">The third command uses the *ChildJobState* parameter with a value of Failed.The output includes all parent jobs and only the child jobs that failed.</span></span>

<span data-ttu-id="75d20-212">Der vierte Befehl verwendet die **jobstateinfo** -Eigenschaft von Aufträgen und seine **reason** -Eigenschaft, um zu ermitteln, warum Job5 fehlgeschlagen ist.</span><span class="sxs-lookup"><span data-stu-id="75d20-212">The fourth command uses the **JobStateInfo** property of jobs and its **Reason** property to discover why Job5 failed.</span></span>

## <span data-ttu-id="75d20-213">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="75d20-213">PARAMETERS</span></span>

### <span data-ttu-id="75d20-214">Nach</span><span class="sxs-lookup"><span data-stu-id="75d20-214">-After</span></span>

<span data-ttu-id="75d20-215">Ruft abgeschlossene Aufträge ab, die nach dem angegebenen Datum und der angegebenen Uhrzeit beendet wurden.</span><span class="sxs-lookup"><span data-stu-id="75d20-215">Gets completed jobs that ended after the specified date and time.</span></span> <span data-ttu-id="75d20-216">Geben Sie ein **DateTime** -Objekt ein, z. b. ein vom Get-Date Cmdlet zurück gegebenes oder eine Zeichenfolge, die in ein **DateTime** -Objekt konvertiert werden kann, z `Dec 1, 2012 2:00 AM` . b `11/06` . oder.</span><span class="sxs-lookup"><span data-stu-id="75d20-216">Enter a **DateTime** object, such as one returned by the Get-Date cmdlet or a string that can be converted to a **DateTime** object, such as `Dec 1, 2012 2:00 AM` or `11/06`.</span></span>

<span data-ttu-id="75d20-217">Dieser Parameter kann nur für benutzerdefinierte Auftragstypen wie z. B. Workflowaufträge und geplante Aufträge verwendet werden, die über eine **EndTime** -Eigenschaft verfügen.</span><span class="sxs-lookup"><span data-stu-id="75d20-217">This parameter works only on custom job types, such as workflow jobs and scheduled jobs, that have an **EndTime** property.</span></span> <span data-ttu-id="75d20-218">Es funktioniert nicht bei standardmäßigen Hintergrund Aufträgen, wie z. b. bei der Verwendung des Cmdlets **Start-Job** .</span><span class="sxs-lookup"><span data-stu-id="75d20-218">It does not work on standard background jobs, such as those created by using the **Start-Job** cmdlet.</span></span> <span data-ttu-id="75d20-219">Weitere Informationen zur Unterstützung für diesen Parameter finden Sie unter dem Hilfethema für den Auftragstyp.</span><span class="sxs-lookup"><span data-stu-id="75d20-219">For information about support for this parameter, see the help topic for the job type.</span></span>

<span data-ttu-id="75d20-220">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="75d20-220">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.DateTime
Parameter Sets: SessionIdParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet, CommandParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="75d20-221">-Vor</span><span class="sxs-lookup"><span data-stu-id="75d20-221">-Before</span></span>

<span data-ttu-id="75d20-222">Ruft abgeschlossene Aufträge ab, die vor dem angegebenen Datum und der angegebenen Uhrzeit beendet wurden.</span><span class="sxs-lookup"><span data-stu-id="75d20-222">Gets completed jobs that ended before the specified date and time.</span></span>
<span data-ttu-id="75d20-223">Geben Sie ein **DateTime** -Objekt ein.</span><span class="sxs-lookup"><span data-stu-id="75d20-223">Enter a **DateTime** object.</span></span>

<span data-ttu-id="75d20-224">Dieser Parameter kann nur für benutzerdefinierte Auftragstypen wie z. B. Workflowaufträge und geplante Aufträge verwendet werden, die über eine **EndTime** -Eigenschaft verfügen.</span><span class="sxs-lookup"><span data-stu-id="75d20-224">This parameter works only on custom job types, such as workflow jobs and scheduled jobs, that have an **EndTime** property.</span></span> <span data-ttu-id="75d20-225">Es funktioniert nicht bei standardmäßigen Hintergrund Aufträgen, wie z. b. bei der Verwendung des Cmdlets **Start-Job** .</span><span class="sxs-lookup"><span data-stu-id="75d20-225">It does not work on standard background jobs, such as those created by using the **Start-Job** cmdlet.</span></span> <span data-ttu-id="75d20-226">Weitere Informationen zur Unterstützung für diesen Parameter finden Sie unter dem Hilfethema für den Auftragstyp.</span><span class="sxs-lookup"><span data-stu-id="75d20-226">For information about support for this parameter, see the help topic for the job type.</span></span>

<span data-ttu-id="75d20-227">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="75d20-227">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.DateTime
Parameter Sets: SessionIdParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet, CommandParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="75d20-228">-Childjobstate</span><span class="sxs-lookup"><span data-stu-id="75d20-228">-ChildJobState</span></span>

<span data-ttu-id="75d20-229">Ruft nur die untergeordneten Aufträge ab, die den angegebenen Status aufweisen.</span><span class="sxs-lookup"><span data-stu-id="75d20-229">Gets only the child jobs that have the specified state.</span></span>
<span data-ttu-id="75d20-230">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="75d20-230">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="75d20-231">NotStarted</span><span class="sxs-lookup"><span data-stu-id="75d20-231">NotStarted</span></span>
- <span data-ttu-id="75d20-232">Wird ausgeführt</span><span class="sxs-lookup"><span data-stu-id="75d20-232">Running</span></span>
- <span data-ttu-id="75d20-233">Abgeschlossen</span><span class="sxs-lookup"><span data-stu-id="75d20-233">Completed</span></span>
- <span data-ttu-id="75d20-234">Fehler</span><span class="sxs-lookup"><span data-stu-id="75d20-234">Failed</span></span>
- <span data-ttu-id="75d20-235">Beendet</span><span class="sxs-lookup"><span data-stu-id="75d20-235">Stopped</span></span>
- <span data-ttu-id="75d20-236">Blockiert</span><span class="sxs-lookup"><span data-stu-id="75d20-236">Blocked</span></span>
- <span data-ttu-id="75d20-237">Ausgesetzt</span><span class="sxs-lookup"><span data-stu-id="75d20-237">Suspended</span></span>
- <span data-ttu-id="75d20-238">Getrennt</span><span class="sxs-lookup"><span data-stu-id="75d20-238">Disconnected</span></span>
- <span data-ttu-id="75d20-239">Wird angehalten</span><span class="sxs-lookup"><span data-stu-id="75d20-239">Suspending</span></span>
- <span data-ttu-id="75d20-240">Wird beendet</span><span class="sxs-lookup"><span data-stu-id="75d20-240">Stopping</span></span>

<span data-ttu-id="75d20-241">Standardmäßig ruft **Get-Job** keine untergeordneten Aufträge ab.</span><span class="sxs-lookup"><span data-stu-id="75d20-241">By default, **Get-Job** does not get child jobs.</span></span>
<span data-ttu-id="75d20-242">Wenn Sie den *incluentchildjob* -Parameter verwenden, ruft **Get-Job** alle untergeordneten Aufträge ab.</span><span class="sxs-lookup"><span data-stu-id="75d20-242">By using the *IncludeChildJob* parameter, **Get-Job** gets all child jobs.</span></span>
<span data-ttu-id="75d20-243">Bei Verwendung des *ChildJobState* -Parameters hat der *IncludeChildJob* -Parameter keine Auswirkungen.</span><span class="sxs-lookup"><span data-stu-id="75d20-243">If you use the *ChildJobState* parameter, the *IncludeChildJob* parameter has no effect.</span></span>

<span data-ttu-id="75d20-244">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="75d20-244">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.JobState
Parameter Sets: SessionIdParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet, CommandParameterSet
Aliases:
Accepted values: NotStarted, Running, Completed, Failed, Stopped, Blocked, Suspended, Disconnected, Suspending, Stopping, AtBreakpoint

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="75d20-245">-Command</span><span class="sxs-lookup"><span data-stu-id="75d20-245">-Command</span></span>

<span data-ttu-id="75d20-246">Gibt ein Array von Befehlen als Zeichen folgen an.</span><span class="sxs-lookup"><span data-stu-id="75d20-246">Specifies an array of commands as strings.</span></span>
<span data-ttu-id="75d20-247">Mit diesem Cmdlet werden die Aufträge abgerufen, die die angegebenen Befehle enthalten.</span><span class="sxs-lookup"><span data-stu-id="75d20-247">This cmdlet gets the jobs that include the specified commands.</span></span>
<span data-ttu-id="75d20-248">Standardmäßig werden alle Aufträge fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="75d20-248">The default is all jobs.</span></span>
<span data-ttu-id="75d20-249">Sie können Platzhalter Zeichen verwenden, um ein Befehls Muster anzugeben.</span><span class="sxs-lookup"><span data-stu-id="75d20-249">You can use wildcard characters to specify a command pattern.</span></span>

```yaml
Type: System.String[]
Parameter Sets: CommandParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="75d20-250">-Filter</span><span class="sxs-lookup"><span data-stu-id="75d20-250">-Filter</span></span>

<span data-ttu-id="75d20-251">Gibt eine Hash Tabelle mit Bedingungen an.</span><span class="sxs-lookup"><span data-stu-id="75d20-251">Specifies a hash table of conditions.</span></span>
<span data-ttu-id="75d20-252">Dieses Cmdlet ruft Aufträge ab, die alle Bedingungen erfüllen.</span><span class="sxs-lookup"><span data-stu-id="75d20-252">This cmdlet gets jobs that satisfy all of the conditions.</span></span>
<span data-ttu-id="75d20-253">Geben Sie eine Hashtabelle ein, in der die Schlüssel Auftragseigenschaften und die Werte Werte der Auftragseigenschaften sind.</span><span class="sxs-lookup"><span data-stu-id="75d20-253">Enter a hash table where the keys are job properties and the values are job property values.</span></span>

<span data-ttu-id="75d20-254">Dieser Parameter funktioniert nur mit benutzerdefinierten Auftragstypen, z. B. Workflowaufträgen und geplanten Aufträgen.</span><span class="sxs-lookup"><span data-stu-id="75d20-254">This parameter works only on custom job types, such as workflow jobs and scheduled jobs.</span></span>
<span data-ttu-id="75d20-255">Es funktioniert nicht bei standardmäßigen Hintergrund Aufträgen, wie z. b. bei der Verwendung des Cmdlets **Start-Job** .</span><span class="sxs-lookup"><span data-stu-id="75d20-255">It does not work on standard background jobs, such as those created by using the **Start-Job** cmdlet.</span></span>
<span data-ttu-id="75d20-256">Weitere Informationen zur Unterstützung für diesen Parameter finden Sie unter dem Hilfethema für den Auftragstyp.</span><span class="sxs-lookup"><span data-stu-id="75d20-256">For information about support for this parameter, see the help topic for the job type.</span></span>

<span data-ttu-id="75d20-257">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="75d20-257">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Collections.Hashtable
Parameter Sets: FilterParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="75d20-258">-Hasmoredata</span><span class="sxs-lookup"><span data-stu-id="75d20-258">-HasMoreData</span></span>

<span data-ttu-id="75d20-259">Gibt an, ob dieses Cmdlet nur Aufträge mit dem angegebenen **hasmoredata** -Eigenschafts Wert abruft.</span><span class="sxs-lookup"><span data-stu-id="75d20-259">Indicates whether this cmdlet gets only jobs that have the specified **HasMoreData** property value.</span></span>
<span data-ttu-id="75d20-260">Die **HasMoreData** -Eigenschaft gibt an, ob alle Auftragsergebnisse in der aktuellen Sitzung empfangen wurden.</span><span class="sxs-lookup"><span data-stu-id="75d20-260">The **HasMoreData** property indicates whether all job results have been received in the current session.</span></span>
<span data-ttu-id="75d20-261">Um Aufträge mit weiteren Ergebnissen zu erhalten, geben Sie den Wert $true an.</span><span class="sxs-lookup"><span data-stu-id="75d20-261">To get jobs that have more results, specify a value of $True.</span></span>
<span data-ttu-id="75d20-262">Um Aufträge zu erhalten, die keine weiteren Ergebnisse aufweisen, geben Sie den Wert $false an.</span><span class="sxs-lookup"><span data-stu-id="75d20-262">To get jobs that do not have more results, specify a value of $False.</span></span>

<span data-ttu-id="75d20-263">Verwenden Sie das Cmdlet "Receive-Job", um die Ergebnisse eines Auftrags zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="75d20-263">To get the results of a job, use the Receive-Job cmdlet.</span></span>

<span data-ttu-id="75d20-264">Wenn Sie das **Receive-Job-** Cmdlet verwenden, löscht es die zurückgegebenen Ergebnisse aus dem in-Memory-Sitzungs spezifischen Speicher.</span><span class="sxs-lookup"><span data-stu-id="75d20-264">When you use the **Receive-Job** cmdlet, it deletes from its in-memory, session-specific storage the results that it returned.</span></span> <span data-ttu-id="75d20-265">Wenn alle Ergebnisse des Auftrags in der aktuellen Sitzung zurückgegeben wurden, wird der Wert der **hasmoredata** -Eigenschaft des Auftrags auf $false) festgelegt, um anzugeben, dass keine weiteren Ergebnisse für den Auftrag in der aktuellen Sitzung angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="75d20-265">When it has returned all results of the job in the current session, it sets the value of the **HasMoreData** property of the job to $False) to indicate that it has no more results for the job in the current session.</span></span> <span data-ttu-id="75d20-266">Verwenden Sie den *Keep* -Parameter von **Receive-Job** , um zu verhindern, dass **Receive-Job** Ergebnisse löscht und den Wert der **HasMoreData** -Eigenschaft ändert.</span><span class="sxs-lookup"><span data-stu-id="75d20-266">Use the *Keep* parameter of **Receive-Job** to prevent **Receive-Job** from deleting results and changing the value of the **HasMoreData** property.</span></span> <span data-ttu-id="75d20-267">Geben Sie Folgendes ein, um weitere Informationen zu erhalten: `Get-Help Receive-Job`.</span><span class="sxs-lookup"><span data-stu-id="75d20-267">For more information, type `Get-Help Receive-Job`.</span></span>

<span data-ttu-id="75d20-268">Die **HasMoreData** -Eigenschaft ist für die aktuelle Sitzung spezifisch.</span><span class="sxs-lookup"><span data-stu-id="75d20-268">The **HasMoreData** property is specific to the current session.</span></span> <span data-ttu-id="75d20-269">Wenn die Ergebnisse für einen benutzerdefinierten Auftragstyp außerhalb der Sitzung gespeichert werden, wie z. b. der geplante Auftragstyp, der Auftrags Ergebnisse auf dem Datenträger speichert, können Sie das **Receive-Job-** Cmdlet in einer anderen Sitzung verwenden, um die Auftrags Ergebnisse zu erhalten, auch wenn der Wert von **hasmoredata** $false ist.</span><span class="sxs-lookup"><span data-stu-id="75d20-269">If results for a custom job type are saved outside of the session, such as the scheduled job type, which saves job results on disk, you can use the **Receive-Job** cmdlet in a different session to get the job results again, even if the value of **HasMoreData** is $False.</span></span> <span data-ttu-id="75d20-270">Weitere Informationen finden Sie in den Hilfethemen für den benutzerdefinierten Auftragstyp.</span><span class="sxs-lookup"><span data-stu-id="75d20-270">For more information, see the help topics for the custom job type.</span></span>

<span data-ttu-id="75d20-271">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="75d20-271">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Boolean
Parameter Sets: SessionIdParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet, CommandParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="75d20-272">-Id</span><span class="sxs-lookup"><span data-stu-id="75d20-272">-Id</span></span>

<span data-ttu-id="75d20-273">Gibt ein Array von IDs von Aufträgen an, die von diesem Cmdlet abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="75d20-273">Specifies an array of IDs of jobs that this cmdlet gets.</span></span>

<span data-ttu-id="75d20-274">Die ID ist eine Ganzzahl, die den Auftrag in der aktuellen Sitzung eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="75d20-274">The ID is an integer that uniquely identifies the job in the current session.</span></span>
<span data-ttu-id="75d20-275">Es ist einfacher, sich zu merken und als die Instanz-ID einzugeben, aber es ist nur in der aktuellen Sitzung eindeutig.</span><span class="sxs-lookup"><span data-stu-id="75d20-275">It is easier to remember and to type than the instance ID, but it is unique only in the current session.</span></span>
<span data-ttu-id="75d20-276">Sie können eine oder mehrere durch Kommas getrennte IDs eingeben.</span><span class="sxs-lookup"><span data-stu-id="75d20-276">You can type one or more IDs separated by commas.</span></span>
<span data-ttu-id="75d20-277">Um die ID eines Auftrags zu ermitteln, geben Sie `Get-Job` ohne Parameter ein.</span><span class="sxs-lookup"><span data-stu-id="75d20-277">To find the ID of a job, type `Get-Job` without parameters.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: SessionIdParameterSet
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="75d20-278">-Incluentchildjob</span><span class="sxs-lookup"><span data-stu-id="75d20-278">-IncludeChildJob</span></span>

<span data-ttu-id="75d20-279">Gibt an, dass dieses Cmdlet neben den übergeordneten Aufträgen auch untergeordnete Aufträge zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="75d20-279">Indicates that this cmdlet returns child jobs, in addition to parent jobs.</span></span>

<span data-ttu-id="75d20-280">Dieser Parameter ist besonders nützlich für die Untersuchung von Workflow Aufträgen, für die **Get-Job** einen übergeordneten Container Auftrag zurückgibt, sowie für Auftrags Fehler, da der Grund für den Fehler in einer Eigenschaft des untergeordneten Auftrags gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="75d20-280">This parameter is especially useful for investigating workflow jobs, for which **Get-Job** returns a container parent job, and job failures, because the reason for the failure is saved in a property of the child job.</span></span>

<span data-ttu-id="75d20-281">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="75d20-281">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: SessionIdParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet, CommandParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="75d20-282">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="75d20-282">-InstanceId</span></span>

<span data-ttu-id="75d20-283">Gibt ein Array von Instanz-IDs von Aufträgen an, die von diesem Cmdlet abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="75d20-283">Specifies an array of instance IDs of jobs that this cmdlet gets.</span></span>
<span data-ttu-id="75d20-284">Standardmäßig werden alle Aufträge fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="75d20-284">The default is all jobs.</span></span>

<span data-ttu-id="75d20-285">Eine Instanz-ID ist eine GUID, die den Auftrag auf dem Computer eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="75d20-285">An instance ID is a GUID that uniquely identifies the job on the computer.</span></span>
<span data-ttu-id="75d20-286">Zum Ermitteln der Instanz-ID eines Auftrags verwenden Sie **Get-Job** .</span><span class="sxs-lookup"><span data-stu-id="75d20-286">To find the instance ID of a job, use **Get-Job** .</span></span>

```yaml
Type: System.Guid[]
Parameter Sets: InstanceIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="75d20-287">-Name</span><span class="sxs-lookup"><span data-stu-id="75d20-287">-Name</span></span>

<span data-ttu-id="75d20-288">Gibt ein Array von instanzfreundlichen Namen von Aufträgen an, die von diesem Cmdlet abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="75d20-288">Specifies an array of instance friendly names of jobs that this cmdlet gets.</span></span>
<span data-ttu-id="75d20-289">Geben Sie einen Auftragsnamen ein, oder verwenden Sie Platzhalterzeichen, um ein Auftragsnamensmuster einzugeben.</span><span class="sxs-lookup"><span data-stu-id="75d20-289">Enter a job name, or use wildcard characters to enter a job name pattern.</span></span>
<span data-ttu-id="75d20-290">Standardmäßig ruft **Get-Job** alle Aufträge in der aktuellen Sitzung ab.</span><span class="sxs-lookup"><span data-stu-id="75d20-290">By default, **Get-Job** gets all jobs in the current session.</span></span>

```yaml
Type: System.String[]
Parameter Sets: NameParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="75d20-291">-Latest</span><span class="sxs-lookup"><span data-stu-id="75d20-291">-Newest</span></span>

<span data-ttu-id="75d20-292">Gibt eine Anzahl von Aufträgen an, die erhalten werden.</span><span class="sxs-lookup"><span data-stu-id="75d20-292">Specifies a number of jobs to get.</span></span>
<span data-ttu-id="75d20-293">Dieses Cmdlet ruft die Aufträge ab, die zuletzt beendet wurden.</span><span class="sxs-lookup"><span data-stu-id="75d20-293">This cmdlet gets the jobs that ended most recently.</span></span>

<span data-ttu-id="75d20-294">Die letzten Aufträge werden vom *Newest* -Parameter nicht in der Reihenfolge ihrer Endezeit sortiert oder zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="75d20-294">The *Newest* parameter does not sort or return the newest jobs in end-time order.</span></span>
<span data-ttu-id="75d20-295">Um die Ausgabe zu sortieren, verwenden Sie das Cmdlet "Sort-Object".</span><span class="sxs-lookup"><span data-stu-id="75d20-295">To sort the output, use the Sort-Object cmdlet.</span></span>

<span data-ttu-id="75d20-296">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="75d20-296">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Int32
Parameter Sets: SessionIdParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet, CommandParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="75d20-297">-State</span><span class="sxs-lookup"><span data-stu-id="75d20-297">-State</span></span>

<span data-ttu-id="75d20-298">Gibt einen Auftragsstatus an.</span><span class="sxs-lookup"><span data-stu-id="75d20-298">Specifies a job state.</span></span>
<span data-ttu-id="75d20-299">Dieses Cmdlet ruft nur Aufträge im angegebenen Zustand ab.</span><span class="sxs-lookup"><span data-stu-id="75d20-299">This cmdlet gets only jobs in the specified state.</span></span>
<span data-ttu-id="75d20-300">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="75d20-300">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="75d20-301">NotStarted</span><span class="sxs-lookup"><span data-stu-id="75d20-301">NotStarted</span></span>
- <span data-ttu-id="75d20-302">Wird ausgeführt</span><span class="sxs-lookup"><span data-stu-id="75d20-302">Running</span></span>
- <span data-ttu-id="75d20-303">Abgeschlossen</span><span class="sxs-lookup"><span data-stu-id="75d20-303">Completed</span></span>
- <span data-ttu-id="75d20-304">Fehler</span><span class="sxs-lookup"><span data-stu-id="75d20-304">Failed</span></span>
- <span data-ttu-id="75d20-305">Beendet</span><span class="sxs-lookup"><span data-stu-id="75d20-305">Stopped</span></span>
- <span data-ttu-id="75d20-306">Blockiert</span><span class="sxs-lookup"><span data-stu-id="75d20-306">Blocked</span></span>
- <span data-ttu-id="75d20-307">Ausgesetzt</span><span class="sxs-lookup"><span data-stu-id="75d20-307">Suspended</span></span>
- <span data-ttu-id="75d20-308">Getrennt</span><span class="sxs-lookup"><span data-stu-id="75d20-308">Disconnected</span></span>
- <span data-ttu-id="75d20-309">Wird angehalten</span><span class="sxs-lookup"><span data-stu-id="75d20-309">Suspending</span></span>
- <span data-ttu-id="75d20-310">Wird beendet</span><span class="sxs-lookup"><span data-stu-id="75d20-310">Stopping</span></span>

<span data-ttu-id="75d20-311">Standardmäßig ruft **Get-Job** alle Aufträge in der aktuellen Sitzung ab.</span><span class="sxs-lookup"><span data-stu-id="75d20-311">By default, **Get-Job** gets all the jobs in the current session.</span></span>

<span data-ttu-id="75d20-312">Weitere Informationen zu Auftrags Zuständen finden Sie unter [jobstate-Enumeration](https://msdn.microsoft.com/library/system.management.automation.jobstate) in der MSDN Library.</span><span class="sxs-lookup"><span data-stu-id="75d20-312">For more information about job states, see [JobState Enumeration](https://msdn.microsoft.com/library/system.management.automation.jobstate) in the MSDN library.</span></span>

```yaml
Type: System.Management.Automation.JobState
Parameter Sets: StateParameterSet
Aliases:
Accepted values: NotStarted, Running, Completed, Failed, Stopped, Blocked, Suspended, Disconnected, Suspending, Stopping, AtBreakpoint

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="75d20-313">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="75d20-313">CommonParameters</span></span>

<span data-ttu-id="75d20-314">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="75d20-314">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="75d20-315">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="75d20-315">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="75d20-316">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="75d20-316">INPUTS</span></span>

### <span data-ttu-id="75d20-317">Keine</span><span class="sxs-lookup"><span data-stu-id="75d20-317">None</span></span>

<span data-ttu-id="75d20-318">Eingaben können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="75d20-318">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="75d20-319">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="75d20-319">OUTPUTS</span></span>

### <span data-ttu-id="75d20-320">System. Management. Automation. remotingjob</span><span class="sxs-lookup"><span data-stu-id="75d20-320">System.Management.Automation.RemotingJob</span></span>

<span data-ttu-id="75d20-321">Dieses Cmdlet gibt Objekte zurück, die die Aufträge in der Sitzung darstellen.</span><span class="sxs-lookup"><span data-stu-id="75d20-321">This cmdlet returns objects that represent the jobs in the session.</span></span>

## <span data-ttu-id="75d20-322">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="75d20-322">NOTES</span></span>

* <span data-ttu-id="75d20-323">Die **PSJobTypeName** -Eigenschaft von Aufträgen gibt den Auftragstyp des Auftrags an.</span><span class="sxs-lookup"><span data-stu-id="75d20-323">The **PSJobTypeName** property of jobs indicates the job type of the job.</span></span> <span data-ttu-id="75d20-324">Der Eigenschaftswert wird vom Autor des Auftragstyps bestimmt.</span><span class="sxs-lookup"><span data-stu-id="75d20-324">The property value is determined by the job type author.</span></span> <span data-ttu-id="75d20-325">Die folgende Liste enthält allgemeine Auftragstypen.</span><span class="sxs-lookup"><span data-stu-id="75d20-325">The following list shows common job types.</span></span>

  - <span data-ttu-id="75d20-326">**Backgroundjob** .</span><span class="sxs-lookup"><span data-stu-id="75d20-326">**BackgroundJob** .</span></span>
<span data-ttu-id="75d20-327">Lokaler Auftrag wurde mithilfe von **Start-Job** gestartet.</span><span class="sxs-lookup"><span data-stu-id="75d20-327">Local job started by using **Start-Job** .</span></span>

  - <span data-ttu-id="75d20-328">**Remotejob** .</span><span class="sxs-lookup"><span data-stu-id="75d20-328">**RemoteJob** .</span></span>
<span data-ttu-id="75d20-329">Der Auftrag wurde in einer **PSSession** mithilfe des *AsJob* -Parameters des Invoke-Command-Cmdlets gestartet.</span><span class="sxs-lookup"><span data-stu-id="75d20-329">Job started in a **PSSession** by using the *AsJob* parameter of the Invoke-Command cmdlet.</span></span>

  - <span data-ttu-id="75d20-330">**Psworkflowjob** .</span><span class="sxs-lookup"><span data-stu-id="75d20-330">**PSWorkflowJob** .</span></span>
<span data-ttu-id="75d20-331">Auftrag, der mit dem allgemeinen *AsJob* -Parameter von Workflows gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="75d20-331">Job started by using the *AsJob* common parameter of workflows.</span></span>

## <span data-ttu-id="75d20-332">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="75d20-332">RELATED LINKS</span></span>

[<span data-ttu-id="75d20-333">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="75d20-333">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="75d20-334">Receive-Job</span><span class="sxs-lookup"><span data-stu-id="75d20-334">Receive-Job</span></span>](Receive-Job.md)

[<span data-ttu-id="75d20-335">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="75d20-335">Remove-Job</span></span>](Remove-Job.md)

[<span data-ttu-id="75d20-336">Start-Job</span><span class="sxs-lookup"><span data-stu-id="75d20-336">Start-Job</span></span>](Start-Job.md)

[<span data-ttu-id="75d20-337">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="75d20-337">Stop-Job</span></span>](Stop-Job.md)

[<span data-ttu-id="75d20-338">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="75d20-338">Wait-Job</span></span>](Wait-Job.md)