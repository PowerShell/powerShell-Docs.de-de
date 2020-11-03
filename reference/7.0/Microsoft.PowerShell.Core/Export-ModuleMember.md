---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/export-modulemember?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-ModuleMember
ms.openlocfilehash: 8d99f861a9cbdc72d30975275c49c6cd5bde2bed
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93211327"
---
# <span data-ttu-id="e7969-103">Export-ModuleMember</span><span class="sxs-lookup"><span data-stu-id="e7969-103">Export-ModuleMember</span></span>

## <span data-ttu-id="e7969-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="e7969-104">SYNOPSIS</span></span>
<span data-ttu-id="e7969-105">Gibt die Modulelemente an, die exportiert werden.</span><span class="sxs-lookup"><span data-stu-id="e7969-105">Specifies the module members that are exported.</span></span>

## <span data-ttu-id="e7969-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e7969-106">SYNTAX</span></span>

```
Export-ModuleMember [[-Function] <String[]>] [-Cmdlet <String[]>] [-Variable <String[]>] [-Alias <String[]>]
 [<CommonParameters>]
```

## <span data-ttu-id="e7969-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e7969-107">DESCRIPTION</span></span>

<span data-ttu-id="e7969-108">Das **Export-modulemember** -Cmdlet gibt die Modul Elemente an, die aus einer Skript Modul Datei (. psm1) exportiert werden, oder aus einem dynamischen Modul, das mit dem Cmdlet "New-Module" erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="e7969-108">The **Export-ModuleMember** cmdlet specifies the module members that are exported from a script module (.psm1) file, or from a dynamic module created by using the New-Module cmdlet.</span></span>
<span data-ttu-id="e7969-109">Zu den Modulmembern gehören Cmdlets, Funktionen, Variablen und Aliase.</span><span class="sxs-lookup"><span data-stu-id="e7969-109">Module members include cmdlets, functions, variables, and aliases.</span></span>
<span data-ttu-id="e7969-110">Dieses Cmdlet kann nur in einer Skriptmoduldatei oder einem dynamischen Modul verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e7969-110">This cmdlet can be used only in a script module file or a dynamic module.</span></span>

<span data-ttu-id="e7969-111">Wenn ein Skript Modul keinen **Export-modulemember** -Befehl enthält, werden die Funktionen und Aliase im Skript Modul exportiert, die Variablen jedoch nicht.</span><span class="sxs-lookup"><span data-stu-id="e7969-111">If a script module does not include an **Export-ModuleMember** command, the functions and aliases in the script module are exported, but the variables are not.</span></span>
<span data-ttu-id="e7969-112">Wenn ein Skript Modul **Export-modulemember** -Befehle enthält, werden nur die Elemente exportiert, die in den **Export-modulemember** -Befehlen angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="e7969-112">When a script module includes **Export-ModuleMember** commands, only the members specified in the **Export-ModuleMember** commands are exported.</span></span>
<span data-ttu-id="e7969-113">Sie können **Export-modulemember** auch verwenden, um Member, die das Skript Modul aus anderen Modulen importiert, zu unterdrücken oder zu exportieren.</span><span class="sxs-lookup"><span data-stu-id="e7969-113">You can also use **Export-ModuleMember** to suppress or export members that the script module imports from other modules.</span></span>

<span data-ttu-id="e7969-114">Ein **Export-modulemember** -Befehl ist optional, aber es handelt sich um eine bewährte Vorgehensweise.</span><span class="sxs-lookup"><span data-stu-id="e7969-114">An **Export-ModuleMember** command is optional, but it is a best practice.</span></span>
<span data-ttu-id="e7969-115">Auch wenn der Befehl die Standardwerte bestätigt, wird die Absicht des Modulautors veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="e7969-115">Even if the command confirms the default values, it demonstrates the intention of the module author.</span></span>

## <span data-ttu-id="e7969-116">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="e7969-116">EXAMPLES</span></span>

