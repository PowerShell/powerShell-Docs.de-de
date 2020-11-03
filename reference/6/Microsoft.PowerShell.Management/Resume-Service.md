---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/resume-service?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Resume-Service
ms.openlocfilehash: 00de396b049259904433843e01879c75e3982ca1
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212300"
---
# <span data-ttu-id="9f939-103">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="9f939-103">Resume-Service</span></span>

## <span data-ttu-id="9f939-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="9f939-104">SYNOPSIS</span></span>
<span data-ttu-id="9f939-105">Setzt angehaltene (unterbrochene) Dienste fort.</span><span class="sxs-lookup"><span data-stu-id="9f939-105">Resumes one or more suspended (paused) services.</span></span>

## <span data-ttu-id="9f939-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9f939-106">SYNTAX</span></span>

### <span data-ttu-id="9f939-107">Inputobject (Standard)</span><span class="sxs-lookup"><span data-stu-id="9f939-107">InputObject (Default)</span></span>

```
Resume-Service [-InputObject] <ServiceController[]> [-PassThru] [-Include <String[]>] [-Exclude <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="9f939-108">Standard</span><span class="sxs-lookup"><span data-stu-id="9f939-108">Default</span></span>

```
Resume-Service [-Name] <String[]> [-PassThru] [-Include <String[]>] [-Exclude <String[]>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="9f939-109">DisplayName</span><span class="sxs-lookup"><span data-stu-id="9f939-109">DisplayName</span></span>

```
Resume-Service [-PassThru] -DisplayName <String[]> [-Include <String[]>] [-Exclude <String[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="9f939-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9f939-110">DESCRIPTION</span></span>

<span data-ttu-id="9f939-111">Das **Resume-Service-** Cmdlet sendet für jeden der angegebenen Dienste eine Fortsetzungs Meldung an den Windows-Dienst Controller.</span><span class="sxs-lookup"><span data-stu-id="9f939-111">The **Resume-Service** cmdlet sends a resume message to the Windows Service Controller for each of the specified services.</span></span>
<span data-ttu-id="9f939-112">Wenn ein Dienst angehalten wird, wird er fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="9f939-112">If a service is suspended, it resumes.</span></span>
<span data-ttu-id="9f939-113">Wenn er gerade ausgeführt wird, wird die Meldung ignoriert.</span><span class="sxs-lookup"><span data-stu-id="9f939-113">If it is currently running, the message is ignored.</span></span>
<span data-ttu-id="9f939-114">Sie können die Dienste mit ihren Dienstnamen oder anzeigen Amen angeben, oder Sie können mit dem *Inputobject* -Parameter ein Dienst Objekt übergeben, das die wiederherzustellenden Dienste darstellt.</span><span class="sxs-lookup"><span data-stu-id="9f939-114">You can specify the services by their service names or display names, or you can use the *InputObject* parameter to pass a service object that represents the services that you want to resume.</span></span>

## <span data-ttu-id="9f939-115">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="9f939-115">EXAMPLES</span></span>

### <span data-ttu-id="9f939-116">Beispiel 1: Fortsetzen eines Dienstanbieter auf dem lokalen Computer</span><span class="sxs-lookup"><span data-stu-id="9f939-116">Example 1: Resume a service on the local computer</span></span>

```
PS C:\> Resume-Service "sens"
```

<span data-ttu-id="9f939-117">Mit diesem Befehl wird der System Ereignis Benachrichtigungsdienst auf dem lokalen Computer fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="9f939-117">This command resumes the System Event Notification service  on the local computer.</span></span>
<span data-ttu-id="9f939-118">Der Dienst Name wird im Befehl von Sens dargestellt.</span><span class="sxs-lookup"><span data-stu-id="9f939-118">The service name is represented in the command by sens.</span></span>
<span data-ttu-id="9f939-119">Der Befehl verwendet den *Name* -Parameter, um den Dienstnamen des Dienstanbieter anzugeben, aber der Befehl lässt den Parameternamen aus, da der Parameter Name optional ist.</span><span class="sxs-lookup"><span data-stu-id="9f939-119">The command uses the *Name* parameter to specify the service name of the service, but the command omits the parameter name because the parameter name is optional.</span></span>

### <span data-ttu-id="9f939-120">Beispiel 2: Fortsetzen aller angehaltenen Dienste</span><span class="sxs-lookup"><span data-stu-id="9f939-120">Example 2: Resume all suspended services</span></span>

```
PS C:\> Get-Service | Where-Object {$_.Status -eq "Paused"} | Resume-Service
```

<span data-ttu-id="9f939-121">Mit diesem Befehl werden alle angehaltenen Dienste auf dem Computer fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="9f939-121">This command resumes all of the suspended  services on the computer.</span></span>
<span data-ttu-id="9f939-122">Mit dem Befehl "Get-Service Cmdlet" werden alle Dienste auf dem Computer abgerufen.</span><span class="sxs-lookup"><span data-stu-id="9f939-122">The Get-Service cmdlet command gets all of the services on the computer.</span></span>
<span data-ttu-id="9f939-123">Der Pipeline Operator (|) übergibt die Ergebnisse an das Where-Object-Cmdlet, das die Dienste auswählt, deren **Status** -Eigenschaft angehalten ist.</span><span class="sxs-lookup"><span data-stu-id="9f939-123">The pipeline operator (|) passes the results to the Where-Object cmdlet, which selects the services that have a **Status** property of Paused.</span></span>
<span data-ttu-id="9f939-124">Der nächste Pipeline Operator sendet die Ergebnisse an **Resume-Service** , wodurch die angehaltenen Dienste fortgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="9f939-124">The next pipeline operator sends the results to **Resume-Service** , which resumes the paused services.</span></span>

<span data-ttu-id="9f939-125">In der Praxis verwenden Sie den *WhatIf* -Parameter, um die Auswirkung des Befehls zu ermitteln, bevor Sie ihn ausführen.</span><span class="sxs-lookup"><span data-stu-id="9f939-125">In practice, you would use the *WhatIf* parameter to determine the effect of the command before you run it.</span></span>

## <span data-ttu-id="9f939-126">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9f939-126">PARAMETERS</span></span>

### <span data-ttu-id="9f939-127">-DisplayName</span><span class="sxs-lookup"><span data-stu-id="9f939-127">-DisplayName</span></span>

<span data-ttu-id="9f939-128">Gibt die Anzeigenamen der fortzusetzenden Dienste an.</span><span class="sxs-lookup"><span data-stu-id="9f939-128">Specifies the display names of the services to be resumed.</span></span>
<span data-ttu-id="9f939-129">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="9f939-129">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="9f939-130">-Ausschließen</span><span class="sxs-lookup"><span data-stu-id="9f939-130">-Exclude</span></span>

<span data-ttu-id="9f939-131">Gibt die Dienste an, die von diesem Cmdlet ausgelassen werden.</span><span class="sxs-lookup"><span data-stu-id="9f939-131">Specifies services that this cmdlet omits.</span></span>
<span data-ttu-id="9f939-132">Der Wert dieses Parameters qualifiziert den *Name* -Parameter.</span><span class="sxs-lookup"><span data-stu-id="9f939-132">The value of this parameter qualifies the *Name* parameter.</span></span>
<span data-ttu-id="9f939-133">Geben Sie ein Namenselement oder-Muster ein, z. b. s \*.</span><span class="sxs-lookup"><span data-stu-id="9f939-133">Enter a name element or pattern, such as s\*.</span></span>
<span data-ttu-id="9f939-134">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="9f939-134">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="9f939-135">-Include</span><span class="sxs-lookup"><span data-stu-id="9f939-135">-Include</span></span>

<span data-ttu-id="9f939-136">Gibt Dienste zum Fortsetzen an.</span><span class="sxs-lookup"><span data-stu-id="9f939-136">Specifies services to resume.</span></span>
<span data-ttu-id="9f939-137">Der Wert dieses Parameters qualifiziert den *Name* -Parameter.</span><span class="sxs-lookup"><span data-stu-id="9f939-137">The value of this parameter qualifies *Name* parameter.</span></span>
<span data-ttu-id="9f939-138">Geben Sie ein Namenselement oder-Muster ein, z. b. s \*.</span><span class="sxs-lookup"><span data-stu-id="9f939-138">Enter a name element or pattern, such as s\*.</span></span>
<span data-ttu-id="9f939-139">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="9f939-139">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="9f939-140">-InputObject</span><span class="sxs-lookup"><span data-stu-id="9f939-140">-InputObject</span></span>

<span data-ttu-id="9f939-141">Gibt **ServiceController** -Objekte an, die die fort zusetzenden Dienste darstellen.</span><span class="sxs-lookup"><span data-stu-id="9f939-141">Specifies **ServiceController** objects that represent the services to resumed.</span></span>
<span data-ttu-id="9f939-142">Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, mit dem die Objekte abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="9f939-142">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

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

### <span data-ttu-id="9f939-143">-Name</span><span class="sxs-lookup"><span data-stu-id="9f939-143">-Name</span></span>

<span data-ttu-id="9f939-144">Gibt die Dienstnamen der fortzusetzenden Dienste an.</span><span class="sxs-lookup"><span data-stu-id="9f939-144">Specifies the service names of the services to be resumed.</span></span>

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

### <span data-ttu-id="9f939-145">-PassThru</span><span class="sxs-lookup"><span data-stu-id="9f939-145">-PassThru</span></span>

<span data-ttu-id="9f939-146">Gibt ein Objekt zurück, das den Dienst darstellt.</span><span class="sxs-lookup"><span data-stu-id="9f939-146">Returns an object that represents the service.</span></span>
<span data-ttu-id="9f939-147">Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="9f939-147">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="9f939-148">-Confirm</span><span class="sxs-lookup"><span data-stu-id="9f939-148">-Confirm</span></span>

<span data-ttu-id="9f939-149">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="9f939-149">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="9f939-150">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="9f939-150">-WhatIf</span></span>

<span data-ttu-id="9f939-151">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="9f939-151">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="9f939-152">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="9f939-152">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="9f939-153">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="9f939-153">CommonParameters</span></span>

<span data-ttu-id="9f939-154">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="9f939-154">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="9f939-155">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="9f939-155">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="9f939-156">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="9f939-156">INPUTS</span></span>

### <span data-ttu-id="9f939-157">System. ServiceProcess. ServiceController, System. String</span><span class="sxs-lookup"><span data-stu-id="9f939-157">System.ServiceProcess.ServiceController, System.String</span></span>

<span data-ttu-id="9f939-158">Sie können ein Dienst Objekt oder eine Zeichenfolge, die einen Dienstnamen enthält, über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="9f939-158">You can pipe a service object or a string that contains a service name to this cmdlet.</span></span>

## <span data-ttu-id="9f939-159">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="9f939-159">OUTPUTS</span></span>

### <span data-ttu-id="9f939-160">Keine, System. ServiceProcess. ServiceController</span><span class="sxs-lookup"><span data-stu-id="9f939-160">None, System.ServiceProcess.ServiceController</span></span>

<span data-ttu-id="9f939-161">Dieses Cmdlet generiert ein **System. ServiceProcess. ServiceController** -Objekt, das den fortgesetzten Dienst darstellt, wenn Sie den *passthru* -Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="9f939-161">This cmdlet generates a **System.ServiceProcess.ServiceController** object that represents the resumed service, if you specify the *PassThru* parameter.</span></span>
<span data-ttu-id="9f939-162">Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="9f939-162">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="9f939-163">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="9f939-163">NOTES</span></span>

* <span data-ttu-id="9f939-164">Der Status von Diensten, die angehalten wurden, wurde angehalten.</span><span class="sxs-lookup"><span data-stu-id="9f939-164">The status of services that have been suspended is Paused.</span></span> <span data-ttu-id="9f939-165">Wenn Dienste fortgesetzt werden, lautet Ihr Status wird ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="9f939-165">When services are resumed, their status is Running.</span></span>
* <span data-ttu-id="9f939-166">**Resume-Service** kann Dienste nur steuern, wenn der aktuelle Benutzer über die entsprechende Berechtigung verfügt.</span><span class="sxs-lookup"><span data-stu-id="9f939-166">**Resume-Service** can control services only when the current user has permission to do this.</span></span> <span data-ttu-id="9f939-167">Wenn ein Befehl nicht ordnungsgemäß verarbeitet wird, verfügen Sie u. U. nicht über die erforderlichen Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="9f939-167">If a command does not work correctly, you might not have the required permissions.</span></span>
* <span data-ttu-id="9f939-168">Geben Sie ein, um die Dienstnamen und anzeigen amen der Dienste auf dem System zu suchen `Get-Service` .</span><span class="sxs-lookup"><span data-stu-id="9f939-168">To find the service names and display names of the services on your system, type `Get-Service`.</span></span> <span data-ttu-id="9f939-169">Die Dienstnamen werden in der Spalte **Name** angezeigt, und die anzeigen Amen werden in der Spalte **Display Name** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9f939-169">The service names appear in the **Name** column, and the display names appear in the **DisplayName** column.</span></span>

## <span data-ttu-id="9f939-170">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="9f939-170">RELATED LINKS</span></span>

[<span data-ttu-id="9f939-171">Get-Service</span><span class="sxs-lookup"><span data-stu-id="9f939-171">Get-Service</span></span>](Get-Service.md)

[<span data-ttu-id="9f939-172">New-Service</span><span class="sxs-lookup"><span data-stu-id="9f939-172">New-Service</span></span>](New-Service.md)

[<span data-ttu-id="9f939-173">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="9f939-173">Restart-Service</span></span>](Restart-Service.md)

[<span data-ttu-id="9f939-174">Set-Service</span><span class="sxs-lookup"><span data-stu-id="9f939-174">Set-Service</span></span>](Set-Service.md)

[<span data-ttu-id="9f939-175">Start-Service</span><span class="sxs-lookup"><span data-stu-id="9f939-175">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="9f939-176">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="9f939-176">Stop-Service</span></span>](Stop-Service.md)

[<span data-ttu-id="9f939-177">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="9f939-177">Suspend-Service</span></span>](Suspend-Service.md)

[<span data-ttu-id="9f939-178">Remove-Service</span><span class="sxs-lookup"><span data-stu-id="9f939-178">Remove-Service</span></span>](Remove-Service.md)