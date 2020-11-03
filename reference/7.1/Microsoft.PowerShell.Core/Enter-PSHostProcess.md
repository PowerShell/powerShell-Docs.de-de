---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 07/23/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/enter-pshostprocess?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enter-PSHostProcess
ms.openlocfilehash: 14f6173e318c6abd223ddff85a3694cfaac75c93
ms.sourcegitcommit: 9dddf1d2e91ebcd347fcfb7bf6ef670d49a12ab7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2020
ms.locfileid: "93218967"
---
# <span data-ttu-id="7916a-103">Enter-PSHostProcess</span><span class="sxs-lookup"><span data-stu-id="7916a-103">Enter-PSHostProcess</span></span>

## <span data-ttu-id="7916a-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="7916a-104">SYNOPSIS</span></span>
<span data-ttu-id="7916a-105">Stellt eine Verbindung mit einer interaktiven Sitzung mit einem lokalen Prozess her und wechselt in diese.</span><span class="sxs-lookup"><span data-stu-id="7916a-105">Connects to and enters into an interactive session with a local process.</span></span>

## <span data-ttu-id="7916a-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="7916a-106">SYNTAX</span></span>

### <span data-ttu-id="7916a-107">Processidparameterset (Standard)</span><span class="sxs-lookup"><span data-stu-id="7916a-107">ProcessIdParameterSet (Default)</span></span>

```
Enter-PSHostProcess [-Id] <Int32> [[-AppDomainName] <String>] [<CommonParameters>]
```

### <span data-ttu-id="7916a-108">Processparameterset</span><span class="sxs-lookup"><span data-stu-id="7916a-108">ProcessParameterSet</span></span>

```
Enter-PSHostProcess [-Process] <Process> [[-AppDomainName] <String>] [<CommonParameters>]
```

### <span data-ttu-id="7916a-109">Processnameparameterset</span><span class="sxs-lookup"><span data-stu-id="7916a-109">ProcessNameParameterSet</span></span>

```
Enter-PSHostProcess [-Name] <String> [[-AppDomainName] <String>] [<CommonParameters>]
```

### <span data-ttu-id="7916a-110">Pshostprocessinfonoparameterset</span><span class="sxs-lookup"><span data-stu-id="7916a-110">PSHostProcessInfoParameterSet</span></span>

```
Enter-PSHostProcess [-HostProcessInfo] <PSHostProcessInfo> [[-AppDomainName] <String>]
 [<CommonParameters>]
```

### <span data-ttu-id="7916a-111">Pipameparameterset</span><span class="sxs-lookup"><span data-stu-id="7916a-111">PipeNameParameterSet</span></span>

```
Enter-PSHostProcess -CustomPipeName <String> [<CommonParameters>]
```

## <span data-ttu-id="7916a-112">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7916a-112">DESCRIPTION</span></span>

<span data-ttu-id="7916a-113">`Enter-PSHostProcess`Mit dem-Cmdlet wird eine Verbindung mit einer interaktiven Sitzung hergestellt und mit einem lokalen Prozess verknüpft.</span><span class="sxs-lookup"><span data-stu-id="7916a-113">The `Enter-PSHostProcess` cmdlet connects to and enters into an interactive session with a local process.</span></span> <span data-ttu-id="7916a-114">Ab PowerShell 6,2 wird dieses Cmdlet auf nicht-Windows-Plattformen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7916a-114">Beginning in PowerShell 6.2, this cmdlet is supported on non-Windows platforms.</span></span>

<span data-ttu-id="7916a-115">Anstatt einen neuen Prozess zum Hosten von PowerShell zu erstellen und eine Remote Sitzung auszuführen, wird die interaktive Remote Sitzung in einem vorhandenen Prozess ausgeführt, auf dem bereits PowerShell ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="7916a-115">Instead of creating a new process to host PowerShell and run a remote session, the remote, interactive session is run in an existing process that is already running PowerShell.</span></span> <span data-ttu-id="7916a-116">Wenn Sie mit einer Remote Sitzung für einen angegebenen Prozess interagieren, können Sie laufende Runspaces auflisten und dann einen zu debuggenden Runspace auswählen, indem Sie entweder `Debug-Runspace` oder Ausführen `Enable-RunspaceDebug` .</span><span class="sxs-lookup"><span data-stu-id="7916a-116">When you are interacting with a remote session on a specified process, you can enumerate running runspaces, and then select a runspace to debug by running either `Debug-Runspace` or `Enable-RunspaceDebug`.</span></span>