### <span data-ttu-id="e7969-117">Beispiel 1: Exportieren von Funktionen und Aliasen in einem Skript Modul</span><span class="sxs-lookup"><span data-stu-id="e7969-117">Example 1: Export functions and aliases in a script module</span></span>

```powershell
Export-ModuleMember -Function * -Alias *
```

<span data-ttu-id="e7969-118">Dieser Befehl exportiert alle Funktionen und Aliase, die im Skript Modul definiert sind.</span><span class="sxs-lookup"><span data-stu-id="e7969-118">This command exports all the functions and aliases defined in the script module.</span></span>

### <span data-ttu-id="e7969-119">Beispiel 2: Exportieren spezifischer Aliase und Funktionen</span><span class="sxs-lookup"><span data-stu-id="e7969-119">Example 2: Export specific aliases and functions</span></span>

```powershell
Export-ModuleMember -Function Get-Test, New-Test, Start-Test -Alias gtt, ntt, stt
```

<span data-ttu-id="e7969-120">Dieser Befehl exportiert die drei Aliase und drei Funktionen, die im Skriptmodul definiert sind.</span><span class="sxs-lookup"><span data-stu-id="e7969-120">This command exports three aliases and three functions defined in the script module.</span></span>

<span data-ttu-id="e7969-121">Verwenden Sie dieses Befehlsformat, um Namen der Modulelemente anzugeben.</span><span class="sxs-lookup"><span data-stu-id="e7969-121">You can use this command format to specify the names of module members.</span></span>

### <span data-ttu-id="e7969-122">Beispiel 3: Exportieren von keinen Membern</span><span class="sxs-lookup"><span data-stu-id="e7969-122">Example 3: Export no members</span></span>

```powershell
Export-ModuleMember
```

<span data-ttu-id="e7969-123">Dieser Befehl gibt an, dass keine im Skriptmodul definierten Elemente exportiert werden.</span><span class="sxs-lookup"><span data-stu-id="e7969-123">This command specifies that no members defined in the script module are exported.</span></span>

<span data-ttu-id="e7969-124">Dieser Befehl verhindert, dass Modulelemente exportiert werden, blendet die Elemente aber nicht aus.</span><span class="sxs-lookup"><span data-stu-id="e7969-124">This command prevents the module members from being exported, but it does not hide the members.</span></span>
<span data-ttu-id="e7969-125">Die Benutzer können Modulelemente lesen und kopieren oder den Aufrufoperator (&) verwenden, um Modulelemente aufzurufen, die nicht exportiert werden.</span><span class="sxs-lookup"><span data-stu-id="e7969-125">Users can read and copy module members or use the call operator (&) to invoke module members that are not exported.</span></span>

### <span data-ttu-id="e7969-126">Beispiel 4: Exportieren einer bestimmten Variablen</span><span class="sxs-lookup"><span data-stu-id="e7969-126">Example 4: Export a specific variable</span></span>

```powershell
Export-ModuleMember -Variable increment
```

<span data-ttu-id="e7969-127">Dieser Befehl exportiert nur die $increment-Variable aus dem Skriptmodul.</span><span class="sxs-lookup"><span data-stu-id="e7969-127">This command exports only the $increment variable from the script module.</span></span>
<span data-ttu-id="e7969-128">Keine anderen Elemente werden exportiert.</span><span class="sxs-lookup"><span data-stu-id="e7969-128">No other members are exported.</span></span>

<span data-ttu-id="e7969-129">Wenn Sie eine Variable exportieren möchten, zusätzlich zum Exportieren der Funktionen in einem Modul, muss der **Export-modulemember** -Befehl die Namen aller Funktionen und den Namen der Variablen enthalten.</span><span class="sxs-lookup"><span data-stu-id="e7969-129">If you want to export a variable, in addition to exporting the functions in a module, the **Export-ModuleMember** command must include the names of all of the functions and the name of the variable.</span></span>

