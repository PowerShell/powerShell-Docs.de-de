---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/unblock-file?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Unblock-File
ms.openlocfilehash: 617d36f61434d8b779d1161610cc7757c6a7725d
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93216199"
---
# <span data-ttu-id="56b24-103">Unblock-File</span><span class="sxs-lookup"><span data-stu-id="56b24-103">Unblock-File</span></span>

## <span data-ttu-id="56b24-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="56b24-104">SYNOPSIS</span></span>
<span data-ttu-id="56b24-105">Hebt die Blockierung von Dateien auf, die aus dem Internet heruntergeladen wurden.</span><span class="sxs-lookup"><span data-stu-id="56b24-105">Unblocks files that were downloaded from the Internet.</span></span>

## <span data-ttu-id="56b24-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="56b24-106">SYNTAX</span></span>

### <span data-ttu-id="56b24-107">Bypath (Standard)</span><span class="sxs-lookup"><span data-stu-id="56b24-107">ByPath (Default)</span></span>

```
Unblock-File [-Path] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="56b24-108">Byliteralpath</span><span class="sxs-lookup"><span data-stu-id="56b24-108">ByLiteralPath</span></span>

```
Unblock-File -LiteralPath <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="56b24-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="56b24-109">DESCRIPTION</span></span>

<span data-ttu-id="56b24-110">Mit dem Cmdlet **Unblock-File** können Sie Dateien öffnen, die aus dem Internet heruntergeladen wurden.</span><span class="sxs-lookup"><span data-stu-id="56b24-110">The **Unblock-File** cmdlet lets you open files that were downloaded from the Internet.</span></span>
<span data-ttu-id="56b24-111">Die Blockierung von PowerShell-Skriptdateien, die aus dem Internet heruntergeladen wurden, wird aufgehoben, sodass Sie Sie ausführen können, auch wenn die PowerShell-Ausführungs Richtlinie **RemoteSigned** ist.</span><span class="sxs-lookup"><span data-stu-id="56b24-111">It unblocks PowerShell script files that were downloaded from the Internet so you can run them, even when the PowerShell execution policy is **RemoteSigned** .</span></span>
<span data-ttu-id="56b24-112">Standardmäßig werden diese Dateien blockiert, um den Computer vor nicht vertrauenswürdigen Dateien zu schützen.</span><span class="sxs-lookup"><span data-stu-id="56b24-112">By default, these files are blocked to protect the computer from untrusted files.</span></span>

<span data-ttu-id="56b24-113">Überprüfen Sie vor der Verwendung des **Unblock-File** -Cmdlets die Datei und die Quelle und stellen Sie sicher, dass sie sicher geöffnet werden kann.</span><span class="sxs-lookup"><span data-stu-id="56b24-113">Before using the **Unblock-File** cmdlet, review the file and its source and verify that it is safe to open.</span></span>

<span data-ttu-id="56b24-114">Intern wird das **Unblock-File** -Cmdlet aus dem alternativen Datenstrom „Zone.Identifier“ entfernt, der den Wert „3“ hat, um anzugeben, dass er aus dem Internet heruntergeladen wurde.</span><span class="sxs-lookup"><span data-stu-id="56b24-114">Internally, the **Unblock-File** cmdlet removes the Zone.Identifier alternate data stream, which has a value of "3" to indicate that it was downloaded from the Internet.</span></span>

<span data-ttu-id="56b24-115">Weitere Informationen zu PowerShell-Ausführungsrichtlinien finden Sie unter [about_Execution_Policies](../Microsoft.PowerShell.Core/about/about_Execution_Policies.md).</span><span class="sxs-lookup"><span data-stu-id="56b24-115">For more information about PowerShell execution policies, see [about_Execution_Policies](../Microsoft.PowerShell.Core/about/about_Execution_Policies.md).</span></span>

<span data-ttu-id="56b24-116">Dieses Cmdlet wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="56b24-116">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="56b24-117">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="56b24-117">EXAMPLES</span></span>

### <span data-ttu-id="56b24-118">Beispiel 1: Entsperren einer Datei</span><span class="sxs-lookup"><span data-stu-id="56b24-118">Example 1: Unblock a file</span></span>

```
PS C:\> Unblock-File -Path C:\Users\User01\Documents\Downloads\PowerShellTips.chm
```

