---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/21/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertfrom-stringdata?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertFrom-StringData
ms.openlocfilehash: f4b58605059d85cd2a215969c13f9cc2e5262465
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214140"
---
# <span data-ttu-id="1ab50-103">ConvertFrom-StringData</span><span class="sxs-lookup"><span data-stu-id="1ab50-103">ConvertFrom-StringData</span></span>

## <span data-ttu-id="1ab50-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="1ab50-104">SYNOPSIS</span></span>
<span data-ttu-id="1ab50-105">Konvertiert eine Zeichenfolge, die mindestens ein Schlüssel-Wert-Paar enthält, in eine Hashtabelle.</span><span class="sxs-lookup"><span data-stu-id="1ab50-105">Converts a string containing one or more key and value pairs to a hash table.</span></span>

## <span data-ttu-id="1ab50-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="1ab50-106">SYNTAX</span></span>

```
ConvertFrom-StringData [-StringData] <String> [<CommonParameters>]
```

## <span data-ttu-id="1ab50-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1ab50-107">DESCRIPTION</span></span>

<span data-ttu-id="1ab50-108">Mit dem- `ConvertFrom-StringData` Cmdlet wird eine Zeichenfolge, die ein oder mehrere Schlüssel-Wert-Paare enthält, in eine Hash Tabelle konvertiert.</span><span class="sxs-lookup"><span data-stu-id="1ab50-108">The `ConvertFrom-StringData` cmdlet converts a string that contains one or more key and value pairs into a hash table.</span></span> <span data-ttu-id="1ab50-109">Da sich jedes Schlüssel-Wert-Paar in einer separaten Zeile befinden muss, werden diese Zeichen folgen häufig als Eingabeformat verwendet.</span><span class="sxs-lookup"><span data-stu-id="1ab50-109">Because each key-value pair must be on a separate line, here-strings are often used as the input format.</span></span> <span data-ttu-id="1ab50-110">Standardmäßig muss der **Schlüssel** von dem **Wert** durch ein Gleichheitszeichen () getrennt werden `=` .</span><span class="sxs-lookup"><span data-stu-id="1ab50-110">By default, the **key** must be separated from the **value** by an equals sign (`=`) character.</span></span>

<span data-ttu-id="1ab50-111">Das- `ConvertFrom-StringData` Cmdlet gilt als sicheres Cmdlet, das im- `DATA` Abschnitt eines Skripts oder einer Funktion verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="1ab50-111">The `ConvertFrom-StringData` cmdlet is considered to be a safe cmdlet that can be used in the `DATA` section of a script or function.</span></span> <span data-ttu-id="1ab50-112">Bei Verwendung in einem `DATA` Abschnitt muss der Inhalt der Zeichenfolge den Regeln für einen Daten Abschnitt entsprechen.</span><span class="sxs-lookup"><span data-stu-id="1ab50-112">When used in a `DATA` section, the contents of the string must conform to the rules for a DATA section.</span></span> <span data-ttu-id="1ab50-113">Weitere Informationen finden Sie unter [about_Data_Sections](../Microsoft.PowerShell.Core/About/about_Data_Sections.md).</span><span class="sxs-lookup"><span data-stu-id="1ab50-113">For more information, see [about_Data_Sections](../Microsoft.PowerShell.Core/About/about_Data_Sections.md).</span></span>