<span data-ttu-id="7916a-117">Für den Prozess, den Sie eingeben möchten, muss PowerShell (System.Management.Automation.dll) gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="7916a-117">The process that you want to enter must be hosting PowerShell (System.Management.Automation.dll).</span></span>
<span data-ttu-id="7916a-118">Sie müssen entweder Mitglied der Gruppe "Administratoren" auf dem Computer sein, auf dem der Prozess gefunden wurde, oder Sie müssen der Benutzer sein, der das Skript ausgeführt hat, das den Prozess gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="7916a-118">You must be either a member of the Administrators group on the computer on which the process is found, or you must be the user who is running the script that started the process.</span></span>

<span data-ttu-id="7916a-119">Nachdem Sie einen zu debuggenden Runspace ausgewählt haben, wird eine remotedebuggingsitzung für den Runspace geöffnet, wenn Sie entweder einen Befehl ausführen oder im Debugger angehalten wird.</span><span class="sxs-lookup"><span data-stu-id="7916a-119">After you have selected a runspace to debug, a remote debug session is opened for the runspace if it is either currently running a command or is stopped in the debugger.</span></span> <span data-ttu-id="7916a-120">Anschließend können Sie das Runspace-Skript genauso Debuggen wie andere Remote Sitzungs Skripts.</span><span class="sxs-lookup"><span data-stu-id="7916a-120">You can then debug the runspace script in the same way you would debug other remote session scripts.</span></span>

<span data-ttu-id="7916a-121">Trennen Sie von einer Debugsitzung und dann der interaktiven Sitzung mit dem Prozess, indem Sie "beenden" zweimal ausführen, oder beenden Sie die Ausführung des Skripts, indem Sie den vorhandenen Debugger beenden-Befehl ausführen.</span><span class="sxs-lookup"><span data-stu-id="7916a-121">Detach from a debugging session, and then the interactive session with the process, by running exit twice, or stop script execution by running the existing debugger quit command.</span></span>

<span data-ttu-id="7916a-122">Wenn Sie einen Prozess mithilfe des **Name** -Parameters angeben und nur ein Prozess mit dem angegebenen Namen gefunden wird, wird der Prozess eingegeben.</span><span class="sxs-lookup"><span data-stu-id="7916a-122">If you specify a process by using the **Name** parameter, and there is only one process found with the specified name, the process is entered.</span></span> <span data-ttu-id="7916a-123">Wenn mehr als ein Prozess mit dem angegebenen Namen gefunden wird, gibt PowerShell einen Fehler zurück und listet alle Prozesse mit dem angegebenen Namen auf.</span><span class="sxs-lookup"><span data-stu-id="7916a-123">If more than one process with the specified name is found, PowerShell returns an error, and lists all processes found with the specified name.</span></span>

<span data-ttu-id="7916a-124">Um das Anfügen an Prozesse auf Remote Computern zu unterstützen, `Enter-PSHostProcess` ist das Cmdlet auf einem angegebenen Remote Computer aktiviert, sodass Sie einen lokalen Prozess innerhalb einer PowerShell-Remote Sitzung anfügen können.</span><span class="sxs-lookup"><span data-stu-id="7916a-124">To support attaching to processes on remote computers, the `Enter-PSHostProcess` cmdlet is enabled in a specified remote computer, so that you can attach to a local process within a remote PowerShell session.</span></span>

## <span data-ttu-id="7916a-125">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="7916a-125">EXAMPLES</span></span>

### <span data-ttu-id="7916a-126">Beispiel 1: Starten des Debuggens eines Runspace innerhalb des PowerShell ISE-Prozesses</span><span class="sxs-lookup"><span data-stu-id="7916a-126">Example 1: Start debugging a runspace within the PowerShell ISE process</span></span>

