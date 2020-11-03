---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 07/21/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/remove-variable?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-Variable
ms.openlocfilehash: c6347ea9ca2169c6379871131bc98001bcdb5d25
ms.sourcegitcommit: 84fcc90bd018ab76ac4e964d53e7c9c2b5a7b6c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2020
ms.locfileid: "93218884"
---
# <span data-ttu-id="20605-103">Remove-Variable</span><span class="sxs-lookup"><span data-stu-id="20605-103">Remove-Variable</span></span>

## <span data-ttu-id="20605-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="20605-104">SYNOPSIS</span></span>
<span data-ttu-id="20605-105">Löscht eine Variable und ihren Wert.</span><span class="sxs-lookup"><span data-stu-id="20605-105">Deletes a variable and its value.</span></span>

## <span data-ttu-id="20605-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="20605-106">SYNTAX</span></span>

```
Remove-Variable [-Name] <String[]> [-Include <String[]>] [-Exclude <String[]>] [-Force] [-Scope <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="20605-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="20605-107">DESCRIPTION</span></span>

<span data-ttu-id="20605-108">Das `Remove-Variable` -Cmdlet löscht eine Variable und ihren Wert aus dem Gültigkeitsbereich, in dem Sie definiert ist, z. b. die aktuelle Sitzung.</span><span class="sxs-lookup"><span data-stu-id="20605-108">The `Remove-Variable` cmdlet deletes a variable and its value from the scope in which it is defined, such as the current session.</span></span> <span data-ttu-id="20605-109">Mit diesem Cmdlet können Sie Variablen löschen, die als Konstanten festgelegt sind, oder solche, die dem System gehören.</span><span class="sxs-lookup"><span data-stu-id="20605-109">You cannot use this cmdlet to delete variables that are set as constants or those that are owned by the system.</span></span>

## <span data-ttu-id="20605-110">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="20605-110">EXAMPLES</span></span>

### <span data-ttu-id="20605-111">Beispiel 1: Entfernen einer Variablen</span><span class="sxs-lookup"><span data-stu-id="20605-111">Example 1: Remove a variable</span></span>

```powershell
Remove-Variable Smp
```

<span data-ttu-id="20605-112">Mit diesem Befehl wird die `$Smp` Variable gelöscht.</span><span class="sxs-lookup"><span data-stu-id="20605-112">This command deletes the `$Smp` variable.</span></span>

## <span data-ttu-id="20605-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="20605-113">PARAMETERS</span></span>

### <span data-ttu-id="20605-114">-Ausschließen</span><span class="sxs-lookup"><span data-stu-id="20605-114">-Exclude</span></span>

<span data-ttu-id="20605-115">Gibt ein Array von Elementen an, die von diesem Cmdlet aus dem Vorgang ausgelassen werden.</span><span class="sxs-lookup"><span data-stu-id="20605-115">Specifies an array of items that this cmdlet omits from the operation.</span></span> <span data-ttu-id="20605-116">Der Wert dieses Parameters qualifiziert den **Name** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="20605-116">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="20605-117">Geben Sie ein Namenselement oder -muster wie %%amp;quot;s\*%%amp;quot; ein.</span><span class="sxs-lookup"><span data-stu-id="20605-117">Enter a name element or pattern, such as "s\*".</span></span> <span data-ttu-id="20605-118">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="20605-118">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="20605-119">-Force</span><span class="sxs-lookup"><span data-stu-id="20605-119">-Force</span></span>

<span data-ttu-id="20605-120">Gibt an, dass das Cmdlet eine Variable entfernt, auch wenn Sie schreibgeschützt ist.</span><span class="sxs-lookup"><span data-stu-id="20605-120">Indicates that the cmdlet removes a variable even if it is read-only.</span></span> <span data-ttu-id="20605-121">Selbst bei Verwendung des **Force** -Parameters kann das Cmdlet keine Konstante entfernen.</span><span class="sxs-lookup"><span data-stu-id="20605-121">Even using the **Force** parameter, the cmdlet cannot remove a constant.</span></span>

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

### <span data-ttu-id="20605-122">-Include</span><span class="sxs-lookup"><span data-stu-id="20605-122">-Include</span></span>

<span data-ttu-id="20605-123">Gibt ein Array von Elementen an, die dieses Cmdlet im Vorgang löscht.</span><span class="sxs-lookup"><span data-stu-id="20605-123">Specifies an array of items that this cmdlet deletes in the operation.</span></span> <span data-ttu-id="20605-124">Der Wert dieses Parameters qualifiziert den **Name** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="20605-124">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="20605-125">Geben Sie ein Namenselement oder-Muster ein, z. b. s \*.</span><span class="sxs-lookup"><span data-stu-id="20605-125">Enter a name element or pattern, such as s\*.</span></span> <span data-ttu-id="20605-126">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="20605-126">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="20605-127">-Name</span><span class="sxs-lookup"><span data-stu-id="20605-127">-Name</span></span>

<span data-ttu-id="20605-128">Gibt den Namen der zu entfernenden Variablen an.</span><span class="sxs-lookup"><span data-stu-id="20605-128">Specifies the name of the variable to be removed.</span></span> <span data-ttu-id="20605-129">Der Parameter Name ( **Name** ) ist optional.</span><span class="sxs-lookup"><span data-stu-id="20605-129">The parameter name ( **Name** ) is optional.</span></span>
<span data-ttu-id="20605-130">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="20605-130">Wildcards are permitted</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="20605-131">-Bereich</span><span class="sxs-lookup"><span data-stu-id="20605-131">-Scope</span></span>

<span data-ttu-id="20605-132">Ruft nur die Variablen im angegebenen Bereich ab.</span><span class="sxs-lookup"><span data-stu-id="20605-132">Gets only the variables in the specified scope.</span></span> <span data-ttu-id="20605-133">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="20605-133">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="20605-134">Global</span><span class="sxs-lookup"><span data-stu-id="20605-134">Global</span></span>
- <span data-ttu-id="20605-135">Lokal</span><span class="sxs-lookup"><span data-stu-id="20605-135">Local</span></span>
- <span data-ttu-id="20605-136">Skript</span><span class="sxs-lookup"><span data-stu-id="20605-136">Script</span></span>
- <span data-ttu-id="20605-137">Eine Zahl relativ zum aktuellen Bereich (0 bis zur Anzahl der Bereiche, wobei 0 der aktuelle Bereich und 1 der übergeordnete Bereich ist)</span><span class="sxs-lookup"><span data-stu-id="20605-137">A number relative to the current scope (0 through the number of scopes, where 0 is the current scope and 1 is its parent)</span></span>

<span data-ttu-id="20605-138">Local ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="20605-138">Local is the default.</span></span> <span data-ttu-id="20605-139">Weitere Informationen finden Sie unter [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).</span><span class="sxs-lookup"><span data-stu-id="20605-139">For more information, see [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="20605-140">-Confirm</span><span class="sxs-lookup"><span data-stu-id="20605-140">-Confirm</span></span>

<span data-ttu-id="20605-141">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="20605-141">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="20605-142">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="20605-142">-WhatIf</span></span>

<span data-ttu-id="20605-143">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="20605-143">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="20605-144">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="20605-144">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="20605-145">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="20605-145">CommonParameters</span></span>

<span data-ttu-id="20605-146">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="20605-146">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="20605-147">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="20605-147">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="20605-148">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="20605-148">INPUTS</span></span>

### <span data-ttu-id="20605-149">System. Management. Automation. psvariable</span><span class="sxs-lookup"><span data-stu-id="20605-149">System.Management.Automation.PSVariable</span></span>

<span data-ttu-id="20605-150">Sie können ein Variablen Objekt an übergeben `Remove-Variable` .</span><span class="sxs-lookup"><span data-stu-id="20605-150">You can pipe a variable object to `Remove-Variable`.</span></span>

## <span data-ttu-id="20605-151">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="20605-151">OUTPUTS</span></span>

### <span data-ttu-id="20605-152">Keine</span><span class="sxs-lookup"><span data-stu-id="20605-152">None</span></span>

<span data-ttu-id="20605-153">Dieses Cmdlet gibt keine Ausgabe zurück.</span><span class="sxs-lookup"><span data-stu-id="20605-153">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="20605-154">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="20605-154">NOTES</span></span>

- <span data-ttu-id="20605-155">Änderungen wirken sich nur auf den aktuellen Bereich aus, z. B. eine Sitzung.</span><span class="sxs-lookup"><span data-stu-id="20605-155">Changes affect only the current scope, such as a session.</span></span> <span data-ttu-id="20605-156">Um eine Variable aus allen Sitzungen zu löschen, fügen Sie `Remove-Variable` Ihrem PowerShell-Profil einen Befehl hinzu.</span><span class="sxs-lookup"><span data-stu-id="20605-156">To delete a variable from all sessions, add a `Remove-Variable` command to your PowerShell profile.</span></span>

- <span data-ttu-id="20605-157">Sie können auch auf den `Remove-Variable` integrierten Alias verweisen `rv` .</span><span class="sxs-lookup"><span data-stu-id="20605-157">You can also refer to `Remove-Variable` by its built-in alias, `rv`.</span></span> <span data-ttu-id="20605-158">Weitere Informationen finden Sie unter [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="20605-158">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>

## <span data-ttu-id="20605-159">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="20605-159">RELATED LINKS</span></span>

[<span data-ttu-id="20605-160">Clear-Variable</span><span class="sxs-lookup"><span data-stu-id="20605-160">Clear-Variable</span></span>](Clear-Variable.md)

[<span data-ttu-id="20605-161">Get-Variable</span><span class="sxs-lookup"><span data-stu-id="20605-161">Get-Variable</span></span>](Get-Variable.md)

[<span data-ttu-id="20605-162">New-Variable</span><span class="sxs-lookup"><span data-stu-id="20605-162">New-Variable</span></span>](New-Variable.md)

[<span data-ttu-id="20605-163">Set-Variable</span><span class="sxs-lookup"><span data-stu-id="20605-163">Set-Variable</span></span>](Set-Variable.md)