<span data-ttu-id="56b24-119">Dieser Befehl hebt die Blockierung der Datei „PowerShellTips.chm“ auf.</span><span class="sxs-lookup"><span data-stu-id="56b24-119">This command unblocks the PowerShellTips.chm file.</span></span>

### <span data-ttu-id="56b24-120">Beispiel 2: entsperren mehrerer Dateien</span><span class="sxs-lookup"><span data-stu-id="56b24-120">Example 2: Unblock multiple files</span></span>

```
PS C:\> dir C:\Downloads\*PowerShell* | Unblock-File
```

<span data-ttu-id="56b24-121">Dieser Befehl hebt die Blockierung aller Dateien im Verzeichnis „C:\Downloads“ auf, deren Namen die Zeichenfolge „PowerShell“ enthalten.</span><span class="sxs-lookup"><span data-stu-id="56b24-121">This command unblocks all of the files in the C:\Downloads directory whose names include "PowerShell".</span></span>
<span data-ttu-id="56b24-122">Führen Sie keinen Befehl wie diesen aus, bis Sie sichergestellt haben, dass alle Dateien sicher sind.</span><span class="sxs-lookup"><span data-stu-id="56b24-122">Do not run a command like this one until you have verified that all files are safe.</span></span>

### <span data-ttu-id="56b24-123">Beispiel 3: Suchen und Entsperren von Skripts</span><span class="sxs-lookup"><span data-stu-id="56b24-123">Example 3: Find and unblock scripts</span></span>

```
The first command uses the *Stream* parameter of the Get-Item cmdlet get files with the Zone.Identifier stream.Although you could pipe the output directly to the **Unblock-File** cmdlet (Get-Item * -Stream "Zone.Identifier" -ErrorAction SilentlyContinue | ForEach {Unblock-File $_.FileName}), it is prudent to review the file and confirm that it is safe before unblocking.
PS C:\> Get-Item * -Stream "Zone.Identifier" -ErrorAction SilentlyContinue
   FileName: C:\ps-test\Start-ActivityTracker.ps1

Stream                   Length
------                   ------
Zone.Identifier              26

The second command shows what happens when you run a blocked script in a PowerShell session in which the execution policy is **RemoteSigned**. The RemoteSigned policy prevents you from running scripts that are downloaded from the Internet unless they are digitally signed.
PS C:\> C:\ps-test\Start-ActivityTracker.ps1
c:\ps-test\Start-ActivityTracker.ps1 : File c:\ps-test\Start-ActivityTracker.ps1 cannot
be loaded. The file c:\ps-test\Start-ActivityTracker.ps1 is not digitally signed. The script
will not execute on the system. For more information, see about_Execution_Policies.

At line:1 char:1
+ c:\ps-test\Start-ActivityTracker.ps1
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : SecurityError: (:) [], PSSecurityException
    + FullyQualifiedErrorId : UnauthorizedAccess

The third command uses the **Unblock-File** cmdlet to unblock the script so it can run in the session.
PS C:\> Get-Item C:\ps-test\Start-ActivityTracker.ps1 | Unblock-File
```

<span data-ttu-id="56b24-124">Dieser Befehl zeigt, wie Sie PowerShell-Skripts suchen und deren Blockierung entsperren.</span><span class="sxs-lookup"><span data-stu-id="56b24-124">This command shows how to find and unblock PowerShell scripts.</span></span>

## <span data-ttu-id="56b24-125">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="56b24-125">PARAMETERS</span></span>