<span data-ttu-id="7916a-127">In diesem Beispiel führen Sie in `Enter-PSHostProcess` der PowerShell-Konsole aus, um den PowerShell ISE-Prozess einzugeben.</span><span class="sxs-lookup"><span data-stu-id="7916a-127">In this example, you run `Enter-PSHostProcess` from within the PowerShell console to enter the PowerShell ISE process.</span></span> <span data-ttu-id="7916a-128">In der sich ergebenden interaktiven Sitzung finden Sie einen Runspace, den Sie debuggen möchten, indem Sie Ausführen `Get-Runspace` und dann den Runspace Debuggen.</span><span class="sxs-lookup"><span data-stu-id="7916a-128">In the resulting interactive session, you can find a runspace that you want to debug by running `Get-Runspace`, and then debug the runspace.</span></span>

```
PS C:\> Enter-PSHostProcess -Name powershell_ise
[Process:1520]: PS C:\Test\Documents>

Next, get available runspaces within the process you have entered.
PS C:\> [Process:1520]: PS C:\>  Get-Runspace
Id    Name          InstanceId                               State           Availability
--    -------       -----------                              ------          -------------
1     Runspace1     2d91211d-9cce-42f0-ab0e-71ac258b32b5     Opened          Available
2     Runspace2     a3855043-cb16-424a-a616-685360c3763b     Opened          RemoteDebug
3     MyLocalRS     2236dbd8-2105-4dec-a15a-a27d0bfaacb5     Opened          LocalDebug
4     MyRunspace    771356e9-8c44-4b70-9de5-dd17cb41e48e     Opened          Busy
5     Runspace8     3e517382-a97a-49ba-9c3c-fd21f6664288     Broken          None

The runspace objects returned by Get-Runspace also have a NoteProperty called ScriptStackTrace of
the running command stack, if available.Next, debug runspace ID 4, that is running another user's
long-running script. From the list returned from Get-Runspace, note that the runspace state is
Opened, and Availability is Busy, meaning that the runspace is still running the long-running
script.

PS C:\> [Process:1520]: PS C:\>  (Get-Runspace -Id 4).ScriptStackTrace
Command                    Arguments                           Location
-------                    ---------                           --------
MyModuleWorkflowF1         {}                                  TestNoFile3.psm1: line 6
WFTest1                    {}                                  TestNoFile2.ps1: line 14
TestNoFile2.ps1            {}                                  TestNoFile2.ps1: line 22
<ScriptBlock>              {}                                  <No file>

Start an interactive debugging session with this runspace by running the Debug-Runspace cmdlet.

PS C:\> [Process: 1520]: PS C:\>  Debug-Runspace -Id 4
Hit Line breakpoint on 'C:\TestWFVar1.ps1:83'

At C:\TestWFVar1.ps1:83 char:1
+ $scriptVar = "Script Variable"
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

[Process: 1520]: [RSDBG: 4]: PS C:\> >

After you are finished debugging, allow the script to continue running without the debugger attached
by running the exit debugger command. Alternatively, you can quit the debugger with the q or Stop
commands.

PS C:\> [Process:346]: [RSDBG: 3]: PS C:\> > exit
[Process:1520]: PS C:\>

When you are finished working in the process, exit the process by running the Exit-PSHostProcess
cmdlet. This returns you to the PS C:\> prompt.

PS C:\> [Process:1520]: PS C:\>  Exit-PSHostProcess
PS C:\>
```

## <span data-ttu-id="7916a-129">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="7916a-129">PARAMETERS</span></span>

### <span data-ttu-id="7916a-130">-Appdomainname</span><span class="sxs-lookup"><span data-stu-id="7916a-130">-AppDomainName</span></span>

<span data-ttu-id="7916a-131">Gibt einen Anwendungs **Domänen Namen** an, mit dem eine Verbindung hergestellt werden soll, wenn dieser nicht angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="7916a-131">Specifies an application domain name to connect to if omitted, uses **DefaultAppDomain**.</span></span> <span data-ttu-id="7916a-132">Verwenden `Get-PSHostProcessInfo` Sie, um die Anwendungs Domänen Namen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="7916a-132">Use `Get-PSHostProcessInfo` to display the application domain names.</span></span>

