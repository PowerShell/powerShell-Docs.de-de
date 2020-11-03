---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 03/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/test-pssessionconfigurationfile?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-PSSessionConfigurationFile
ms.openlocfilehash: ea57ae0b3affcbe060b74c6cc21e6df6d50e50ff
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93217151"
---
# <span data-ttu-id="d1a51-103">Test-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="d1a51-103">Test-PSSessionConfigurationFile</span></span>

## <span data-ttu-id="d1a51-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="d1a51-104">SYNOPSIS</span></span>
<span data-ttu-id="d1a51-105">Überprüft die Schlüssel und Werte in einer Sitzungskonfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="d1a51-105">Verifies the keys and values in a session configuration file.</span></span>

## <span data-ttu-id="d1a51-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d1a51-106">SYNTAX</span></span>

```
Test-PSSessionConfigurationFile [-Path] <String> [<CommonParameters>]
```

## <span data-ttu-id="d1a51-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d1a51-107">DESCRIPTION</span></span>

<span data-ttu-id="d1a51-108">Mit diesem Cmdlet wird überprüft, ob eine Sitzungs Konfigurationsdatei gültige Schlüssel enthält und die Werte den richtigen Typ haben.</span><span class="sxs-lookup"><span data-stu-id="d1a51-108">This cmdlet verifies that a session configuration file contains valid keys and the values are of the correct type.</span></span> <span data-ttu-id="d1a51-109">Bei Enumerationswerten überprüft das Cmdlet, ob die angegebenen Werte gültig sind.</span><span class="sxs-lookup"><span data-stu-id="d1a51-109">For enumerated values, the cmdlet verifies that the specified values are valid.</span></span>

<span data-ttu-id="d1a51-110">Das-Cmdlet gibt zurück, `$True` Wenn die Datei alle Tests übergibt und `$False` andernfalls.</span><span class="sxs-lookup"><span data-stu-id="d1a51-110">The cmdlet returns `$True` if the file passes all tests and `$False` if it does not.</span></span> <span data-ttu-id="d1a51-111">Um Fehler zu finden, verwenden Sie den **verbose** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="d1a51-111">To find any errors, use the **Verbose** parameter.</span></span>

