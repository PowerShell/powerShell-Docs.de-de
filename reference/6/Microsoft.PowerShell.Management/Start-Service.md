---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/start-service?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-Service
ms.openlocfilehash: ae2b61ab4f5486b761f32603e60a10507e96a907
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212247"
---
# <span data-ttu-id="beac5-103">Start-Service</span><span class="sxs-lookup"><span data-stu-id="beac5-103">Start-Service</span></span>

## <span data-ttu-id="beac5-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="beac5-104">SYNOPSIS</span></span>
<span data-ttu-id="beac5-105">Startet beendete Dienste.</span><span class="sxs-lookup"><span data-stu-id="beac5-105">Starts one or more stopped services.</span></span>

## <span data-ttu-id="beac5-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="beac5-106">SYNTAX</span></span>

### <span data-ttu-id="beac5-107">Inputobject (Standard)</span><span class="sxs-lookup"><span data-stu-id="beac5-107">InputObject (Default)</span></span>

```
Start-Service [-InputObject] <ServiceController[]> [-PassThru] [-Include <String[]>] [-Exclude <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="beac5-108">Standard</span><span class="sxs-lookup"><span data-stu-id="beac5-108">Default</span></span>

```
Start-Service [-Name] <String[]> [-PassThru] [-Include <String[]>] [-Exclude <String[]>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="beac5-109">DisplayName</span><span class="sxs-lookup"><span data-stu-id="beac5-109">DisplayName</span></span>

```
Start-Service [-PassThru] -DisplayName <String[]> [-Include <String[]>] [-Exclude <String[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="beac5-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="beac5-110">DESCRIPTION</span></span>

<span data-ttu-id="beac5-111">Das- `Start-Service` Cmdlet sendet für jeden der angegebenen Dienste eine Start Meldung an den Windows-Dienst Controller.</span><span class="sxs-lookup"><span data-stu-id="beac5-111">The `Start-Service` cmdlet sends a start message to the Windows Service Controller for each of the specified services.</span></span> <span data-ttu-id="beac5-112">Wenn ein Dienst bereits ausgeführt wird, wird die Meldung ignoriert, ohne dass ein Fehler ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="beac5-112">If a service is already running, the message is ignored without error.</span></span> <span data-ttu-id="beac5-113">Sie können die Dienste mit ihren Dienstnamen oder anzeigen Amen angeben, oder Sie können mit dem **Inputobject** -Parameter ein Dienst Objekt bereitstellen, das die Dienste darstellt, die Sie starten möchten.</span><span class="sxs-lookup"><span data-stu-id="beac5-113">You can specify the services by their service names or display names, or you can use the **InputObject** parameter to supply a service object that represents the services that you want to start.</span></span>

## <span data-ttu-id="beac5-114">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="beac5-114">EXAMPLES</span></span>

### <span data-ttu-id="beac5-115">Beispiel 1: Starten eines diensnamens mit seinem Namen</span><span class="sxs-lookup"><span data-stu-id="beac5-115">Example 1: Start a service by using its name</span></span>

<span data-ttu-id="beac5-116">In diesem Beispiel wird der EventLog-Dienst auf dem lokalen Computer gestartet.</span><span class="sxs-lookup"><span data-stu-id="beac5-116">This example starts the EventLog service on the local computer.</span></span> <span data-ttu-id="beac5-117">Mit dem **Name** -Parameter wird der Dienst anhand seines Dienst namens identifiziert.</span><span class="sxs-lookup"><span data-stu-id="beac5-117">The **Name** parameter identifies the service by its service name.</span></span>

```powershell
Start-Service -Name "eventlog"
```

### <span data-ttu-id="beac5-118">Beispiel 2: Anzeigen von Informationen, ohne einen Dienst zu starten</span><span class="sxs-lookup"><span data-stu-id="beac5-118">Example 2: Display information without starting a service</span></span>

<span data-ttu-id="beac5-119">Dieses Beispiel zeigt, was geschieht, wenn Sie die Dienste mit einem anzeigen Amen gestartet haben, der "Remote" enthält.</span><span class="sxs-lookup"><span data-stu-id="beac5-119">This example shows what would occur if you started the services that have a display name that includes "remote".</span></span>

```powershell
Start-Service -DisplayName *remote* -WhatIf
```

<span data-ttu-id="beac5-120">Der **DisplayName** -Parameter identifiziert die Dienste anhand ihres anzeigen Amens anstelle des Dienst namens.</span><span class="sxs-lookup"><span data-stu-id="beac5-120">The **DisplayName** parameter identifies the services by their display name instead of their service name.</span></span> <span data-ttu-id="beac5-121">Der **WhatIf** -Parameter bewirkt, dass das Cmdlet anzeigt, was passieren würde, wenn Sie den Befehl ausführen, aber keine Änderungen vornehmen.</span><span class="sxs-lookup"><span data-stu-id="beac5-121">The **WhatIf** parameter causes the cmdlet to display what would happen when you run the command but does not make changes.</span></span>

### <span data-ttu-id="beac5-122">Beispiel 3: Starten Sie einen Dienst, und notieren Sie die Aktion in einer Textdatei.</span><span class="sxs-lookup"><span data-stu-id="beac5-122">Example 3: Start a service and record the action in a text file</span></span>

<span data-ttu-id="beac5-123">In diesem Beispiel wird der Windows-Verwaltungsinstrumentation (WMI)-Dienst auf dem Computer gestartet, und der services.txt-Datei wird ein Datensatz der Aktion hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="beac5-123">This example starts the Windows Management Instrumentation (WMI) service on the computer and adds a record of the action to the services.txt file.</span></span>

```powershell
$s = Get-Service wmi
Start-Service -InputObject $s -PassThru | Format-List >> services.txt
```

<span data-ttu-id="beac5-124">Zuerst wird verwendet `Get-Service` , um ein Objekt zu erhalten, das den WMI-Dienst darstellt, und in der `$s` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="beac5-124">First we use `Get-Service` to get an object that represent the WMI service and store it in the `$s` variable.</span></span> <span data-ttu-id="beac5-125">Als nächstes starten wir den Dienst.</span><span class="sxs-lookup"><span data-stu-id="beac5-125">Next, we start the service.</span></span> <span data-ttu-id="beac5-126">Ohne den **passthru** -Parameter `Start-Service` erstellt keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="beac5-126">Without the **PassThru** parameter, `Start-Service` does not create any output.</span></span> <span data-ttu-id="beac5-127">Der Pipeline Operator (|) übergibt die Objekt Ausgabe an `Start-Service` das `Format-List` Cmdlet, um das Objekt als Liste seiner Eigenschaften zu formatieren.</span><span class="sxs-lookup"><span data-stu-id="beac5-127">The pipeline operator (|) passes the object output by `Start-Service` to the `Format-List` cmdlet to format the object as a list of its properties.</span></span> <span data-ttu-id="beac5-128">Der Anfüge Weiterleitungs Operator ( \> \> ) leitet die Ausgabe an die services.txt Datei um.</span><span class="sxs-lookup"><span data-stu-id="beac5-128">The append redirection operator (\>\>) redirects the output to the services.txt file.</span></span> <span data-ttu-id="beac5-129">Die Ausgabe wird am Ende der vorhandenen Datei hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="beac5-129">The output is added to the end of the existing file.</span></span>

### <span data-ttu-id="beac5-130">Beispiel 4: Starten eines deaktivierten Dienstanbieter</span><span class="sxs-lookup"><span data-stu-id="beac5-130">Example 4: Start a disabled service</span></span>

<span data-ttu-id="beac5-131">Dieses Beispiel zeigt, wie ein Dienst gestartet wird, wenn der Starttyp des Dienstanbieter **deaktiviert** ist.</span><span class="sxs-lookup"><span data-stu-id="beac5-131">This example shows how to start a service when the start type of the service is **Disabled** .</span></span>

```
PS> Start-Service tlntsvr
Start-Service : Service 'Telnet (TlntSvr)' cannot be started due to the following error: Cannot start service TlntSvr on computer '.'.
At line:1 char:14
+ Start-Service  <<<< tlntsvr

PS> Get-CimInstance win32_service | Where-Object Name -eq "tlntsvr"
ExitCode  : 0
Name      : TlntSvr
ProcessId : 0
StartMode : Disabled
State     : Stopped
Status    : OK

PS> Set-Service tlntsvr -StartupType manual
PS> Start-Service tlntsvr
```

<span data-ttu-id="beac5-132">Beim ersten Versuch, den Telnet-Dienst (tlnzvr) zu starten, tritt ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="beac5-132">The first attempt to start the Telnet service (tlntsvr) fails.</span></span> <span data-ttu-id="beac5-133">Der `Get-CimInstance` Befehl zeigt, dass die **StartMode** -Eigenschaft des tlnzvr-diensdienstanbieter **deaktiviert** ist.</span><span class="sxs-lookup"><span data-stu-id="beac5-133">The `Get-CimInstance` command shows that the **StartMode** property of the Tlntsvr service is **Disabled** .</span></span> <span data-ttu-id="beac5-134">Mit dem- `Set-Service` Cmdlet wird der Starttyp in **manuell** geändert.</span><span class="sxs-lookup"><span data-stu-id="beac5-134">The `Set-Service` cmdlet changes the start type to **Manual** .</span></span> <span data-ttu-id="beac5-135">Nun können wir den Befehl erneut übermitteln `Start-Service` .</span><span class="sxs-lookup"><span data-stu-id="beac5-135">Now, we can resubmit the `Start-Service` command.</span></span> <span data-ttu-id="beac5-136">Dieses Mal wird der Befehl ohne Fehler verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="beac5-136">This time, the command succeeds.</span></span> <span data-ttu-id="beac5-137">Führen Sie aus, um zu überprüfen, ob der Befehl erfolgreich war `Get-Service`</span><span class="sxs-lookup"><span data-stu-id="beac5-137">To verify that the command succeeded, run `Get-Service`.</span></span>

## <span data-ttu-id="beac5-138">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="beac5-138">PARAMETERS</span></span>

### <span data-ttu-id="beac5-139">-DisplayName</span><span class="sxs-lookup"><span data-stu-id="beac5-139">-DisplayName</span></span>

<span data-ttu-id="beac5-140">Gibt die anzeigen amen der zu startenden Dienste an.</span><span class="sxs-lookup"><span data-stu-id="beac5-140">Specifies the display names of the services to start.</span></span> <span data-ttu-id="beac5-141">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="beac5-141">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: DisplayName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="beac5-142">-Ausschließen</span><span class="sxs-lookup"><span data-stu-id="beac5-142">-Exclude</span></span>

<span data-ttu-id="beac5-143">Gibt die Dienste an, die von diesem Cmdlet ausgelassen werden.</span><span class="sxs-lookup"><span data-stu-id="beac5-143">Specifies services that this cmdlet omits.</span></span> <span data-ttu-id="beac5-144">Der Wert dieses Parameters qualifiziert den **Name** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="beac5-144">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="beac5-145">Geben Sie ein Namenselement oder-Muster ein, z `s*` . b..</span><span class="sxs-lookup"><span data-stu-id="beac5-145">Enter a name element or pattern, such as `s*`.</span></span> <span data-ttu-id="beac5-146">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="beac5-146">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="beac5-147">-Include</span><span class="sxs-lookup"><span data-stu-id="beac5-147">-Include</span></span>

<span data-ttu-id="beac5-148">Gibt die Dienste an, die von diesem Cmdlet gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="beac5-148">Specifies services that this cmdlet starts.</span></span> <span data-ttu-id="beac5-149">Der Wert dieses Parameters qualifiziert den **Name** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="beac5-149">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="beac5-150">Geben Sie ein Namenselement oder-Muster ein, z `s*` . b..</span><span class="sxs-lookup"><span data-stu-id="beac5-150">Enter a name element or pattern, such as `s*`.</span></span> <span data-ttu-id="beac5-151">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="beac5-151">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="beac5-152">-InputObject</span><span class="sxs-lookup"><span data-stu-id="beac5-152">-InputObject</span></span>

<span data-ttu-id="beac5-153">Gibt **ServiceController** -Objekte an, die die zu startenden Dienste darstellen.</span><span class="sxs-lookup"><span data-stu-id="beac5-153">Specifies **ServiceController** objects representing the services to be started.</span></span> <span data-ttu-id="beac5-154">Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, mit dem die Objekte abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="beac5-154">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

```yaml
Type: System.ServiceProcess.ServiceController[]
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="beac5-155">-Name</span><span class="sxs-lookup"><span data-stu-id="beac5-155">-Name</span></span>

<span data-ttu-id="beac5-156">Gibt die Dienstnamen für die zu startenden Dienste an.</span><span class="sxs-lookup"><span data-stu-id="beac5-156">Specifies the service names for the service to be started.</span></span>

<span data-ttu-id="beac5-157">Der Parametername ist optional.</span><span class="sxs-lookup"><span data-stu-id="beac5-157">The parameter name is optional.</span></span> <span data-ttu-id="beac5-158">Sie können " **Name** " oder den zugehörigen Alias " **Service** Name" verwenden, oder Sie können den Parameternamen weglassen.</span><span class="sxs-lookup"><span data-stu-id="beac5-158">You can use **Name** or its alias, **ServiceName** , or you can omit the parameter name.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Default
Aliases: ServiceName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="beac5-159">-PassThru</span><span class="sxs-lookup"><span data-stu-id="beac5-159">-PassThru</span></span>

<span data-ttu-id="beac5-160">Gibt ein Objekt zurück, das den Dienst darstellt.</span><span class="sxs-lookup"><span data-stu-id="beac5-160">Returns an object that represents the service.</span></span> <span data-ttu-id="beac5-161">Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="beac5-161">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="beac5-162">-Confirm</span><span class="sxs-lookup"><span data-stu-id="beac5-162">-Confirm</span></span>

<span data-ttu-id="beac5-163">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="beac5-163">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="beac5-164">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="beac5-164">-WhatIf</span></span>

<span data-ttu-id="beac5-165">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="beac5-165">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="beac5-166">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="beac5-166">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="beac5-167">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="beac5-167">CommonParameters</span></span>

<span data-ttu-id="beac5-168">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="beac5-168">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="beac5-169">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="beac5-169">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="beac5-170">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="beac5-170">INPUTS</span></span>

### <span data-ttu-id="beac5-171">System. ServiceProcess. ServiceController, System. String</span><span class="sxs-lookup"><span data-stu-id="beac5-171">System.ServiceProcess.ServiceController, System.String</span></span>

<span data-ttu-id="beac5-172">Sie können Objekte, die die Dienstnamen enthalten, über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="beac5-172">You can pipe objects that represent the services or strings that contain the service names to this cmdlet.</span></span>

## <span data-ttu-id="beac5-173">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="beac5-173">OUTPUTS</span></span>

### <span data-ttu-id="beac5-174">Keine, System. ServiceProcess. ServiceController</span><span class="sxs-lookup"><span data-stu-id="beac5-174">None, System.ServiceProcess.ServiceController</span></span>

<span data-ttu-id="beac5-175">Dieses Cmdlet generiert ein **System. ServiceProcess. ServiceController** -Objekt, das den Dienst darstellt, wenn Sie **passthru** angeben.</span><span class="sxs-lookup"><span data-stu-id="beac5-175">This cmdlet generates a **System.ServiceProcess.ServiceController** object that represents the service, if you specify **PassThru** .</span></span> <span data-ttu-id="beac5-176">Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="beac5-176">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="beac5-177">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="beac5-177">NOTES</span></span>

* <span data-ttu-id="beac5-178">Sie können auch auf den `Start-Service` integrierten Alias verweisen `sasv` .</span><span class="sxs-lookup"><span data-stu-id="beac5-178">You can also refer to `Start-Service` by its built-in alias, `sasv`.</span></span> <span data-ttu-id="beac5-179">Weitere Informationen finden Sie unter [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="beac5-179">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>
* <span data-ttu-id="beac5-180">`Start-Service` Dienste können nur von gesteuert werden, wenn der aktuelle Benutzer über die entsprechende Berechtigung verfügt.</span><span class="sxs-lookup"><span data-stu-id="beac5-180">`Start-Service` can control services only if the current user has permission to do this.</span></span> <span data-ttu-id="beac5-181">Wenn ein Befehl nicht ordnungsgemäß verarbeitet wird, verfügen Sie u. U. nicht über die erforderlichen Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="beac5-181">If a command does not work correctly, you might not have the required permissions.</span></span>
* <span data-ttu-id="beac5-182">Geben Sie ein, um die Dienstnamen und anzeigen amen der Dienste auf dem System zu suchen `Get-Service` .</span><span class="sxs-lookup"><span data-stu-id="beac5-182">To find the service names and display names of the services on your system, type `Get-Service`.</span></span>
  <span data-ttu-id="beac5-183">Die Dienstnamen werden in der Spalte **Name** angezeigt, und die anzeigen Amen werden in der Spalte **Display Name** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="beac5-183">The service names appear in the **Name** column, and the display names appear in the **DisplayName** column.</span></span>
* <span data-ttu-id="beac5-184">Sie können nur die Dienste starten, die den Starttyp manuell, automatisch oder automatisch (verzögerter Start) aufweisen.</span><span class="sxs-lookup"><span data-stu-id="beac5-184">You can start only the services that have a start type of Manual, Automatic, or Automatic (Delayed Start).</span></span> <span data-ttu-id="beac5-185">Sie können keine Dienste starten, die den Starttyp "deaktiviert" aufweisen.</span><span class="sxs-lookup"><span data-stu-id="beac5-185">You cannot start the services that have a start type of Disabled.</span></span> <span data-ttu-id="beac5-186">Wenn ein `Start-Service` Befehl mit der Meldung fehlschlägt `Cannot start service \<service-name\> on computer` , verwenden `Get-CimInstance` Sie, um den Starttyp des Dienstanbieter zu suchen, und verwenden Sie ggf. das `Set-Service` Cmdlet, um den Starttyp des Dienstanbieter zu ändern.</span><span class="sxs-lookup"><span data-stu-id="beac5-186">If a `Start-Service` command fails with the message `Cannot start service \<service-name\> on computer`, use `Get-CimInstance` to find the start type of the service and, if you have to, use the `Set-Service` cmdlet to change the start type of the service.</span></span>
* <span data-ttu-id="beac5-187">Einige Dienste, beispielsweise der Dienst für Leistungsprotokolle und -warnungen (SysmonLog), werden automatisch beendet, wenn sie keine Vorgänge ausführen müssen.</span><span class="sxs-lookup"><span data-stu-id="beac5-187">Some services, such as Performance Logs and Alerts (SysmonLog) stop automatically if they have no work to do.</span></span> <span data-ttu-id="beac5-188">Wenn PowerShell einen Dienst startet, der sich fast sofort beendet, wird die folgende Meldung angezeigt: `Service \<display-name\> start failed.`</span><span class="sxs-lookup"><span data-stu-id="beac5-188">When PowerShell starts a service that stops itself almost immediately, it displays the following message: `Service \<display-name\> start failed.`</span></span>

## <span data-ttu-id="beac5-189">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="beac5-189">RELATED LINKS</span></span>

[<span data-ttu-id="beac5-190">Get-Service</span><span class="sxs-lookup"><span data-stu-id="beac5-190">Get-Service</span></span>](Get-Service.md)

[<span data-ttu-id="beac5-191">New-Service</span><span class="sxs-lookup"><span data-stu-id="beac5-191">New-Service</span></span>](New-Service.md)

[<span data-ttu-id="beac5-192">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="beac5-192">Restart-Service</span></span>](Restart-Service.md)

[<span data-ttu-id="beac5-193">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="beac5-193">Resume-Service</span></span>](Resume-Service.md)

[<span data-ttu-id="beac5-194">Set-Service</span><span class="sxs-lookup"><span data-stu-id="beac5-194">Set-Service</span></span>](Set-Service.md)

[<span data-ttu-id="beac5-195">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="beac5-195">Stop-Service</span></span>](Stop-Service.md)

[<span data-ttu-id="beac5-196">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="beac5-196">Suspend-Service</span></span>](Suspend-Service.md)

[<span data-ttu-id="beac5-197">Remove-Service</span><span class="sxs-lookup"><span data-stu-id="beac5-197">Remove-Service</span></span>](Remove-Service.md)