```yaml
Type: System.String
Parameter Sets: ProcessIdParameterSet, ProcessParameterSet, ProcessNameParameterSet, PSHostProcessInfoParameterSet
Aliases:

Required: False
Position: 1
Default value: DefaultAppDomain
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7916a-133">-Hostprocessinfo</span><span class="sxs-lookup"><span data-stu-id="7916a-133">-HostProcessInfo</span></span>

<span data-ttu-id="7916a-134">Gibt ein **pshostprocessinfo** -Objekt an, das mit PowerShell verbunden werden kann.</span><span class="sxs-lookup"><span data-stu-id="7916a-134">Specifies a **PSHostProcessInfo** object that can be connected to with PowerShell.</span></span> <span data-ttu-id="7916a-135">Verwenden `Get-PSHostProcessInfo` Sie, um das-Objekt zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="7916a-135">Use `Get-PSHostProcessInfo` to get the object.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.PSHostProcessInfo
Parameter Sets: PSHostProcessInfoParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="7916a-136">-Id</span><span class="sxs-lookup"><span data-stu-id="7916a-136">-Id</span></span>

<span data-ttu-id="7916a-137">Gibt einen Prozess mit der Prozess-ID an.</span><span class="sxs-lookup"><span data-stu-id="7916a-137">Specifies a process by the process ID.</span></span> <span data-ttu-id="7916a-138">Führen Sie das-Cmdlet aus, um eine Prozess-ID zu erhalten `Get-Process` .</span><span class="sxs-lookup"><span data-stu-id="7916a-138">To get a process ID, run the `Get-Process` cmdlet.</span></span>

```yaml
Type: System.Int32
Parameter Sets: ProcessIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7916a-139">-Name</span><span class="sxs-lookup"><span data-stu-id="7916a-139">-Name</span></span>

<span data-ttu-id="7916a-140">Gibt einen Prozess anhand des Prozess namens an.</span><span class="sxs-lookup"><span data-stu-id="7916a-140">Specifies a process by the process name.</span></span> <span data-ttu-id="7916a-141">Um einen Prozessnamen zu erhalten, führen Sie das- `Get-Process` Cmdlet aus.</span><span class="sxs-lookup"><span data-stu-id="7916a-141">To get a process name, run the `Get-Process` cmdlet.</span></span> <span data-ttu-id="7916a-142">Sie können Prozessnamen auch aus dem Dialogfeld Eigenschaften eines Prozesses im Task-Manager erhalten.</span><span class="sxs-lookup"><span data-stu-id="7916a-142">You can also get process names from the Properties dialog box of a process in Task Manager.</span></span>

```yaml
Type: System.String
Parameter Sets: ProcessNameParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7916a-143">-Prozess</span><span class="sxs-lookup"><span data-stu-id="7916a-143">-Process</span></span>

<span data-ttu-id="7916a-144">Gibt einen Prozess vom Prozess Objekt an.</span><span class="sxs-lookup"><span data-stu-id="7916a-144">Specifies a process by the process object.</span></span> <span data-ttu-id="7916a-145">Die einfachste Möglichkeit, diesen Parameter zu verwenden, besteht darin, die Ergebnisse eines Befehls zu speichern, der den `Get-Process` Prozess zurückgibt, den Sie in eine Variable eingeben möchten, und dann die Variable als Wert dieses Parameters anzugeben.</span><span class="sxs-lookup"><span data-stu-id="7916a-145">The simplest way to use this parameter is to save the results of a `Get-Process` command that returns process that you want to enter in a variable, and then specify the variable as the value of this parameter.</span></span>

```yaml
Type: System.Diagnostics.Process
Parameter Sets: ProcessParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="7916a-146">-Custompipame</span><span class="sxs-lookup"><span data-stu-id="7916a-146">-CustomPipeName</span></span>

<span data-ttu-id="7916a-147">Ruft den Namen des benutzerdefinierten Named Pipe für die Verbindung ab oder legt ihn fest.</span><span class="sxs-lookup"><span data-stu-id="7916a-147">Gets or sets the custom named pipe name to connect to.</span></span> <span data-ttu-id="7916a-148">Dies wird in der Regel in Verbindung mit verwendet `pwsh -CustomPipeName` .</span><span class="sxs-lookup"><span data-stu-id="7916a-148">This is usually used in conjunction with `pwsh -CustomPipeName`.</span></span>

