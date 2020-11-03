---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 07/16/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/enable-psremoting?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-PSRemoting
ms.openlocfilehash: f74fe88cfb1d89e2f21d3f85e5c604d75f8ac55d
ms.sourcegitcommit: 0e0f45d0d8deb8c9088a4f4a32218edde052b686
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/17/2020
ms.locfileid: "93218031"
---
# <span data-ttu-id="6ef39-103">Enable-PSRemoting</span><span class="sxs-lookup"><span data-stu-id="6ef39-103">Enable-PSRemoting</span></span>

## <span data-ttu-id="6ef39-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="6ef39-104">SYNOPSIS</span></span>
<span data-ttu-id="6ef39-105">Konfiguriert den Computer für den Empfang von Remotebefehlen.</span><span class="sxs-lookup"><span data-stu-id="6ef39-105">Configures the computer to receive remote commands.</span></span>

## <span data-ttu-id="6ef39-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="6ef39-106">SYNTAX</span></span>

```
Enable-PSRemoting [-Force] [-SkipNetworkProfileCheck] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="6ef39-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="6ef39-107">DESCRIPTION</span></span>

<span data-ttu-id="6ef39-108">Das- `Enable-PSRemoting` Cmdlet konfiguriert den Computer für den Empfang von PowerShell-Remote Befehlen, die mithilfe der WS-Management-Technologie gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="6ef39-108">The `Enable-PSRemoting` cmdlet configures the computer to receive PowerShell remote commands that are sent by using the WS-Management technology.</span></span> <span data-ttu-id="6ef39-109">WS-Management basierte PowerShell-Remoting wird derzeit nur auf der Windows-Plattform unterstützt.</span><span class="sxs-lookup"><span data-stu-id="6ef39-109">WS-Management based PowerShell remoting is currently supported only on Windows platform.</span></span>

<span data-ttu-id="6ef39-110">PowerShell-Remoting ist auf Windows Server-Plattformen standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="6ef39-110">PowerShell remoting is enabled by default on Windows Server platforms.</span></span> <span data-ttu-id="6ef39-111">Sie können verwenden `Enable-PSRemoting` , um PowerShell-Remoting unter anderen unterstützten Versionen von Windows zu aktivieren und Remoting wieder zu aktivieren, wenn es deaktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="6ef39-111">You can use `Enable-PSRemoting` to enable PowerShell remoting on other supported versions of Windows and to re-enable remoting if it becomes disabled.</span></span>

<span data-ttu-id="6ef39-112">Sie müssen diesen Befehl nur einmal auf jedem Computer ausführen, der Befehle empfängt.</span><span class="sxs-lookup"><span data-stu-id="6ef39-112">You have to run this command only one time on each computer that will receive commands.</span></span> <span data-ttu-id="6ef39-113">Sie müssen Sie nicht auf Computern ausführen, auf denen nur Befehle gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="6ef39-113">You do not have to run it on computers that only send commands.</span></span> <span data-ttu-id="6ef39-114">Da die Konfiguration Listener startet, um Remote Verbindungen zu akzeptieren, ist es ratsam, Sie nur dort auszuführen, wo Sie benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="6ef39-114">Because the configuration starts listeners to accept remote connections, it is prudent to run it only where it is needed.</span></span>

<span data-ttu-id="6ef39-115">Das Aktivieren von PowerShell-Remoting unter Client Versionen von Windows, wenn sich der Computer in einem öffentlichen Netzwerk befindet, ist normalerweise nicht zulässig. Sie können diese Einschränkung jedoch überspringen, indem Sie den **skipnetworkprofilecheck** -Parameter verwenden.</span><span class="sxs-lookup"><span data-stu-id="6ef39-115">Enabling PowerShell remoting on client versions of Windows when the computer is on a public network is normally disallowed, but you can skip this restriction by using the **SkipNetworkProfileCheck** parameter.</span></span> <span data-ttu-id="6ef39-116">Weitere Informationen finden Sie in der Beschreibung des **SkipNetworkProfileCheck** -Parameters.</span><span class="sxs-lookup"><span data-stu-id="6ef39-116">For more information, see the description of the **SkipNetworkProfileCheck** parameter.</span></span>

<span data-ttu-id="6ef39-117">Mehrere PowerShell-Installationen können nebeneinander auf einem einzelnen Computer vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="6ef39-117">Multiple PowerShell installations can exist side-by-side on a single computer.</span></span> <span data-ttu-id="6ef39-118">Beim Ausführen `Enable-PSRemoting` von wird ein remotingendpunkt für die jeweilige Installationsversion konfiguriert, in der das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="6ef39-118">Running `Enable-PSRemoting` will configure a remoting endpoint for the specific installation version that you are running the cmdlet in.</span></span> <span data-ttu-id="6ef39-119">Wenn Sie also ausführen `Enable-PSRemoting` , während Sie PowerShell 6,2 ausführen, wird ein remotingendpunkt konfiguriert, der PowerShell 6,2 ausführt.</span><span class="sxs-lookup"><span data-stu-id="6ef39-119">So if you run `Enable-PSRemoting` while running PowerShell 6.2, a remoting endpoint will be configured that runs PowerShell 6.2.</span></span> <span data-ttu-id="6ef39-120">Wenn Sie `Enable-PSRemoting` während der Ausführung von PowerShell 7-Preview ausführen, wird ein remotingendpunkt konfiguriert, auf dem PowerShell 7 (Vorschau) ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="6ef39-120">If you run `Enable-PSRemoting` while running PowerShell 7-preview, a remoting endpoint will be configured that runs PowerShell 7-preview.</span></span>

<span data-ttu-id="6ef39-121">`Enable-PSRemoting` erstellt bei Bedarf zwei remoteend Punkt Konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="6ef39-121">`Enable-PSRemoting` creates two remoting endpoint configurations as needed.</span></span> <span data-ttu-id="6ef39-122">Wenn die Endpunkt Konfigurationen bereits vorhanden sind, werden Sie einfach für die Aktivierung sichergestellt.</span><span class="sxs-lookup"><span data-stu-id="6ef39-122">If the endpoint configurations already exist, then they are simply ensured to be enabled.</span></span> <span data-ttu-id="6ef39-123">Die erstellten Konfigurationen sind identisch, haben jedoch unterschiedliche Namen.</span><span class="sxs-lookup"><span data-stu-id="6ef39-123">The created configurations are identical but have different names.</span></span> <span data-ttu-id="6ef39-124">Eine erhält einen einfachen Namen, der der PowerShell-Version entspricht, die die Sitzung hostet.</span><span class="sxs-lookup"><span data-stu-id="6ef39-124">One will have a simple name corresponding to the PowerShell version that hosts the session.</span></span> <span data-ttu-id="6ef39-125">Der andere Konfigurations Name enthält ausführlichere Informationen über die PowerShell-Version, die die Sitzung hostet.</span><span class="sxs-lookup"><span data-stu-id="6ef39-125">The other configuration name contains more detailed information about the PowerShell version which hosts the session.</span></span> <span data-ttu-id="6ef39-126">Wenn Sie z. b `Enable-PSRemoting` . in PowerShell 6,2 ausgeführt werden, erhalten Sie zwei konfigurierte Endpunkte mit dem Namen **PowerShell. 6** , **PowerShell. 6.2.2**.</span><span class="sxs-lookup"><span data-stu-id="6ef39-126">For example, when running `Enable-PSRemoting` in PowerShell 6.2, you will get two configured endpoints named **PowerShell.6** , **PowerShell.6.2.2**.</span></span>
<span data-ttu-id="6ef39-127">Dies ermöglicht es Ihnen, mit dem einfachen Namen **PowerShell. 6** eine Verbindung mit der neuesten Version des PowerShell 6-Hosts herzustellen.</span><span class="sxs-lookup"><span data-stu-id="6ef39-127">This allows you to create a connection to the latest PowerShell 6 host version by using the simple name **PowerShell.6**.</span></span> <span data-ttu-id="6ef39-128">Oder Sie können eine Verbindung mit einer bestimmten PowerShell-Host Version herstellen, indem Sie den längeren Namen **PowerShell. 6.2.2** verwenden.</span><span class="sxs-lookup"><span data-stu-id="6ef39-128">Or you can connect to a specific PowerShell host version by using the longer name **PowerShell.6.2.2**.</span></span>

<span data-ttu-id="6ef39-129">Wenn Sie die neu aktivierten Remotingendpunkte verwenden möchten, müssen Sie Sie mit dem **ConfigurationName** -Parameter angeben, wenn Sie eine Remote Verbindung mithilfe der `Invoke-Command` `New-PSSession` `Enter-PSSession` Cmdlets,, erstellen.</span><span class="sxs-lookup"><span data-stu-id="6ef39-129">To use the newly enabled remoting endpoints, you must specify them by name with the **ConfigurationName** parameter when creating a remote connection using the `Invoke-Command`,`New-PSSession`,`Enter-PSSession` cmdlets.</span></span> <span data-ttu-id="6ef39-130">Weitere Informationen finden Sie unter Beispiel 4.</span><span class="sxs-lookup"><span data-stu-id="6ef39-130">For more information, see Example 4.</span></span>

<span data-ttu-id="6ef39-131">Das- `Enable-PSRemoting` Cmdlet führt die folgenden Vorgänge aus:</span><span class="sxs-lookup"><span data-stu-id="6ef39-131">The `Enable-PSRemoting` cmdlet performs the following operations:</span></span>

- <span data-ttu-id="6ef39-132">Führt das Cmdlet " [Set-wsmanquickconfig](../Microsoft.WSMan.Management/Set-WSManQuickConfig.md) " aus, mit dem die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="6ef39-132">Runs the [Set-WSManQuickConfig](../Microsoft.WSMan.Management/Set-WSManQuickConfig.md) cmdlet, which performs the following tasks:</span></span>
  - <span data-ttu-id="6ef39-133">Startet den WinRM-Dienst.</span><span class="sxs-lookup"><span data-stu-id="6ef39-133">Starts the WinRM service.</span></span>
  - <span data-ttu-id="6ef39-134">Legt den Starttyp für den WinRM-Dienst auf "automatisch" fest.</span><span class="sxs-lookup"><span data-stu-id="6ef39-134">Sets the startup type on the WinRM service to Automatic.</span></span>
  - <span data-ttu-id="6ef39-135">Erstellt einen Listener, um Anforderungen an eine beliebige IP-Adresse zu akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="6ef39-135">Creates a listener to accept requests on any IP address.</span></span>
  - <span data-ttu-id="6ef39-136">Aktiviert eine Firewallausnahme für die WS-Management-Kommunikation.</span><span class="sxs-lookup"><span data-stu-id="6ef39-136">Enables a firewall exception for WS-Management communications.</span></span>
  - <span data-ttu-id="6ef39-137">Erstellt bei Bedarf die Sitzungs Endpunkt Konfigurationen für einfache und lange Namen.</span><span class="sxs-lookup"><span data-stu-id="6ef39-137">Creates the simple and long name session endpoint configurations if needed.</span></span>
  - <span data-ttu-id="6ef39-138">Aktiviert alle Sitzungs Konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="6ef39-138">Enables all session configurations.</span></span>
  - <span data-ttu-id="6ef39-139">Ändert die Sicherheits Beschreibung aller Sitzungs Konfigurationen, um den Remote Zugriff zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="6ef39-139">Changes the security descriptor of all session configurations to allow remote access.</span></span>
- <span data-ttu-id="6ef39-140">Startet den WinRM-Dienst neu, damit die vorangehenden Änderungen wirksam werden.</span><span class="sxs-lookup"><span data-stu-id="6ef39-140">Restarts the WinRM service to make the preceding changes effective.</span></span>

<span data-ttu-id="6ef39-141">Um dieses Cmdlet auf der Windows-Plattform auszuführen, starten Sie PowerShell mit der Option als Administrator ausführen.</span><span class="sxs-lookup"><span data-stu-id="6ef39-141">To run this cmdlet on the Windows platform, start PowerShell by using the Run as administrator option.</span></span> <span data-ttu-id="6ef39-142">Dieses Cmdlet ist unter Linux-oder MacOS-Versionen von PowerShell nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="6ef39-142">This cmdlet is not available on Linux or MacOS versions of PowerShell.</span></span>

> [!CAUTION]
> <span data-ttu-id="6ef39-143">Dieses Cmdlet hat keine Auswirkungen auf die von Windows PowerShell erstellten remoteend Punkt Konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="6ef39-143">This cmdlet does not affect remote endpoint configurations created by Windows PowerShell.</span></span>
> <span data-ttu-id="6ef39-144">Sie wirkt sich nur auf Endpunkte aus, die mit PowerShell Version 6 und höher erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="6ef39-144">It only affects endpoints created with PowerShell version 6 and greater.</span></span> <span data-ttu-id="6ef39-145">Zum Aktivieren und Deaktivieren von PowerShell-Remoting-Endpunkten, die von Windows PowerShell gehostet werden, führen Sie das `Enable-PSRemoting` Cmdlet in einer Windows PowerShell-Sitzung aus.</span><span class="sxs-lookup"><span data-stu-id="6ef39-145">To enable and disable PowerShell remoting endpoints that are hosted by Windows PowerShell, run the `Enable-PSRemoting` cmdlet from within a Windows PowerShell session.</span></span>

## <span data-ttu-id="6ef39-146">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="6ef39-146">EXAMPLES</span></span>

### <span data-ttu-id="6ef39-147">Beispiel 1: Konfigurieren eines Computers für den Empfang von Remote Befehlen</span><span class="sxs-lookup"><span data-stu-id="6ef39-147">Example 1: Configure a computer to receive remote commands</span></span>

<span data-ttu-id="6ef39-148">Mit diesem Befehl wird der Computer für den Empfang von Remotebefehlen konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="6ef39-148">This command configures the computer to receive remote commands.</span></span>

```powershell
Enable-PSRemoting
```

```Output
WARNING: PowerShell remoting has been enabled only for PowerShell Core configurations and does not
affect Windows PowerShell remoting configurations. Run this cmdlet in Windows PowerShell to affect
all PowerShell remoting configurations.
```

### <span data-ttu-id="6ef39-149">Beispiel 2: Konfigurieren eines Computers für den Empfang von Remote Befehlen ohne Bestätigungsaufforderung</span><span class="sxs-lookup"><span data-stu-id="6ef39-149">Example 2: Configure a computer to receive remote commands without a confirmation prompt</span></span>

<span data-ttu-id="6ef39-150">Mit diesem Befehl wird der Computer für den Empfang von Remotebefehlen konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="6ef39-150">This command configures the computer to receive remote commands.</span></span>
<span data-ttu-id="6ef39-151">Der **Force** -Parameter unterdrückt die Eingabe Aufforderungen des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="6ef39-151">The **Force** parameter suppresses the user prompts.</span></span>

```powershell
Enable-PSRemoting -Force
```

```Output
WARNING: PowerShell remoting has been enabled only for PowerShell Core configurations and does not
affect Windows PowerShell remoting configurations. Run this cmdlet in Windows PowerShell to affect
all PowerShell remoting configurations.
```

### <span data-ttu-id="6ef39-152">Beispiel 3: zulassen des Remote Zugriffs auf Clients</span><span class="sxs-lookup"><span data-stu-id="6ef39-152">Example 3: Allow remote access on clients</span></span>

<span data-ttu-id="6ef39-153">In diesem Beispiel wird gezeigt, wie der Remote Zugriff aus öffentlichen Netzwerken unter Client Versionen des Windows-Betriebssystems zugelassen wird.</span><span class="sxs-lookup"><span data-stu-id="6ef39-153">This example shows how to allow remote access from public networks on client versions of the Windows operating system.</span></span> <span data-ttu-id="6ef39-154">Der Name der Firewallregel kann sich für unterschiedliche Windows-Versionen unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="6ef39-154">The name of the firewall rule can be different for different versions of Windows.</span></span>
<span data-ttu-id="6ef39-155">Verwenden `Get-NetFirewallRule` Sie, um eine Liste der Regeln anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="6ef39-155">Use `Get-NetFirewallRule` to see a list of rules.</span></span> <span data-ttu-id="6ef39-156">Vor dem Aktivieren der Firewallregel können Sie die Sicherheitseinstellungen in der Regel anzeigen, um zu überprüfen, ob die Konfiguration für Ihre Umgebung geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="6ef39-156">Before enabling the firewall rule, view the security settings in the rule to verify that the configuration is appropriate for your environment.</span></span>

```powershell
Get-NetFirewallRule -Name 'WINRM*' | Select-Object Name
```

```Output
Name
----
WINRM-HTTP-In-TCP-NoScope
WINRM-HTTP-In-TCP
WINRM-HTTP-Compat-In-TCP-NoScope
WINRM-HTTP-Compat-In-TCP
```

```powershell
Enable-PSRemoting -SkipNetworkProfileCheck -Force
Set-NetFirewallRule -Name 'WINRM-HTTP-In-TCP' -RemoteAddress Any
```

<span data-ttu-id="6ef39-157">Standardmäßig `Enable-PSRemoting` erstellt Netzwerk Regeln, die den Remote Zugriff über private Netzwerke und Domänen Netzwerke ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="6ef39-157">By default, `Enable-PSRemoting` creates network rules that allow remote access from private and domain networks.</span></span> <span data-ttu-id="6ef39-158">Der Befehl verwendet den **SkipNetworkProfileCheck** -Parameter, um Remotezugriff aus öffentlichen Netzwerken im gleichen lokalen Subnetz zuzulassen.</span><span class="sxs-lookup"><span data-stu-id="6ef39-158">The command uses the **SkipNetworkProfileCheck** parameter to allow remote access from public networks in the same local subnet.</span></span> <span data-ttu-id="6ef39-159">Der Befehl gibt den **Force** -Parameter an, um Bestätigungsmeldungen zu unterdrücken.</span><span class="sxs-lookup"><span data-stu-id="6ef39-159">The command specifies the **Force** parameter to suppress confirmation messages.</span></span>

<span data-ttu-id="6ef39-160">Der **skipnetworkprofilecheck** -Parameter wirkt sich nicht auf Serverversionen des Windows-Betriebssystems aus, die standardmäßig den Remote Zugriff von öffentlichen Netzwerken im gleichen lokalen Subnetz zulassen.</span><span class="sxs-lookup"><span data-stu-id="6ef39-160">The **SkipNetworkProfileCheck** parameter does not affect server versions of the Windows operating system, which allow remote access from public networks in the same local subnet by default.</span></span>

<span data-ttu-id="6ef39-161">Das- `Set-NetFirewallRule` Cmdlet im **Netsecurity** -Modul fügt eine Firewallregel hinzu, die den Remote Zugriff aus öffentlichen Netzwerken von einem beliebigen Remote Standort aus zulässt.</span><span class="sxs-lookup"><span data-stu-id="6ef39-161">The `Set-NetFirewallRule` cmdlet in the **NetSecurity** module adds a firewall rule that allows remote access from public networks from any remote location.</span></span> <span data-ttu-id="6ef39-162">Dies gilt auch für Standorte in unterschiedlichen Subnetzen.</span><span class="sxs-lookup"><span data-stu-id="6ef39-162">This includes locations in different subnets.</span></span>

### <span data-ttu-id="6ef39-163">Beispiel 4: Erstellen einer Remote Sitzung mit der neu aktivierten Endpunkt Konfiguration</span><span class="sxs-lookup"><span data-stu-id="6ef39-163">Example 4: Create a remote session to the newly enabled endpoint configuration</span></span>

<span data-ttu-id="6ef39-164">Dieses Beispiel zeigt, wie Sie PowerShell-Remoting auf einem Computer aktivieren, die konfigurierten Endpunkt Namen suchen und eine Remote Sitzung zu einem der Endpunkte erstellen.</span><span class="sxs-lookup"><span data-stu-id="6ef39-164">This example shows how to enable PowerShell remoting on a computer, find the configured endpoint names, and create a remote session to one of the endpoints.</span></span>

<span data-ttu-id="6ef39-165">Der erste Befehl aktiviert PowerShell-Remoting auf dem Computer.</span><span class="sxs-lookup"><span data-stu-id="6ef39-165">The first command enables PowerShell remoting on the computer.</span></span>

<span data-ttu-id="6ef39-166">Mit dem zweiten Befehl werden die Endpunkt Konfigurationen aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="6ef39-166">The second command lists the endpoint configurations.</span></span>

<span data-ttu-id="6ef39-167">Mit dem dritten Befehl wird eine PowerShell-Remote Sitzung auf demselben Computer erstellt, wobei der **PowerShell. 6** -Endpunkt nach Name angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="6ef39-167">The third command creates a remote PowerShell session to the same machine, specifying the **PowerShell.6** endpoint by name.</span></span> <span data-ttu-id="6ef39-168">Die Remote Sitzung wird mit der neuesten Version von PowerShell 6 (6.2.2) gehostet.</span><span class="sxs-lookup"><span data-stu-id="6ef39-168">The remote session will be hosted with the latest PowerShell 6 version (6.2.2).</span></span>

<span data-ttu-id="6ef39-169">Mit dem letzten Befehl wird `$PSVersionTable` auf die Variable in der Remote Sitzung zugegriffen, um die PowerShell-Version anzuzeigen, in der die Sitzung gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="6ef39-169">The last command accesses the `$PSVersionTable` variable in the remote session to display the PowerShell version that is hosting the session.</span></span>

```powershell
Enable-PSRemoting -Force

