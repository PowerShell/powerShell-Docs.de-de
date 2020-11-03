---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/restart-service?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Restart-Service
ms.openlocfilehash: 5ad6fb4d39b604834bb77935b14686e088bb61f2
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93211868"
---
# <span data-ttu-id="a39e6-103">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="a39e6-103">Restart-Service</span></span>

## <span data-ttu-id="a39e6-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="a39e6-104">SYNOPSIS</span></span>
<span data-ttu-id="a39e6-105">Beendet Dienste und startet diese anschließend.</span><span class="sxs-lookup"><span data-stu-id="a39e6-105">Stops and then starts one or more services.</span></span>

## <span data-ttu-id="a39e6-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a39e6-106">SYNTAX</span></span>

### <span data-ttu-id="a39e6-107">Inputobject (Standard)</span><span class="sxs-lookup"><span data-stu-id="a39e6-107">InputObject (Default)</span></span>

```
Restart-Service [-Force] [-InputObject] <ServiceController[]> [-PassThru] [-Include <String[]>]
 [-Exclude <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="a39e6-108">Standard</span><span class="sxs-lookup"><span data-stu-id="a39e6-108">Default</span></span>

```
Restart-Service [-Force] [-Name] <String[]> [-PassThru] [-Include <String[]>] [-Exclude <String[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="a39e6-109">DisplayName</span><span class="sxs-lookup"><span data-stu-id="a39e6-109">DisplayName</span></span>

```
Restart-Service [-Force] [-PassThru] -DisplayName <String[]> [-Include <String[]>] [-Exclude <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="a39e6-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a39e6-110">DESCRIPTION</span></span>

<span data-ttu-id="a39e6-111">Das **Restart-Service-** Cmdlet sendet eine Nachricht zum Abbrechen und eine Start Meldung an den Windows-Dienst Controller für einen angegebenen Dienst.</span><span class="sxs-lookup"><span data-stu-id="a39e6-111">The **Restart-Service** cmdlet sends a stop message and then a start message to the Windows Service Controller for a specified service.</span></span>
<span data-ttu-id="a39e6-112">Wenn ein Dienst bereits beendet wurde, wird er gestartet, ohne dass ein Fehler ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="a39e6-112">If a service was already stopped, it is started without notifying you of an error.</span></span>
<span data-ttu-id="a39e6-113">Sie können die Dienste mit ihren Dienstnamen oder anzeigen Amen angeben, oder Sie können mit dem *Inputobject* -Parameter ein Objekt übergeben, das die einzelnen neu zu startenden Dienste darstellt.</span><span class="sxs-lookup"><span data-stu-id="a39e6-113">You can specify the services by their service names or display names, or you can use the *InputObject* parameter to pass an object that represents each service that you want to restart.</span></span>

## <span data-ttu-id="a39e6-114">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="a39e6-114">EXAMPLES</span></span>

### <span data-ttu-id="a39e6-115">Beispiel 1: Neustarten eines Dienstanbieter auf dem lokalen Computer</span><span class="sxs-lookup"><span data-stu-id="a39e6-115">Example 1: Restart a service on the local computer</span></span>

```powershell
PS C:\> Restart-Service -Name winmgmt
```

<span data-ttu-id="a39e6-116">Mit diesem Befehl wird der WMI-Dienst (WinMgmt) auf dem lokalen Computer neu gestartet.</span><span class="sxs-lookup"><span data-stu-id="a39e6-116">This command restarts the Windows Management Instrumentation service (WinMgmt) on the local computer.</span></span>

### <span data-ttu-id="a39e6-117">Beispiel 2: Ausschließen eines Dienstanbieter</span><span class="sxs-lookup"><span data-stu-id="a39e6-117">Example 2: Exclude a service</span></span>

```powershell
PS C:\> Restart-Service -DisplayName "net*" -Exclude "net logon"
```

<span data-ttu-id="a39e6-118">Mit diesem Befehl werden die Dienste neu gestartet, deren Anzeige Name mit "NET" beginnt, mit Ausnahme des Anmelde Diensts.</span><span class="sxs-lookup"><span data-stu-id="a39e6-118">This command restarts the services that have a display name that starts with Net, except for the Net Logon service.</span></span>

### <span data-ttu-id="a39e6-119">Beispiel 3: Starten aller beendeten Netzwerkdienste</span><span class="sxs-lookup"><span data-stu-id="a39e6-119">Example 3: Start all stopped network services</span></span>

```powershell
PS C:\> Get-Service -Name "net*" | Where-Object {$_.Status -eq "Stopped"} | Restart-Service
```

<span data-ttu-id="a39e6-120">Mit diesem Befehl werden alle beendeten Netzwerkdienste auf dem Computer gestartet.</span><span class="sxs-lookup"><span data-stu-id="a39e6-120">This command starts all of the stopped network services on the computer.</span></span>

<span data-ttu-id="a39e6-121">Dieser Befehl verwendet das Cmdlet "Get-Service", um Objekte zu erhalten, die die Dienste darstellen, deren Dienst Name mit "NET" beginnt.</span><span class="sxs-lookup"><span data-stu-id="a39e6-121">This command uses the Get-Service cmdlet to get objects that represent the services whose service name starts with net.</span></span>
<span data-ttu-id="a39e6-122">Der Pipeline Operator (|) sendet das Dienst Objekt an das Cmdlet "Where-Object", das nur die Dienste auswählt, die den Status "beendet" aufweisen.</span><span class="sxs-lookup"><span data-stu-id="a39e6-122">The pipeline operator (|) sends the services object to the Where-Object cmdlet, which selects only the services that have a status of stopped.</span></span>
<span data-ttu-id="a39e6-123">Ein weiterer Pipeline Operator sendet die ausgewählten Dienste an **Restart-Service** .</span><span class="sxs-lookup"><span data-stu-id="a39e6-123">Another pipeline operator sends the selected services to **Restart-Service** .</span></span>

<span data-ttu-id="a39e6-124">In der Praxis verwenden Sie den *WhatIf* -Parameter, um die Auswirkung des Befehls zu ermitteln, bevor Sie ihn ausführen.</span><span class="sxs-lookup"><span data-stu-id="a39e6-124">In practice, you would use the *WhatIf* parameter to determine the effect of the command before you run it.</span></span>

## <span data-ttu-id="a39e6-125">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a39e6-125">PARAMETERS</span></span>

### <span data-ttu-id="a39e6-126">-DisplayName</span><span class="sxs-lookup"><span data-stu-id="a39e6-126">-DisplayName</span></span>

<span data-ttu-id="a39e6-127">Gibt die anzeigen Amen von Diensten an, die neu gestartet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="a39e6-127">Specifies the display names of services to restarted.</span></span>
<span data-ttu-id="a39e6-128">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="a39e6-128">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="a39e6-129">-Ausschließen</span><span class="sxs-lookup"><span data-stu-id="a39e6-129">-Exclude</span></span>

<span data-ttu-id="a39e6-130">Gibt die Dienste an, die von diesem Cmdlet ausgelassen werden.</span><span class="sxs-lookup"><span data-stu-id="a39e6-130">Specifies services that this cmdlet omits.</span></span>
<span data-ttu-id="a39e6-131">Der Wert dieses Parameters qualifiziert den *Name* -Parameter.</span><span class="sxs-lookup"><span data-stu-id="a39e6-131">The value of this parameter qualifies the *Name* parameter.</span></span>
<span data-ttu-id="a39e6-132">Geben Sie ein Namenselement oder-Muster ein, z. b. s \*.</span><span class="sxs-lookup"><span data-stu-id="a39e6-132">Enter a name element or pattern, such as s\*.</span></span>
<span data-ttu-id="a39e6-133">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="a39e6-133">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="a39e6-134">-Force</span><span class="sxs-lookup"><span data-stu-id="a39e6-134">-Force</span></span>

<span data-ttu-id="a39e6-135">Erzwingt die Ausführung des Befehls ohne Aufforderung zur Bestätigung durch den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="a39e6-135">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="a39e6-136">-Include</span><span class="sxs-lookup"><span data-stu-id="a39e6-136">-Include</span></span>

<span data-ttu-id="a39e6-137">Gibt die Dienste an, die von diesem Cmdlet neu gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="a39e6-137">Specifies services that this cmdlet restarts.</span></span>
<span data-ttu-id="a39e6-138">Der Wert dieses Parameters qualifiziert den *Name* -Parameter.</span><span class="sxs-lookup"><span data-stu-id="a39e6-138">The value of this parameter qualifies the *Name* parameter.</span></span>
<span data-ttu-id="a39e6-139">Geben Sie ein Namenselement oder-Muster ein, z. b. s \*.</span><span class="sxs-lookup"><span data-stu-id="a39e6-139">Enter a name element or pattern, such as s\*.</span></span>
<span data-ttu-id="a39e6-140">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="a39e6-140">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="a39e6-141">-InputObject</span><span class="sxs-lookup"><span data-stu-id="a39e6-141">-InputObject</span></span>

<span data-ttu-id="a39e6-142">Gibt **ServiceController** -Objekte an, die die neu zu Start-Dienste darstellen.</span><span class="sxs-lookup"><span data-stu-id="a39e6-142">Specifies **ServiceController** objects that represent the services to restart.</span></span>
<span data-ttu-id="a39e6-143">Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, mit dem die Objekte abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="a39e6-143">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

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

### <span data-ttu-id="a39e6-144">-Name</span><span class="sxs-lookup"><span data-stu-id="a39e6-144">-Name</span></span>

<span data-ttu-id="a39e6-145">Gibt die Dienstnamen der neu zu startenden Dienste an.</span><span class="sxs-lookup"><span data-stu-id="a39e6-145">Specifies the service names of the services to restart.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Default
Aliases: ServiceName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="a39e6-146">-PassThru</span><span class="sxs-lookup"><span data-stu-id="a39e6-146">-PassThru</span></span>

<span data-ttu-id="a39e6-147">Gibt ein Objekt zurück, das den Dienst darstellt.</span><span class="sxs-lookup"><span data-stu-id="a39e6-147">Returns an object that represents the service.</span></span>
<span data-ttu-id="a39e6-148">Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="a39e6-148">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="a39e6-149">-Confirm</span><span class="sxs-lookup"><span data-stu-id="a39e6-149">-Confirm</span></span>

<span data-ttu-id="a39e6-150">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="a39e6-150">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="a39e6-151">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="a39e6-151">-WhatIf</span></span>

<span data-ttu-id="a39e6-152">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a39e6-152">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="a39e6-153">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="a39e6-153">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="a39e6-154">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="a39e6-154">CommonParameters</span></span>

<span data-ttu-id="a39e6-155">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="a39e6-155">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a39e6-156">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="a39e6-156">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a39e6-157">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="a39e6-157">INPUTS</span></span>

### <span data-ttu-id="a39e6-158">System. ServiceProcess. ServiceController, System. String</span><span class="sxs-lookup"><span data-stu-id="a39e6-158">System.ServiceProcess.ServiceController, System.String</span></span>

<span data-ttu-id="a39e6-159">Sie können ein Dienst Objekt oder eine Zeichenfolge, die einen Dienstnamen enthält, über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="a39e6-159">You can pipe a service object or a string that contains a service name to this cmdlet.</span></span>

## <span data-ttu-id="a39e6-160">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="a39e6-160">OUTPUTS</span></span>

### <span data-ttu-id="a39e6-161">Keine, System. ServiceProcess. ServiceController</span><span class="sxs-lookup"><span data-stu-id="a39e6-161">None, System.ServiceProcess.ServiceController</span></span>

<span data-ttu-id="a39e6-162">Dieses Cmdlet generiert ein **System. ServiceProcess. ServiceController** -Objekt, das den neu gestarteten Dienst darstellt, wenn Sie den *passthru* -Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="a39e6-162">This cmdlet generates a **System.ServiceProcess.ServiceController** object that represents the restarted service, if you specify the *PassThru* parameter.</span></span>
<span data-ttu-id="a39e6-163">Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="a39e6-163">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="a39e6-164">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="a39e6-164">NOTES</span></span>

* <span data-ttu-id="a39e6-165">**Neustart: der Dienst** kann nur dann Dienste steuern, wenn der aktuelle Benutzer über die entsprechende Berechtigung verfügt.</span><span class="sxs-lookup"><span data-stu-id="a39e6-165">**Restart-Service** can control services only when the current user has permission to do this.</span></span> <span data-ttu-id="a39e6-166">Wenn ein Befehl nicht ordnungsgemäß verarbeitet wird, verfügen Sie u. U. nicht über die erforderlichen Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="a39e6-166">If a command does not work correctly, you might not have the required permissions.</span></span>
* <span data-ttu-id="a39e6-167">Um die Dienstnamen und anzeigen amen der Dienste auf Ihrem System zu suchen, geben **Sie Get-Service** "ein.</span><span class="sxs-lookup"><span data-stu-id="a39e6-167">To find the service names and display names of the services on your system, type **Get-Service** ".</span></span> <span data-ttu-id="a39e6-168">Die Dienstnamen werden in der Spalte **Name** angezeigt, und die anzeigen Amen werden in der Spalte **Display Name** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a39e6-168">The service names appear in the **Name** column, and the display names appear in the **DisplayName** column.</span></span>

## <span data-ttu-id="a39e6-169">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="a39e6-169">RELATED LINKS</span></span>

[<span data-ttu-id="a39e6-170">Get-Service</span><span class="sxs-lookup"><span data-stu-id="a39e6-170">Get-Service</span></span>](Get-Service.md)

[<span data-ttu-id="a39e6-171">New-Service</span><span class="sxs-lookup"><span data-stu-id="a39e6-171">New-Service</span></span>](New-Service.md)

[<span data-ttu-id="a39e6-172">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="a39e6-172">Resume-Service</span></span>](Resume-Service.md)

[<span data-ttu-id="a39e6-173">Set-Service</span><span class="sxs-lookup"><span data-stu-id="a39e6-173">Set-Service</span></span>](Set-Service.md)

[<span data-ttu-id="a39e6-174">Start-Service</span><span class="sxs-lookup"><span data-stu-id="a39e6-174">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="a39e6-175">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="a39e6-175">Stop-Service</span></span>](Stop-Service.md)

[<span data-ttu-id="a39e6-176">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="a39e6-176">Suspend-Service</span></span>](Suspend-Service.md)

[<span data-ttu-id="a39e6-177">Remove-Service</span><span class="sxs-lookup"><span data-stu-id="a39e6-177">Remove-Service</span></span>](Remove-Service.md)