<span data-ttu-id="1ab50-114">`ConvertFrom-StringData` unterstützt Escapezeichenfolgen, die von herkömmlichen maschinellen Übersetzungstools zugelassen werden.</span><span class="sxs-lookup"><span data-stu-id="1ab50-114">`ConvertFrom-StringData` supports escape character sequences that are allowed by conventional machine translation tools.</span></span> <span data-ttu-id="1ab50-115">Das heißt, das Cmdlet kann umgekehrte Schrägstriche ( `\` ) als Escapezeichen in den Zeichen folgen Daten mit der [Regex. unescape-Methode und nicht](/dotnet/api/system.text.regularexpressions.regex.unescape)mit dem PowerShell-Graviszeichen-Zeichen () interpretieren, \` das normalerweise das Ende einer Zeile in einem Skript signalisiert.</span><span class="sxs-lookup"><span data-stu-id="1ab50-115">That is, the cmdlet can interpret backslashes (`\`) as escape characters in the string data by using the [Regex.Unescape Method](/dotnet/api/system.text.regularexpressions.regex.unescape), instead of the PowerShell backtick character (\`) that would normally signal the end of a line in a script.</span></span> <span data-ttu-id="1ab50-116">In der here-Zeichenfolge funktioniert das Hochkommazeichen nicht.</span><span class="sxs-lookup"><span data-stu-id="1ab50-116">Inside the here-string, the backtick character does not work.</span></span> <span data-ttu-id="1ab50-117">Sie können auch einen literalen umgekehrten Schrägstrich in den Ergebnissen beibehalten, indem Sie ihn mit einem vorangehenden umgekehrten Schrägstrich versehen, wie folgt: `\\` .</span><span class="sxs-lookup"><span data-stu-id="1ab50-117">You can also preserve a literal backslash in your results by escaping it with a preceding backslash, like this: `\\`.</span></span> <span data-ttu-id="1ab50-118">Umgekehrte Schrägstriche ohne Escapezeichen, wie z. B. solche, die häufig in Dateipfaden verwendet werden, können in den Ergebnissen als unzulässige Escapesequenzen gerendert werden.</span><span class="sxs-lookup"><span data-stu-id="1ab50-118">Unescaped backslash characters, such as those that are commonly used in file paths, can render as illegal escape sequences in your results.</span></span>

## <span data-ttu-id="1ab50-119">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="1ab50-119">EXAMPLES</span></span>

### <span data-ttu-id="1ab50-120">Beispiel 1: Konvertieren einer here-Zeichenfolge in einfachen Anführungszeichen in eine Hash Tabelle</span><span class="sxs-lookup"><span data-stu-id="1ab50-120">Example 1: Convert a single-quoted here-string to a hash table</span></span>

<span data-ttu-id="1ab50-121">In diesem Beispiel wird eine here-Zeichenfolge von Benutzer Nachrichten in einfache Anführungszeichen in eine Hash Tabelle konvertiert.</span><span class="sxs-lookup"><span data-stu-id="1ab50-121">This example converts a single-quoted here-string of user messages into a hash table.</span></span> <span data-ttu-id="1ab50-122">In einer Zeichenfolge in einfachen Anführungszeichen werden Werte nicht durch Variablen ersetzt und Ausdrücke nicht ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="1ab50-122">In a single-quoted string, values are not substituted for variables and expressions are not evaluated.</span></span>
<span data-ttu-id="1ab50-123">Mit dem- `ConvertFrom-StringData` Cmdlet wird der Wert in der- `$Here` Variablen in eine Hash Tabelle konvertiert.</span><span class="sxs-lookup"><span data-stu-id="1ab50-123">The `ConvertFrom-StringData` cmdlet converts the value in the `$Here` variable to a hash table.</span></span>

```powershell
$Here = @'
Msg1 = The string parameter is required.
Msg2 = Credentials are required for this command.
Msg3 = The specified variable does not exist.
'@
ConvertFrom-StringData -StringData $Here
```

```Output
Name                           Value
----                           -----
Msg3                           The specified variable does not exist.
Msg2                           Credentials are required for this command.
Msg1                           The string parameter is required.
```

### <span data-ttu-id="1ab50-124">Beispiel 2: Konvertieren einer here-Zeichenfolge mit einem Kommentar</span><span class="sxs-lookup"><span data-stu-id="1ab50-124">Example 2: Convert a here-string containing a comment</span></span>

<span data-ttu-id="1ab50-125">In diesem Beispiel wird eine here-Zeichenfolge, die einen Kommentar und mehrere Schlüssel-Wert-Paare enthält, in eine Hash Tabelle konvertiert.</span><span class="sxs-lookup"><span data-stu-id="1ab50-125">This example converts a here-string that contains a comment and multiple key-value pairs into a hash table.</span></span>

```powershell
ConvertFrom-StringData -StringData @'
Name = Disks.ps1

# Category is optional.

Category = Storage
Cost = Free
'@
```

```Output
Name                           Value
----                           -----
Cost                           Free
Category                       Storage
Name                           Disks.ps1
```

<span data-ttu-id="1ab50-126">Der Wert des **StringData** -Parameters ist eine here-Zeichenfolge anstelle einer Variablen, die eine here-Zeichenfolge enthält.</span><span class="sxs-lookup"><span data-stu-id="1ab50-126">The value of the **StringData** parameter is a here-string, instead of a variable that contains a here-string.</span></span> <span data-ttu-id="1ab50-127">Beide Formate sind gültig.</span><span class="sxs-lookup"><span data-stu-id="1ab50-127">Either format is valid.</span></span> <span data-ttu-id="1ab50-128">Die here-Zeichenfolge enthält einen Kommentar zu einer der Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="1ab50-128">The here-string includes a comment about one of the strings.</span></span>
<span data-ttu-id="1ab50-129">`ConvertFrom-StringData` ignoriert einzeilige Kommentare, aber das `#` Zeichen muss das erste Zeichen in der Zeile sein, das kein Leerzeichen ist.</span><span class="sxs-lookup"><span data-stu-id="1ab50-129">`ConvertFrom-StringData` ignores single-line comments, but the `#` character must be the first non-whitespace character on the line.</span></span> <span data-ttu-id="1ab50-130">Alle Zeichen in der Zeile nach dem `#` werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="1ab50-130">All characters on the line after the `#` are ignored.</span></span>

### <span data-ttu-id="1ab50-131">Beispiel 3: Konvertieren einer Zeichenfolge in eine Hash Tabelle</span><span class="sxs-lookup"><span data-stu-id="1ab50-131">Example 3: Convert a string to a hash table</span></span>

<span data-ttu-id="1ab50-132">In diesem Beispiel wird eine reguläre Zeichenfolge in doppelten Anführungszeichen (keine here-Zeichenfolge) in eine Hash Tabelle konvertiert und in der `$A` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="1ab50-132">This example converts a regular double-quoted string (not a here-string) into a hash table and saves it in the `$A` variable.</span></span>

```powershell
$A = ConvertFrom-StringData -StringData "Top = Red `n Bottom = Blue"
$A
```

```Output
Name             Value
----             -----
Bottom           Blue
Top              Red
```

<span data-ttu-id="1ab50-133">Um die Bedingung zu erfüllen, dass sich jedes Schlüssel-Wert-Paar in einer separaten Zeile befinden muss, verwendet die Zeichenfolge das PowerShell-Zeilen vorformat ( \` n), um die Paare voneinander zu trennen.</span><span class="sxs-lookup"><span data-stu-id="1ab50-133">To satisfy the condition that each key-value pair must be on a separate line, the string uses the PowerShell newline character (\`n) to separate the pairs.</span></span>

### <span data-ttu-id="1ab50-134">Beispiel 4: Verwenden von ConvertFrom-StringData im Daten Abschnitt eines Skripts</span><span class="sxs-lookup"><span data-stu-id="1ab50-134">Example 4: Use ConvertFrom-StringData in the DATA section of a script</span></span>

<span data-ttu-id="1ab50-135">Dieses Beispiel zeigt einen `ConvertFrom-StringData` Befehl, der im Daten Abschnitt eines Skripts verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="1ab50-135">This example shows a `ConvertFrom-StringData` command used in the DATA section of a script.</span></span>
<span data-ttu-id="1ab50-136">Die Anweisungen unter dem DATA-Abschnitt zeigen den Text für den Benutzer an.</span><span class="sxs-lookup"><span data-stu-id="1ab50-136">The statements below the DATA section display the text to the user.</span></span>

```powershell
$TextMsgs = DATA {
ConvertFrom-StringData @'
Text001 = The $Notebook variable contains the name of the user's system notebook.
Text002 = The $MyNotebook variable contains the name of the user's private notebook.
'@
}
$TextMsgs
```

```Output
Name             Value
----             -----
Text001          The $Notebook variable contains the name of the user's system notebook.
Text002          The $MyNotebook variable contains the name of the user's private notebook.
```

<span data-ttu-id="1ab50-137">Da der Text Variablennamen enthält, muss er in einer Zeichenfolge in einfachen Anführungszeichen eingeschlossen werden, damit die Variablen wörtlich interpretiert und nicht erweitert werden.</span><span class="sxs-lookup"><span data-stu-id="1ab50-137">Because the text includes variable names, it must be enclosed in a single-quoted string so that the variables are interpreted literally and not expanded.</span></span> <span data-ttu-id="1ab50-138">Variablen sind im **Data** -Abschnitt nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="1ab50-138">Variables are not permitted in the **DATA** section.</span></span>

### <span data-ttu-id="1ab50-139">Beispiel 5: Verwenden des Pipeline-Operators zum Übergeben einer Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1ab50-139">Example 5: Use the pipeline operator to pass a string</span></span>

<span data-ttu-id="1ab50-140">Dieses Beispiel zeigt, dass Sie einen Pipeline Operator () verwenden können, um `|` eine Zeichenfolge an zu senden `ConvertFrom-StringData` .</span><span class="sxs-lookup"><span data-stu-id="1ab50-140">This example shows that you can use a pipeline operator (`|`) to send a string to `ConvertFrom-StringData`.</span></span> <span data-ttu-id="1ab50-141">Der Wert der `$Here` Variablen wird an weitergeleitet `ConvertFrom-StringData` und das Ergebnis in der `$Hash` Variablen.</span><span class="sxs-lookup"><span data-stu-id="1ab50-141">The the value of the `$Here` variable is piped to `ConvertFrom-StringData` and the result in the `$Hash` variable.</span></span>

```powershell
$Here = @'
Msg1 = The string parameter is required.
Msg2 = Credentials are required for this command.
Msg3 = The specified variable does not exist.
'@
$Hash = $Here | ConvertFrom-StringData
$Hash
```

```Output
Name     Value
----     -----
Msg3     The specified variable does not exist.
Msg2     Credentials are required for this command.
Msg1     The string parameter is required.
```

### <span data-ttu-id="1ab50-142">Beispiel 6: Verwenden von Escapezeichen zum Hinzufügen neuer Zeilen und Zurückgeben von Zeichen</span><span class="sxs-lookup"><span data-stu-id="1ab50-142">Example 6: Use escape characters to add new lines and return characters</span></span>

<span data-ttu-id="1ab50-143">Dieses Beispiel zeigt die Verwendung von Escapezeichen zum Erstellen neuer Zeilen und zum Zurückgeben von Zeichen in den Quelldaten.</span><span class="sxs-lookup"><span data-stu-id="1ab50-143">This example shows the use of escape characters to create new lines and return characters in source data.</span></span> <span data-ttu-id="1ab50-144">Die Escapesequenz `\n` wird verwendet, um neue Zeilen in einem TextBlock zu erstellen, der mit einem Namen oder einem Element in der resultierenden Hash Tabelle verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="1ab50-144">The escape sequence `\n` is used to create new lines within a block of text that is associated with a name or item in the resulting hash table.</span></span>

```powershell
ConvertFrom-StringData @"
Vincentio = Heaven doth with us as we with torches do,\nNot light them for themselves; for if our virtues\nDid not go forth of us, 'twere all alike\nAs if we had them not.
Angelo = Let there be some more test made of my metal,\nBefore so noble and so great a figure\nBe stamp'd upon it.
"@ | Format-List
```

```Output
Name  : Angelo
Value : Let there be some more test made of my metal,
        Before so noble and so great a figure
        Be stamp'd upon it.

Name  : Vincentio
Value : Heaven doth with us as we with torches do,
        Not light them for themselves; for if our virtues
        Did not go forth of us, 'twere all alike
        As if we had them not.
```

### <span data-ttu-id="1ab50-145">Beispiel 7: Verwenden eines umgekehrten Schrägstrichs zum ordnungsgemäßen Rendering eines Dateipfads</span><span class="sxs-lookup"><span data-stu-id="1ab50-145">Example 7: Use backslash escape character to correctly render a file path</span></span>

<span data-ttu-id="1ab50-146">In diesem Beispiel wird gezeigt, wie der umgekehrte Schrägstrich-Escapezeichen in den Zeichen folgen Daten verwendet wird, damit ein Dateipfad in der resultierenden Hash Tabelle ordnungsgemäß dargestellt werden kann `ConvertFrom-StringData` .</span><span class="sxs-lookup"><span data-stu-id="1ab50-146">This example shows how to use of the backslash escape character in the string data to allow a file path to render correctly in the resulting `ConvertFrom-StringData` hash table.</span></span> <span data-ttu-id="1ab50-147">Der doppelte umgekehrte Schrägstrich stellt sicher, dass der umgekehrte Literalschrägstrich in der Ausgabe der Hashtabelle ordnungsgemäß gerendert wird.</span><span class="sxs-lookup"><span data-stu-id="1ab50-147">The double backslash ensures that the literal backslash characters render correctly in the hash table output.</span></span>

```powershell
ConvertFrom-StringData "Message=Look in c:\\Windows\\System32"
```

```Output
Name                           Value
----                           -----
Message                        Look in c:\Windows\System32
```

## <span data-ttu-id="1ab50-148">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="1ab50-148">PARAMETERS</span></span>

### <span data-ttu-id="1ab50-149">-StringData</span><span class="sxs-lookup"><span data-stu-id="1ab50-149">-StringData</span></span>

<span data-ttu-id="1ab50-150">Gibt die zu konvertierende Zeichenfolge an.</span><span class="sxs-lookup"><span data-stu-id="1ab50-150">Specifies the string to be converted.</span></span> <span data-ttu-id="1ab50-151">Sie können diesen Parameter verwenden oder eine Zeichenfolge an die Pipeline übergeben `ConvertFrom-StringData` .</span><span class="sxs-lookup"><span data-stu-id="1ab50-151">You can use this parameter or pipe a string to `ConvertFrom-StringData`.</span></span> <span data-ttu-id="1ab50-152">Der Parametername ist optional.</span><span class="sxs-lookup"><span data-stu-id="1ab50-152">The parameter name is optional.</span></span>

<span data-ttu-id="1ab50-153">Der Wert dieses Parameters muss eine Zeichenfolge sein, die mindestens ein Schlüssel-Wert-Paar enthält.</span><span class="sxs-lookup"><span data-stu-id="1ab50-153">The value of this parameter must be a string that contains one or more key-value pairs.</span></span> <span data-ttu-id="1ab50-154">Jedes Schlüssel-Wert-Paar muss sich in einer separaten Zeile befinden, oder jedes Paar muss durch Zeilen vorzeichenzeichen ( \` n) getrennt werden.</span><span class="sxs-lookup"><span data-stu-id="1ab50-154">Each key-value pair must be on a separate line, or each pair must be separated by newline characters (\`n).</span></span>

<span data-ttu-id="1ab50-155">Sie können Kommentare in die Zeichenfolge einschließen, aber die Kommentare dürfen sich nicht in derselben Zeile wie ein Schlüssel-Wert-Paar befinden.</span><span class="sxs-lookup"><span data-stu-id="1ab50-155">You can include comments in the string, but the comments cannot be on the same line as a key-value pair.</span></span> <span data-ttu-id="1ab50-156">`ConvertFrom-StringData` ignoriert einzeilige Kommentare.</span><span class="sxs-lookup"><span data-stu-id="1ab50-156">`ConvertFrom-StringData` ignores single-line comments.</span></span> <span data-ttu-id="1ab50-157">Das `#` Zeichen muss das erste Zeichen in der Zeile sein, das kein Leerzeichen ist.</span><span class="sxs-lookup"><span data-stu-id="1ab50-157">The `#` character must be the first non-whitespace character on the line.</span></span> <span data-ttu-id="1ab50-158">Alle Zeichen in der Zeile nach dem `#` werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="1ab50-158">All characters on the line after the `#` are ignored.</span></span> <span data-ttu-id="1ab50-159">Die Kommentare sind nicht in der Hashtabelle enthalten.</span><span class="sxs-lookup"><span data-stu-id="1ab50-159">The comments are not included in the hash table.</span></span>

<span data-ttu-id="1ab50-160">Eine here-Zeichenfolge ist eine Zeichenfolge, die aus einer oder mehreren Zeilen besteht.</span><span class="sxs-lookup"><span data-stu-id="1ab50-160">A here-string is a string consisting of one or more lines.</span></span> <span data-ttu-id="1ab50-161">Anführungszeichen in der here-Zeichenfolge werden buchstäblich als Teil der Zeichen folgen Daten interpretiert.</span><span class="sxs-lookup"><span data-stu-id="1ab50-161">Quotation marks within the here-string are interpreted literally as part of the string data.</span></span> <span data-ttu-id="1ab50-162">Weitere Informationen finden Sie unter [about_Quoting_Rules](../Microsoft.PowerShell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="1ab50-162">For more information, see [about_Quoting_Rules](../Microsoft.PowerShell.Core/About/about_Quoting_Rules.md).</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="1ab50-163">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="1ab50-163">CommonParameters</span></span>

<span data-ttu-id="1ab50-164">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="1ab50-164">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="1ab50-165">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="1ab50-165">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="1ab50-166">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="1ab50-166">INPUTS</span></span>

### <span data-ttu-id="1ab50-167">System.String</span><span class="sxs-lookup"><span data-stu-id="1ab50-167">System.String</span></span>

<span data-ttu-id="1ab50-168">Sie können eine Zeichenfolge mit einem Schlüssel-Wert-Paar über die Pipeline an übergeben `ConvertFrom-StringData` .</span><span class="sxs-lookup"><span data-stu-id="1ab50-168">You can pipe a string containing a key-value pair to `ConvertFrom-StringData`.</span></span>

## <span data-ttu-id="1ab50-169">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="1ab50-169">OUTPUTS</span></span>

### <span data-ttu-id="1ab50-170">System.Collections.Hashtable</span><span class="sxs-lookup"><span data-stu-id="1ab50-170">System.Collections.Hashtable</span></span>

<span data-ttu-id="1ab50-171">Dieses Cmdlet gibt eine Hash Tabelle zurück, die aus den Schlüssel-Wert-Paaren erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="1ab50-171">This cmdlet returns a hash table that it creates from the key-value pairs.</span></span>

## <span data-ttu-id="1ab50-172">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="1ab50-172">NOTES</span></span>

<span data-ttu-id="1ab50-173">Eine here-Zeichenfolge ist eine Zeichenfolge, die aus mindestens einer Zeile besteht und in der Anführungszeichen als solche interpretiert werden.</span><span class="sxs-lookup"><span data-stu-id="1ab50-173">A here-string is a string consisting of one or more lines within which quotation marks are interpreted literally.</span></span>

<span data-ttu-id="1ab50-174">Dieses Cmdlet kann in Skripts hilfreich sein, in denen Benutzer Meldungen in mehreren gesprochenen Sprachen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="1ab50-174">This cmdlet can be useful in scripts that display user messages in multiple spoken languages.</span></span> <span data-ttu-id="1ab50-175">Sie können die wörterbuchähnlichen Hashtabellen verwenden, um Textzeichenfolgen z. B. in Ressourcendateien von Code zu isolieren und die Textzeichenfolgen für die Verwendung in Übersetzungstools zu formatieren.</span><span class="sxs-lookup"><span data-stu-id="1ab50-175">You can use the dictionary-style hash tables to isolate text strings from code, such as in resource files, and to format the text strings for use in translation tools.</span></span>

## <span data-ttu-id="1ab50-176">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="1ab50-176">RELATED LINKS</span></span>