### <span data-ttu-id="e7969-130">Beispiel 5: mehrere Export Befehle</span><span class="sxs-lookup"><span data-stu-id="e7969-130">Example 5: Multiple export commands</span></span>

```powershell
# From TestModule.psm1
Function New-Test
{
    Write-Output 'I am New-Test function'
}
Export-ModuleMember -Function New-Test

function Validate-Test
{
    Write-Output 'I am Validate-Test function'
}
function Start-Test
{
    Write-Output 'I am Start-Test function'
}
Set-Alias stt Start-Test
Export-ModuleMember -Function Start-Test -Alias stt
```

<span data-ttu-id="e7969-131">Diese Befehle zeigen, wie mehrere **Export-modulemember** -Befehle in einer Skript Modul Datei (. psm1) interpretiert werden.</span><span class="sxs-lookup"><span data-stu-id="e7969-131">These commands show how multiple **Export-ModuleMember** commands are interpreted in a script module (.psm1) file.</span></span>

<span data-ttu-id="e7969-132">Diese Befehle erstellen drei Funktionen und einen Alias und exportieren sie dann.</span><span class="sxs-lookup"><span data-stu-id="e7969-132">These commands create three functions and one alias, and then they export two of the functions and the alias.</span></span>

<span data-ttu-id="e7969-133">Ohne die **Export-modulemember** -Befehle würden alle drei Funktionen und der Alias exportiert werden.</span><span class="sxs-lookup"><span data-stu-id="e7969-133">Without the **Export-ModuleMember** commands, all three of the functions and the alias would be exported.</span></span>
<span data-ttu-id="e7969-134">Mit den **Export-modulemember** -Befehlen werden nur die Funktionen **New-Test** und **Start-Test** und der STT-Alias exportiert.</span><span class="sxs-lookup"><span data-stu-id="e7969-134">With the **Export-ModuleMember** commands, only the **New-Test** and **Start-Test** functions and the STT alias are exported.</span></span>

### <span data-ttu-id="e7969-135">Beispiel 6: Exportieren von Membern in einem dynamischen Modul</span><span class="sxs-lookup"><span data-stu-id="e7969-135">Example 6: Export members in a dynamic module</span></span>

```powershell
New-Module -Script {function SayHello {"Hello!"}; Set-Alias Hi SayHello; Export-ModuleMember -Alias Hi -Function SayHello}
```

<span data-ttu-id="e7969-136">Dieser Befehl zeigt, wie Export-ModuleMember in einem dynamischen Modul verwendet wird, das mit dem **New-Module-** Cmdlet erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="e7969-136">This command shows how to use Export-ModuleMember in a dynamic module that is created by using the **New-Module** cmdlet.</span></span>

<span data-ttu-id="e7969-137">In diesem Beispiel wird **Export-modulemember** zum Exportieren des HI-Alias und der Funktion " **sayHello** " im dynamischen Modul verwendet.</span><span class="sxs-lookup"><span data-stu-id="e7969-137">In this example, **Export-ModuleMember** is used to export both the Hi alias and the **SayHello** function in the dynamic module.</span></span>

### <span data-ttu-id="e7969-138">Beispiel 7: Deklarieren und Exportieren einer Funktion in einem einzelnen Befehl</span><span class="sxs-lookup"><span data-stu-id="e7969-138">Example 7: Declare and export a function in a single command</span></span>

```powershell
# From TestModule.psm1
function Export
{
  param (
    [Parameter(Mandatory=$true)]
    [ValidateSet("function","variable")]
    $Type,
    [Parameter(Mandatory=$true)]
    $Name,
    [Parameter(Mandatory=$true)]
    $Value
    )

    if ($Type -eq "function")
    {
        Set-item "function:script:$Name" $Value
        Export-ModuleMember $Name
    }
    else
    {
    Set-Variable -scope Script $Name $Value
    Export-ModuleMember -variable $Name
    }
}

Export function New-Test {Write-Output 'I am New-Test function'}
function helper {Write-Output 'I am helper function'}

Export variable Interval 0
$Interval = 2
```