<span data-ttu-id="7916a-149">Dieser Parameter wurde in PowerShell 6,2 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="7916a-149">This parameter was introduced in PowerShell 6.2.</span></span>

```yaml
Type: System.String
Parameter Sets: PipeNameParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7916a-150">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="7916a-150">CommonParameters</span></span>

<span data-ttu-id="7916a-151">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="7916a-151">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="7916a-152">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="7916a-152">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="7916a-153">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="7916a-153">INPUTS</span></span>

### <span data-ttu-id="7916a-154">System.Diagnostics.Process</span><span class="sxs-lookup"><span data-stu-id="7916a-154">System.Diagnostics.Process</span></span>

## <span data-ttu-id="7916a-155">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="7916a-155">OUTPUTS</span></span>

## <span data-ttu-id="7916a-156">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="7916a-156">NOTES</span></span>

<span data-ttu-id="7916a-157">`Enter-PSHostProcess` der Vorgang kann nicht in die PowerShell-Sitzung eingegeben werden, in der Sie den Befehl ausführen.</span><span class="sxs-lookup"><span data-stu-id="7916a-157">`Enter-PSHostProcess` cannot enter the process of the PowerShell session in which you are running the command.</span></span> <span data-ttu-id="7916a-158">Sie können jedoch den Prozess einer anderen PowerShell-Sitzung oder eine PowerShell ISE-Sitzung eingeben, die zur gleichen Zeit wie die Sitzung ausgeführt wird, in der Sie ausgeführt werden `Enter-PSHostProcess` .</span><span class="sxs-lookup"><span data-stu-id="7916a-158">You can, however, enter the process of another PowerShell session, or a PowerShell ISE session that is running at the same time as the session in which you are running `Enter-PSHostProcess`.</span></span>

<span data-ttu-id="7916a-159">`Enter-PSHostProcess` Es können nur die Prozesse eingegeben werden, von denen PowerShell gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="7916a-159">`Enter-PSHostProcess` can enter only those processes that are hosting PowerShell.</span></span> <span data-ttu-id="7916a-160">Das heißt, Sie haben das PowerShell-Modul geladen.</span><span class="sxs-lookup"><span data-stu-id="7916a-160">That is, they have loaded the PowerShell engine.</span></span>

<span data-ttu-id="7916a-161">Um einen Prozess innerhalb des Prozesses zu beenden, geben Sie **Exit** ein, und drücken Sie dann die <kbd>Eingabe</kbd>Taste.</span><span class="sxs-lookup"><span data-stu-id="7916a-161">To exit a process from within the process, type **exit** , and then press <kbd>Enter</kbd>.</span></span>

<span data-ttu-id="7916a-162">Vor PowerShell 7.1 unterstützte das Remoting über SSH keine Remotesitzungen über einen zweiten Hop.</span><span class="sxs-lookup"><span data-stu-id="7916a-162">Prior to PowerShell 7.1, remoting over SSH did not support second-hop remote sessions.</span></span> <span data-ttu-id="7916a-163">Diese Funktion war auf Sitzungen beschränkt, die WinRM verwendeten.</span><span class="sxs-lookup"><span data-stu-id="7916a-163">This capability was limited to sessions using WinRM.</span></span> <span data-ttu-id="7916a-164">PowerShell 7.1 ermöglicht, dass `Enter-PSSession` und `Enter-PSHostProcess` in jeder interaktiven Remotesitzung funktionieren.</span><span class="sxs-lookup"><span data-stu-id="7916a-164">PowerShell 7.1 allows `Enter-PSSession` and `Enter-PSHostProcess` to work from within any interactive remote session.</span></span>

## <span data-ttu-id="7916a-165">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="7916a-165">RELATED LINKS</span></span>

[<span data-ttu-id="7916a-166">Exit-PSHostProcess</span><span class="sxs-lookup"><span data-stu-id="7916a-166">Exit-PSHostProcess</span></span>](Exit-PSHostProcess.md)

[<span data-ttu-id="7916a-167">Get-PSHostProcessInfo</span><span class="sxs-lookup"><span data-stu-id="7916a-167">Get-PSHostProcessInfo</span></span>](Get-PSHostProcessInfo.md)