### <span data-ttu-id="56b24-126">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="56b24-126">-LiteralPath</span></span>
<span data-ttu-id="56b24-127">Gibt die Dateien an, deren Blockierung aufgehoben werden soll.</span><span class="sxs-lookup"><span data-stu-id="56b24-127">Specifies the files to unblock.</span></span>
<span data-ttu-id="56b24-128">Im Gegensatz zu *Path* wird der Wert des *LiteralPath* -Parameters genauso verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="56b24-128">Unlike *Path* , the value of the *LiteralPath* parameter is used exactly as it is typed.</span></span>
<span data-ttu-id="56b24-129">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="56b24-129">No characters are interpreted as wildcards.</span></span>
<span data-ttu-id="56b24-130">Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="56b24-130">If the path includes escape characters, enclose it in single quotation marks.</span></span>
<span data-ttu-id="56b24-131">Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="56b24-131">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ByLiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="56b24-132">-Path</span><span class="sxs-lookup"><span data-stu-id="56b24-132">-Path</span></span>
<span data-ttu-id="56b24-133">Gibt die Dateien an, deren Blockierung aufgehoben werden soll.</span><span class="sxs-lookup"><span data-stu-id="56b24-133">Specifies the files to unblock.</span></span>
<span data-ttu-id="56b24-134">Platzhalterzeichen werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="56b24-134">Wildcard characters are supported.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ByPath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="56b24-135">-Confirm</span><span class="sxs-lookup"><span data-stu-id="56b24-135">-Confirm</span></span>

<span data-ttu-id="56b24-136">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="56b24-136">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="56b24-137">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="56b24-137">-WhatIf</span></span>

<span data-ttu-id="56b24-138">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="56b24-138">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="56b24-139">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="56b24-139">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="56b24-140">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="56b24-140">CommonParameters</span></span>

<span data-ttu-id="56b24-141">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="56b24-141">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="56b24-142">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="56b24-142">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="56b24-143">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="56b24-143">INPUTS</span></span>

### <span data-ttu-id="56b24-144">System.String</span><span class="sxs-lookup"><span data-stu-id="56b24-144">System.String</span></span>

<span data-ttu-id="56b24-145">Sie können einen Dateipfad über die Pipeline an **Unblock-File** übergeben.</span><span class="sxs-lookup"><span data-stu-id="56b24-145">You can pipe a file path to **Unblock-File** .</span></span>

## <span data-ttu-id="56b24-146">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="56b24-146">OUTPUTS</span></span>

### <span data-ttu-id="56b24-147">Keine</span><span class="sxs-lookup"><span data-stu-id="56b24-147">None</span></span>

<span data-ttu-id="56b24-148">Dieses Cmdlet generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="56b24-148">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="56b24-149">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="56b24-149">NOTES</span></span>

* <span data-ttu-id="56b24-150">Das Cmdlet **Unblock-File** funktioniert nur in Dateisystemlaufwerken.</span><span class="sxs-lookup"><span data-stu-id="56b24-150">The **Unblock-File** cmdlet works only in file system drives.</span></span>
* <span data-ttu-id="56b24-151">**Unblock-File** führt den gleichen Vorgang wie die **Schaltfläche "entsperren"** im Dialogfeld " **Eigenschaften** " im Datei-Explorer aus.</span><span class="sxs-lookup"><span data-stu-id="56b24-151">**Unblock-File** performs the same operation as the **Unblock** button on the **Properties** dialog box in File Explorer.</span></span>
* <span data-ttu-id="56b24-152">Bei Verwendung des **Unblock-File** -Cmdlets für eine nicht blockierte Datei hat der Befehl keine Auswirkungen auf die Datei, deren Blockierung aufgehoben wurde, und das Cmdlet generiert keine Fehler.</span><span class="sxs-lookup"><span data-stu-id="56b24-152">If you use the **Unblock-File** cmdlet on a file that is not blocked, the command has no effect on the unblocked file and the cmdlet does not generate errors.</span></span>

## <span data-ttu-id="56b24-153">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="56b24-153">RELATED LINKS</span></span>

[<span data-ttu-id="56b24-154">about_Execution_Policies</span><span class="sxs-lookup"><span data-stu-id="56b24-154">about_Execution_Policies</span></span>](../Microsoft.PowerShell.Core/About/about_Execution_Policies.md)

[<span data-ttu-id="56b24-155">Get-Item</span><span class="sxs-lookup"><span data-stu-id="56b24-155">Get-Item</span></span>](../Microsoft.PowerShell.Management/Get-Item.md)

[<span data-ttu-id="56b24-156">Out-File</span><span class="sxs-lookup"><span data-stu-id="56b24-156">Out-File</span></span>](Out-File.md)

[<span data-ttu-id="56b24-157">FileSystem-Anbieter</span><span class="sxs-lookup"><span data-stu-id="56b24-157">FileSystem Provider</span></span>](../Microsoft.PowerShell.Core/about/about_FileSystem_Provider.md)