<span data-ttu-id="e7969-139">Dieses Beispiel enthält eine Funktion namens " **Export** ", die eine Funktion deklariert oder eine Variable erstellt und dann einen `Export-ModuleMember` Befehl für die Funktion oder Variable schreibt.</span><span class="sxs-lookup"><span data-stu-id="e7969-139">This example includes a function named **Export** that declares a function or creates a variable, and then writes an `Export-ModuleMember` command for the function or variable.</span></span>
<span data-ttu-id="e7969-140">Auf diese Weise können Sie eine Funktion oder Variable in einem einzigen Befehl deklarieren und exportieren.</span><span class="sxs-lookup"><span data-stu-id="e7969-140">This lets you declare and export a function or variable in a single command.</span></span>

<span data-ttu-id="e7969-141">Wenn Sie die **Export** -Funktion verwenden möchten, fügen Sie Sie in das Skript Modul ein.</span><span class="sxs-lookup"><span data-stu-id="e7969-141">To use the **Export** function, include it in your script module.</span></span>
<span data-ttu-id="e7969-142">Um eine Funktion zu exportieren, geben Sie `Export` vor dem **Function** -Schlüsselwort ein.</span><span class="sxs-lookup"><span data-stu-id="e7969-142">To export a function, type `Export` before the **Function** keyword.</span></span>

<span data-ttu-id="e7969-143">Um eine Variable zu exportieren, verwenden Sie folgendes Format, um die Variable zu deklarieren und ihren Wert festzulegen:</span><span class="sxs-lookup"><span data-stu-id="e7969-143">To export a variable, use the following format to declare the variable and set its value:</span></span>

`Export variable <variable-name> <value>`

<span data-ttu-id="e7969-144">Die Befehle im Beispiel zeigen das richtige Format.</span><span class="sxs-lookup"><span data-stu-id="e7969-144">The commands in the example show the correct format.</span></span>
<span data-ttu-id="e7969-145">In diesem Beispiel werden nur die **New-Test-** Funktion und die $Interval-Variable exportiert.</span><span class="sxs-lookup"><span data-stu-id="e7969-145">In this example, only the **New-Test** function and the $Interval variable are exported.</span></span>

## <span data-ttu-id="e7969-146">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e7969-146">PARAMETERS</span></span>

### <span data-ttu-id="e7969-147">-Alias</span><span class="sxs-lookup"><span data-stu-id="e7969-147">-Alias</span></span>

<span data-ttu-id="e7969-148">Gibt die Aliase an, die aus der Skriptmoduldatei exportiert werden.</span><span class="sxs-lookup"><span data-stu-id="e7969-148">Specifies the aliases that are exported from the script module file.</span></span>
<span data-ttu-id="e7969-149">Geben Sie die Aliasnamen ein.</span><span class="sxs-lookup"><span data-stu-id="e7969-149">Enter the alias names.</span></span>
<span data-ttu-id="e7969-150">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="e7969-150">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="e7969-151">-Cmdlet</span><span class="sxs-lookup"><span data-stu-id="e7969-151">-Cmdlet</span></span>

<span data-ttu-id="e7969-152">Gibt die Cmdlets an, die aus der Skriptmoduldatei exportiert werden.</span><span class="sxs-lookup"><span data-stu-id="e7969-152">Specifies the cmdlets that are exported from the script module file.</span></span>
<span data-ttu-id="e7969-153">Geben Sie die Cmdlet-Namen ein.</span><span class="sxs-lookup"><span data-stu-id="e7969-153">Enter the cmdlet names.</span></span>
<span data-ttu-id="e7969-154">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="e7969-154">Wildcard characters are permitted.</span></span>