Get-PSSessionConfiguration

$session = New-PSSession -ComputerName localhost -ConfigurationName PowerShell.6

Invoke-Command -Session $session -ScriptBlock { $PSVersionTable }
```

```Output
WARNING: PowerShell remoting has been enabled only for PowerShell Core configurations and does not
affect Windows PowerShell remoting configurations. Run this cmdlet in Windows PowerShell to affect
all PowerShell remoting configurations.

Name          : PowerShell.6
PSVersion     : 6.2
StartupScript :
RunAsUser     :
Permission    : NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed,
                BUILTIN\Remote Management Users AccessAllowed

Name          : PowerShell.6.2.2
PSVersion     : 6.2
StartupScript :
RunAsUser     :
Permission    : NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed,
                BUILTIN\Remote Management Users AccessAllowed

Name                           Value
----                           -----
PSCompatibleVersions           {1.0, 2.0, 3.0, 4.0…}
PSEdition                      Core
PSRemotingProtocolVersion      2.3
Platform                       Win32NT
SerializationVersion           1.1.0.1
GitCommitId                    6.2.2
WSManStackVersion              3.0
PSVersion                      6.2.2
OS                             Microsoft Windows 10.0.18363
```

> [!NOTE]
> <span data-ttu-id="6ef39-170">Der Name der Firewallregel kann je nach Windows-Version unterschiedlich sein.</span><span class="sxs-lookup"><span data-stu-id="6ef39-170">The name of the firewall rule can be different depending on the version of Windows.</span></span> <span data-ttu-id="6ef39-171">Verwenden `Get-NetFirewallRule` Sie das Cmdlet, um die Namen der Regeln auf dem System aufzulisten.</span><span class="sxs-lookup"><span data-stu-id="6ef39-171">Use the `Get-NetFirewallRule` cmdlet to list the names of the rules on your system.</span></span>

## <span data-ttu-id="6ef39-172">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="6ef39-172">PARAMETERS</span></span>

### <span data-ttu-id="6ef39-173">-Confirm</span><span class="sxs-lookup"><span data-stu-id="6ef39-173">-Confirm</span></span>

<span data-ttu-id="6ef39-174">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="6ef39-174">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="6ef39-175">-Force</span><span class="sxs-lookup"><span data-stu-id="6ef39-175">-Force</span></span>

<span data-ttu-id="6ef39-176">Erzwingt die Ausführung des Befehls ohne Aufforderung zur Bestätigung durch den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="6ef39-176">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="6ef39-177">-Skipnetworkprofilecheck</span><span class="sxs-lookup"><span data-stu-id="6ef39-177">-SkipNetworkProfileCheck</span></span>

<span data-ttu-id="6ef39-178">Gibt an, dass dieses Cmdlet Remoting unter Client Versionen des Windows-Betriebssystems aktiviert, wenn sich der Computer in einem öffentlichen Netzwerk befindet.</span><span class="sxs-lookup"><span data-stu-id="6ef39-178">Indicates that this cmdlet enables remoting on client versions of the Windows operating system when the computer is on a public network.</span></span> <span data-ttu-id="6ef39-179">Dieser Parameter aktiviert eine Firewallregel für öffentliche Netzwerke, die den Remotezugriff nur von Computern im selben lokalen Subnetz zulässt.</span><span class="sxs-lookup"><span data-stu-id="6ef39-179">This parameter enables a firewall rule for public networks that allows remote access only from computers in the same local subnet.</span></span>

<span data-ttu-id="6ef39-180">Dieser Parameter wirkt sich nicht auf Serverversionen des Windows-Betriebssystems aus, die standardmäßig über eine Firewallregel für ein lokales Subnetz für öffentliche Netzwerke verfügen.</span><span class="sxs-lookup"><span data-stu-id="6ef39-180">This parameter does not affect server versions of the Windows operating system, which, by default, have a local subnet firewall rule for public networks.</span></span> <span data-ttu-id="6ef39-181">Wenn die Firewallregel für das lokale Subnetz für eine Server Version deaktiviert ist, wird `Enable-PSRemoting` Sie unabhängig vom Wert dieses Parameters erneut aktiviert.</span><span class="sxs-lookup"><span data-stu-id="6ef39-181">If the local subnet firewall rule is disabled on a server version, `Enable-PSRemoting` re-enables it, regardless of the value of this parameter.</span></span>

<span data-ttu-id="6ef39-182">Verwenden Sie das `Set-NetFirewallRule` Cmdlet im **Netsecurity** -Modul, um die Einschränkung für das lokale Subnetz zu entfernen und den Remote Zugriff von allen Standorten in öffentlichen Netzwerken aus zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="6ef39-182">To remove the local subnet restriction and enable remote access from all locations on public networks, use the `Set-NetFirewallRule` cmdlet in the **NetSecurity** module.</span></span>

<span data-ttu-id="6ef39-183">Dieser Parameter wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="6ef39-183">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="6ef39-184">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="6ef39-184">-WhatIf</span></span>

<span data-ttu-id="6ef39-185">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="6ef39-185">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="6ef39-186">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="6ef39-186">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="6ef39-187">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="6ef39-187">CommonParameters</span></span>

<span data-ttu-id="6ef39-188">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="6ef39-188">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="6ef39-189">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="6ef39-189">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="6ef39-190">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="6ef39-190">INPUTS</span></span>

### <span data-ttu-id="6ef39-191">Keine</span><span class="sxs-lookup"><span data-stu-id="6ef39-191">None</span></span>

<span data-ttu-id="6ef39-192">Eingaben können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="6ef39-192">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="6ef39-193">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="6ef39-193">OUTPUTS</span></span>

### <span data-ttu-id="6ef39-194">System.String</span><span class="sxs-lookup"><span data-stu-id="6ef39-194">System.String</span></span>

<span data-ttu-id="6ef39-195">Dieses Cmdlet gibt Zeichen folgen zurück, die die Ergebnisse beschreiben.</span><span class="sxs-lookup"><span data-stu-id="6ef39-195">This cmdlet returns strings that describe its results.</span></span>

## <span data-ttu-id="6ef39-196">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="6ef39-196">NOTES</span></span>

<span data-ttu-id="6ef39-197">Unter Serverversionen des Windows-Betriebssystems `Enable-PSRemoting` erstellt Firewallregeln für private Netzwerke und Domänen Netzwerke, die Remote Zugriff zulassen, und erstellt eine Firewallregel für öffentliche Netzwerke, die den Remote Zugriff nur von Computern im selben lokalen Subnetz zulässt.</span><span class="sxs-lookup"><span data-stu-id="6ef39-197">On server versions of the Windows operating system, `Enable-PSRemoting` creates firewall rules for private and domain networks that allow remote access, and creates a firewall rule for public networks that allows remote access only from computers in the same local subnet.</span></span>

<span data-ttu-id="6ef39-198">Unter Client Versionen des Windows-Betriebssystems `Enable-PSRemoting` erstellt Firewallregeln für private Netzwerke und Domänen Netzwerke, die uneingeschränkten Remote Zugriff zulassen.</span><span class="sxs-lookup"><span data-stu-id="6ef39-198">On client versions of the Windows operating system, `Enable-PSRemoting` creates firewall rules for private and domain networks that allow unrestricted remote access.</span></span> <span data-ttu-id="6ef39-199">Um eine Firewallregel für öffentliche Netzwerke zu erstellen, die Remotezugriff aus dem gleichen lokalen Subnetz zulässt, verwenden Sie den **SkipNetworkProfileCheck** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="6ef39-199">To create a firewall rule for public networks that allows remote access from the same local subnet, use the **SkipNetworkProfileCheck** parameter.</span></span>

<span data-ttu-id="6ef39-200">Wenn Sie auf Client-oder Serverversionen des Windows-Betriebssystems eine Firewallregel für öffentliche Netzwerke erstellen möchten, die die Einschränkung des lokalen Subnetzes entfernt und den Remote Zugriff zulässt, verwenden `Set-NetFirewallRule` Sie das Cmdlet im Netsecurity-Modul, um den folgenden Befehl auszuführen: `Set-NetFirewallRule -Name "WINRM-HTTP-In-TCP-PUBLIC" -RemoteAddress Any`</span><span class="sxs-lookup"><span data-stu-id="6ef39-200">On client or server versions of the Windows operating system, to create a firewall rule for public networks that removes the local subnet restriction and allows remote access , use the `Set-NetFirewallRule` cmdlet in the NetSecurity module to run the following command: `Set-NetFirewallRule -Name "WINRM-HTTP-In-TCP-PUBLIC" -RemoteAddress Any`</span></span>

<span data-ttu-id="6ef39-201">`Enable-PSRemoting` aktiviert alle Sitzungs Konfigurationen, indem der Wert der **aktivierten** Eigenschaft aller Sitzungs Konfigurationen auf festgelegt wird `$True` .</span><span class="sxs-lookup"><span data-stu-id="6ef39-201">`Enable-PSRemoting` enables all session configurations by setting the value of the **Enabled** property of all session configurations to `$True`.</span></span>

<span data-ttu-id="6ef39-202">`Enable-PSRemoting` entfernt die Einstellungen für **Deny_All** und **Network_Deny_All** .</span><span class="sxs-lookup"><span data-stu-id="6ef39-202">`Enable-PSRemoting` removes the **Deny_All** and **Network_Deny_All** settings.</span></span> <span data-ttu-id="6ef39-203">Dies ermöglicht den Remote Zugriff auf Sitzungs Konfigurationen, die für die lokale Verwendung reserviert wurden.</span><span class="sxs-lookup"><span data-stu-id="6ef39-203">This provides remote access to session configurations that were reserved for local use.</span></span>

## <span data-ttu-id="6ef39-204">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="6ef39-204">RELATED LINKS</span></span>

[<span data-ttu-id="6ef39-205">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="6ef39-205">Disable-PSSessionConfiguration</span></span>](Disable-PSSessionConfiguration.md)

[<span data-ttu-id="6ef39-206">Enable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="6ef39-206">Enable-PSSessionConfiguration</span></span>](Enable-PSSessionConfiguration.md)

[<span data-ttu-id="6ef39-207">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="6ef39-207">Get-PSSessionConfiguration</span></span>](Get-PSSessionConfiguration.md)

[<span data-ttu-id="6ef39-208">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="6ef39-208">Register-PSSessionConfiguration</span></span>](Register-PSSessionConfiguration.md)

[<span data-ttu-id="6ef39-209">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="6ef39-209">Set-PSSessionConfiguration</span></span>](Set-PSSessionConfiguration.md)

[<span data-ttu-id="6ef39-210">Disable-PSRemoting</span><span class="sxs-lookup"><span data-stu-id="6ef39-210">Disable-PSRemoting</span></span>](Disable-PSRemoting.md)

[<span data-ttu-id="6ef39-211">WSMan-Anbieter</span><span class="sxs-lookup"><span data-stu-id="6ef39-211">WSMan Provider</span></span>](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

[<span data-ttu-id="6ef39-212">about_Remote</span><span class="sxs-lookup"><span data-stu-id="6ef39-212">about_Remote</span></span>](About/about_Remote.md)

[<span data-ttu-id="6ef39-213">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="6ef39-213">about_Session_Configurations</span></span>](About/about_Session_Configurations.md)