<span data-ttu-id="d1a51-112">`Test-PSSessionConfigurationFile` überprüft die Sitzungs Konfigurationsdateien, z. b. die, die vom `New-PSSessionConfigurationFile` Cmdlet erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="d1a51-112">`Test-PSSessionConfigurationFile` verifies the session configuration files, such as those created by the `New-PSSessionConfigurationFile` cmdlet.</span></span> <span data-ttu-id="d1a51-113">Weitere Informationen zu Sitzungs Konfigurationen finden Sie unter [about_Session_Configurations](About/about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="d1a51-113">For information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span> <span data-ttu-id="d1a51-114">Weitere Informationen zu Sitzungs Konfigurationsdateien finden Sie unter [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md).</span><span class="sxs-lookup"><span data-stu-id="d1a51-114">For information about session configuration files, see [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md).</span></span>

<span data-ttu-id="d1a51-115">Dieses Cmdlet wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="d1a51-115">This cmdlet was introduced in PowerShell 3.0.</span></span>

## <span data-ttu-id="d1a51-116">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="d1a51-116">EXAMPLES</span></span>

### <span data-ttu-id="d1a51-117">Beispiel 1: Testen einer Sitzungs Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="d1a51-117">Example 1: Test a session configuration file</span></span>

```powershell
Test-PSSessionConfigurationFile -Path "FullLanguage.pssc"
```

```Output
True
```

### <span data-ttu-id="d1a51-118">Beispiel 2: Testen der Sitzungs Konfigurationsdatei einer Sitzungs Konfiguration</span><span class="sxs-lookup"><span data-stu-id="d1a51-118">Example 2: Test the session configuration file of a session configuration</span></span>

<span data-ttu-id="d1a51-119">In diesem Beispiel testen wir die Konfigurationsdatei, die in der **eingeschränkten** Sitzungs Konfiguration verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d1a51-119">In this example, we test the configuration file used in the **Restricted** session configuration.</span></span>
<span data-ttu-id="d1a51-120">Der Wert des **path** -Parameters ist das Ergebnis des `Get-PSSessionConfiguration` Befehls, mit dem die **Eingeschränkte** Sitzungs Konfiguration abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="d1a51-120">The value of the **Path** parameter is the result of the `Get-PSSessionConfiguration` command that gets the **Restricted** session configuration.</span></span> <span data-ttu-id="d1a51-121">Der Pfad der Sitzungs Konfigurationsdatei wird im Wert der **configfilepath** -Eigenschaft der Sitzungs Konfiguration gespeichert.</span><span class="sxs-lookup"><span data-stu-id="d1a51-121">The path of the session configuration file is stored in the value of the **ConfigFilePath** property of the session configuration.</span></span>

```powershell
Test-PSSessionConfigurationFile -Path (Get-PSSessionConfiguration -Name Restricted).ConfigFilePath
```

### <span data-ttu-id="d1a51-122">Beispiel 3: Testen aller Sitzungs Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="d1a51-122">Example 3: Test all session configuration files</span></span>

<span data-ttu-id="d1a51-123">Mit der-Funktion in diesem Beispiel werden alle Sitzungs Konfigurationsdateien auf dem lokalen Computer getestet.</span><span class="sxs-lookup"><span data-stu-id="d1a51-123">The function in this example tests all session configuration files on the local computer.</span></span> <span data-ttu-id="d1a51-124">Die-Funktion verwendet das- `Get-PSSessionConfiguration` Cmdlet, um alle Sitzungs Konfigurationen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="d1a51-124">The function uses the `Get-PSSessionConfiguration` cmdlet to get all session configurations.</span></span> <span data-ttu-id="d1a51-125">Der Code in der `ForEach-Object` Schleife zeigt den Dateipfad an und testet jede Sitzungs Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="d1a51-125">The code inside the `ForEach-Object` loop displays the file path and tests each of the session configurations.</span></span>

```powershell
function Test-AllConfigFiles
{
    Get-PSSessionConfiguration | ForEach-Object {
        if ($_.ConfigFilePath) {
            $_.ConfigFilePath
            Test-PSSessionConfigurationFile -Verbose -Path $_.ConfigFilePath
        }
    }
}
Test-AllConfigFiles
```

```Output
C:\WINDOWS\System32\WindowsPowerShell\v1.0\SessionConfig\Empty_6fd77bf6-e084-4372-bd8a-af3e207354d3.pssc
True
C:\WINDOWS\System32\WindowsPowerShell\v1.0\SessionConfig\Full_1e9cb265-dae0-4bd3-89a9-8338a47698a1.pssc
VERBOSE: The member 'AliasDefinitions' must contain the required key 'Description'. Add the require key
to the fileC:\WINDOWS\System32\WindowsPowerShell\v1.0\SessionConfig\Full_1e9cb265-dae0-4bd3-89a9-8338a47698a1.pssc.
False
C:\WINDOWS\System32\WindowsPowerShell\v1.0\SessionConfig\NoLanguage_0c115179-ff2a-4f66-a5eb-e56e5692ba22.pssc
True
C:\WINDOWS\System32\WindowsPowerShell\v1.0\SessionConfig\RestrictedLang_b6bd9474-0a6c-4e06-8722-c2c95bb10d3e.pssc
True
C:\WINDOWS\System32\WindowsPowerShell\v1.0\SessionConfig\RRS_3fb29420-2c87-46e5-a402-e21436331efc.pssc
True
```

<span data-ttu-id="d1a51-126">Die **configfilepath** -Eigenschaft einer Sitzungs Konfiguration enthält den Pfad der Sitzungs Konfigurationsdatei, die in der Sitzungs Konfiguration verwendet wird (sofern vorhanden).</span><span class="sxs-lookup"><span data-stu-id="d1a51-126">The **ConfigFilePath** property of a session configuration contains the path of the session configuration file that is used in the session configuration, if any.</span></span>

<span data-ttu-id="d1a51-127">Wenn der Wert der **ConfigFilePath** -Eigenschaft angegeben ist (sprich er ist „true“), ruft der Befehl den **ConfigFilePath** -Eigenschaftswert ab (bzw. gibt ihn aus).</span><span class="sxs-lookup"><span data-stu-id="d1a51-127">If the value of the **ConfigFilePath** property is populated (is true), the command gets (prints) the **ConfigFilePath** property value.</span></span> <span data-ttu-id="d1a51-128">Dann wird das `Test-PSSessionConfigurationFile` Cmdlet verwendet, um die Datei im **configfilepath** -Wert zu testen.</span><span class="sxs-lookup"><span data-stu-id="d1a51-128">Then it uses the `Test-PSSessionConfigurationFile` cmdlet to test the file in the **ConfigFilePath** value.</span></span> <span data-ttu-id="d1a51-129">Der **Verbose** -Parameter gibt den Dateifehler zurück, wenn die Datei den Test nicht besteht.</span><span class="sxs-lookup"><span data-stu-id="d1a51-129">The **Verbose** parameter returns the file error when the file fails the test.</span></span>

## <span data-ttu-id="d1a51-130">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d1a51-130">PARAMETERS</span></span>

### <span data-ttu-id="d1a51-131">-Path</span><span class="sxs-lookup"><span data-stu-id="d1a51-131">-Path</span></span>

<span data-ttu-id="d1a51-132">Gibt den Pfad und den Dateinamen einer Sitzungs Konfigurationsdatei (. PSSC) an.</span><span class="sxs-lookup"><span data-stu-id="d1a51-132">Specifies the path and filename of a session configuration file (.pssc).</span></span> <span data-ttu-id="d1a51-133">Wenn Sie den Pfad weglassen, wird standardmäßig der aktuelle Ordner angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d1a51-133">If you omit the path, the default is the current folder.</span></span> <span data-ttu-id="d1a51-134">Platzhalter Zeichen werden unterstützt, aber Sie müssen in eine einzelne Datei aufgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="d1a51-134">Wildcard characters are supported, but they must resolve to a single file.</span></span> <span data-ttu-id="d1a51-135">Sie können auch einen Sitzungs Konfigurationsdateipfad an über die Pipeline übergeben `Test-PSSessionConfigurationFile` .</span><span class="sxs-lookup"><span data-stu-id="d1a51-135">You can also pipe a session configuration file path to `Test-PSSessionConfigurationFile`.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="d1a51-136">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="d1a51-136">CommonParameters</span></span>

<span data-ttu-id="d1a51-137">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="d1a51-137">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d1a51-138">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="d1a51-138">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d1a51-139">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="d1a51-139">INPUTS</span></span>

### <span data-ttu-id="d1a51-140">System.String</span><span class="sxs-lookup"><span data-stu-id="d1a51-140">System.String</span></span>

<span data-ttu-id="d1a51-141">Sie können einen Sitzungs Konfigurationsdateipfad an über die Pipeline übergeben `Test-PSSessionConfigurationFile` .</span><span class="sxs-lookup"><span data-stu-id="d1a51-141">You can pipe a session configuration file path to `Test-PSSessionConfigurationFile`.</span></span>

## <span data-ttu-id="d1a51-142">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="d1a51-142">OUTPUTS</span></span>

### <span data-ttu-id="d1a51-143">System.Boolean</span><span class="sxs-lookup"><span data-stu-id="d1a51-143">System.Boolean</span></span>

## <span data-ttu-id="d1a51-144">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="d1a51-144">NOTES</span></span>

## <span data-ttu-id="d1a51-145">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="d1a51-145">RELATED LINKS</span></span>

[<span data-ttu-id="d1a51-146">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="d1a51-146">Disable-PSSessionConfiguration</span></span>](Disable-PSSessionConfiguration.md)

[<span data-ttu-id="d1a51-147">Enable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="d1a51-147">Enable-PSSessionConfiguration</span></span>](Enable-PSSessionConfiguration.md)

[<span data-ttu-id="d1a51-148">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="d1a51-148">Get-PSSessionConfiguration</span></span>](Get-PSSessionConfiguration.md)

[<span data-ttu-id="d1a51-149">New-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="d1a51-149">New-PSSessionConfigurationFile</span></span>](New-PSSessionConfigurationFile.md)

[<span data-ttu-id="d1a51-150">New-PSSessionOption</span><span class="sxs-lookup"><span data-stu-id="d1a51-150">New-PSSessionOption</span></span>](New-PSSessionOption.md)

[<span data-ttu-id="d1a51-151">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="d1a51-151">Register-PSSessionConfiguration</span></span>](Register-PSSessionConfiguration.md)

[<span data-ttu-id="d1a51-152">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="d1a51-152">Set-PSSessionConfiguration</span></span>](Set-PSSessionConfiguration.md)

[<span data-ttu-id="d1a51-153">Test-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="d1a51-153">Test-PSSessionConfigurationFile</span></span>](Test-PSSessionConfigurationFile.md)

[<span data-ttu-id="d1a51-154">Unregister-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="d1a51-154">Unregister-PSSessionConfiguration</span></span>](Unregister-PSSessionConfiguration.md)

[<span data-ttu-id="d1a51-155">WSMan-Anbieter</span><span class="sxs-lookup"><span data-stu-id="d1a51-155">WSMan Provider</span></span>](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

[<span data-ttu-id="d1a51-156">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="d1a51-156">about_Session_Configurations</span></span>](About/about_Session_Configurations.md)

[<span data-ttu-id="d1a51-157">about_Session_Configuration_Files</span><span class="sxs-lookup"><span data-stu-id="d1a51-157">about_Session_Configuration_Files</span></span>](About/about_Session_Configuration_Files.md)