<span data-ttu-id="e7969-155">Sie können keine Cmdlets in einer Skriptmoduldatei erstellen, aber Sie können Cmdlets aus einem binären Modul in ein Skriptmodul importieren und dann erneut aus dem Skriptmodul exportieren.</span><span class="sxs-lookup"><span data-stu-id="e7969-155">You cannot create cmdlets in a script module file, but you can import cmdlets from a binary module into a script module and re-export them from the script module.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="e7969-156">-Funktion</span><span class="sxs-lookup"><span data-stu-id="e7969-156">-Function</span></span>

<span data-ttu-id="e7969-157">Gibt die Funktionen an, die aus der Skriptmoduldatei exportiert werden.</span><span class="sxs-lookup"><span data-stu-id="e7969-157">Specifies the functions that are exported from the script module file.</span></span>
<span data-ttu-id="e7969-158">Geben Sie die Funktionsnamen ein.</span><span class="sxs-lookup"><span data-stu-id="e7969-158">Enter the function names.</span></span>
<span data-ttu-id="e7969-159">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="e7969-159">Wildcard characters are permitted.</span></span>
<span data-ttu-id="e7969-160">Sie können auch Funktionsnamen-Zeichen folgen an **Export-modulemember** übergeben.</span><span class="sxs-lookup"><span data-stu-id="e7969-160">You can also pipe function name strings to **Export-ModuleMember** .</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="e7969-161">-Variable</span><span class="sxs-lookup"><span data-stu-id="e7969-161">-Variable</span></span>

<span data-ttu-id="e7969-162">Gibt die Variablen an, die aus der Skriptmoduldatei exportiert werden.</span><span class="sxs-lookup"><span data-stu-id="e7969-162">Specifies the variables that are exported from the script module file.</span></span>
<span data-ttu-id="e7969-163">Geben Sie die Variablennamen ohne Dollarzeichen ein.</span><span class="sxs-lookup"><span data-stu-id="e7969-163">Enter the variable names, without a dollar sign.</span></span>
<span data-ttu-id="e7969-164">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="e7969-164">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="e7969-165">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="e7969-165">CommonParameters</span></span>

<span data-ttu-id="e7969-166">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="e7969-166">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e7969-167">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="e7969-167">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e7969-168">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="e7969-168">INPUTS</span></span>

### <span data-ttu-id="e7969-169">System.String</span><span class="sxs-lookup"><span data-stu-id="e7969-169">System.String</span></span>

<span data-ttu-id="e7969-170">Sie können Funktionsnamen-Zeichen folgen an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="e7969-170">You can pipe function name strings to this cmdlet.</span></span>

## <span data-ttu-id="e7969-171">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="e7969-171">OUTPUTS</span></span>

### <span data-ttu-id="e7969-172">Keine</span><span class="sxs-lookup"><span data-stu-id="e7969-172">None</span></span>

<span data-ttu-id="e7969-173">Dieses Cmdlet generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="e7969-173">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="e7969-174">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="e7969-174">NOTES</span></span>

* <span data-ttu-id="e7969-175">Um ein Element aus der Liste der exportierten Elemente auszuschließen, fügen Sie einen **Export-modulemember** -Befehl hinzu, der alle anderen Member auflistet, aber das Element auslässt, das Sie ausschließen möchten.</span><span class="sxs-lookup"><span data-stu-id="e7969-175">To exclude a member from the list of exported members, add an **Export-ModuleMember** command that lists all other members but omits the member that you want to exclude.</span></span>

## <span data-ttu-id="e7969-176">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="e7969-176">RELATED LINKS</span></span>

[<span data-ttu-id="e7969-177">Get-Module</span><span class="sxs-lookup"><span data-stu-id="e7969-177">Get-Module</span></span>](Get-Module.md)

[<span data-ttu-id="e7969-178">Import-Module</span><span class="sxs-lookup"><span data-stu-id="e7969-178">Import-Module</span></span>](Import-Module.md)

[<span data-ttu-id="e7969-179">Remove-Module</span><span class="sxs-lookup"><span data-stu-id="e7969-179">Remove-Module</span></span>](Remove-Module.md)