---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 5/1/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/rename-computer?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Rename-Computer
ms.openlocfilehash: 860a5ec4f75136bd53fa5c9621504b1613e9c511
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214527"
---
# <span data-ttu-id="027f3-103">Rename-Computer</span><span class="sxs-lookup"><span data-stu-id="027f3-103">Rename-Computer</span></span>

## <span data-ttu-id="027f3-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="027f3-104">SYNOPSIS</span></span>
<span data-ttu-id="027f3-105">Benennt einen Computer um.</span><span class="sxs-lookup"><span data-stu-id="027f3-105">Renames a computer.</span></span>

## <span data-ttu-id="027f3-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="027f3-106">SYNTAX</span></span>

```
Rename-Computer [-ComputerName <String>] [-PassThru] [-DomainCredential <PSCredential>]
 [-LocalCredential <PSCredential>] [-NewName] <String> [-Force] [-Restart] [-WsmanAuthentication <String>]
 [-Protocol <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="027f3-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="027f3-107">DESCRIPTION</span></span>

<span data-ttu-id="027f3-108">Das `Rename-Computer` Cmdlet benennt den lokalen Computer oder einen Remote Computer um.</span><span class="sxs-lookup"><span data-stu-id="027f3-108">The `Rename-Computer` cmdlet renames the local computer or a remote computer.</span></span>
<span data-ttu-id="027f3-109">Es benennt einen Computer in jedem Befehl um.</span><span class="sxs-lookup"><span data-stu-id="027f3-109">It renames one computer in each command.</span></span>

<span data-ttu-id="027f3-110">Dieses Cmdlet wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="027f3-110">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="027f3-111">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="027f3-111">EXAMPLES</span></span>

### <span data-ttu-id="027f3-112">Beispiel 1: Umbenennen des lokalen Computers</span><span class="sxs-lookup"><span data-stu-id="027f3-112">Example 1: Rename the local computer</span></span>

<span data-ttu-id="027f3-113">Mit diesem Befehl wird der lokale Computer in umbenannt `Server044` und dann neu gestartet, damit die Änderung wirksam wird.</span><span class="sxs-lookup"><span data-stu-id="027f3-113">This command renames the local computer to `Server044` and then restarts it to make the change effective.</span></span>

```powershell
Rename-Computer -NewName "Server044" -DomainCredential Domain01\Admin01 -Restart
```

### <span data-ttu-id="027f3-114">Beispiel 2: Umbenennen eines Remote Computers</span><span class="sxs-lookup"><span data-stu-id="027f3-114">Example 2: Rename a remote computer</span></span>

<span data-ttu-id="027f3-115">Mit diesem Befehl wird der `Srv01` Computer in umbenannt `Server001` .</span><span class="sxs-lookup"><span data-stu-id="027f3-115">This command renames the `Srv01` computer to `Server001`.</span></span> <span data-ttu-id="027f3-116">Der Computer wird nicht neu gestartet.</span><span class="sxs-lookup"><span data-stu-id="027f3-116">The computer is not restarted.</span></span>

<span data-ttu-id="027f3-117">Mit dem **domaincredential** -Parameter werden die Anmelde Informationen eines Benutzers angegeben, der über die Berechtigung zum Umbenennen von Computern in der Domäne verfügt.</span><span class="sxs-lookup"><span data-stu-id="027f3-117">The **DomainCredential** parameter specifies the credentials of a user who has permission to rename computers in the domain.</span></span>

<span data-ttu-id="027f3-118">Der **Force** -Parameter unterdrückt die Bestätigungsaufforderung.</span><span class="sxs-lookup"><span data-stu-id="027f3-118">The **Force** parameter suppresses the confirmation prompt.</span></span>

```powershell
Rename-Computer -ComputerName "Srv01" -NewName "Server001" -DomainCredential Domain01\Admin01 -Force
```

## <span data-ttu-id="027f3-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="027f3-119">PARAMETERS</span></span>

### <span data-ttu-id="027f3-120">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="027f3-120">-ComputerName</span></span>

<span data-ttu-id="027f3-121">Benennt den angegebenen Remotecomputer um.</span><span class="sxs-lookup"><span data-stu-id="027f3-121">Renames the specified remote computer.</span></span>
<span data-ttu-id="027f3-122">Die Standardeinstellung ist der lokale Computer.</span><span class="sxs-lookup"><span data-stu-id="027f3-122">The default is the local computer.</span></span>

<span data-ttu-id="027f3-123">Geben Sie den NetBIOS-Namen, eine IP-Adresse oder den vollqualifizierten Domänennamen eines Remotecomputers ein.</span><span class="sxs-lookup"><span data-stu-id="027f3-123">Type the NetBIOS name, an IP address, or a fully qualified domain name of a remote computer.</span></span>
<span data-ttu-id="027f3-124">Um den lokalen Computer anzugeben, geben Sie den Computernamen, einen Punkt ( `.` ) oder ein `localhost` .</span><span class="sxs-lookup"><span data-stu-id="027f3-124">To specify the local computer, type the computer name, a dot (`.`), or `localhost`.</span></span>

<span data-ttu-id="027f3-125">Dieser Parameter beruht nicht auf PowerShell-Remoting.</span><span class="sxs-lookup"><span data-stu-id="027f3-125">This parameter does not rely on PowerShell remoting.</span></span>
<span data-ttu-id="027f3-126">Sie können den **Computername** -Parameter `Rename-Computer` auch dann verwenden, wenn der Computer nicht für das Ausführen von Remote Befehlen konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="027f3-126">You can use the **ComputerName** parameter of `Rename-Computer` even if your computer is not configured to run remote commands.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Local Computer
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="027f3-127">-Domaincredential</span><span class="sxs-lookup"><span data-stu-id="027f3-127">-DomainCredential</span></span>

<span data-ttu-id="027f3-128">Gibt ein Benutzerkonto an, das über die Berechtigung zum Herstellen einer Verbindung mit der Domäne verfügt.</span><span class="sxs-lookup"><span data-stu-id="027f3-128">Specifies a user account that has permission to connect to the domain.</span></span>
<span data-ttu-id="027f3-129">Zum Umbenennen eines der Domäne hinzugefügten Computers sind explizite Anmeldeinformationen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="027f3-129">Explicit credentials are required to rename a computer that is joined to a domain.</span></span>

<span data-ttu-id="027f3-130">Geben Sie einen Benutzernamen ein, z. b. `User01` oder `Domain01\User01` , oder geben Sie ein **PSCredential** -Objekt ein, z. b. ein vom `Get-Credential` Cmdlet generiertes Objekt.</span><span class="sxs-lookup"><span data-stu-id="027f3-130">Type a user name, such as `User01` or `Domain01\User01`, or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span>

<span data-ttu-id="027f3-131">Wenn Sie einen Benutzernamen eingeben, werden Sie von diesem Cmdlet zur Eingabe eines Kennworts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="027f3-131">If you type a user name, this cmdlet prompts you for a password.</span></span>

<span data-ttu-id="027f3-132">Geben Sie ein Benutzerkonto, das über die Berechtigung zum Herstellen einer Verbindung mit dem durch den **ComputerName** -Parameter angegebenen Computer verfügt, mit dem **LocalCredential** -Parameter an.</span><span class="sxs-lookup"><span data-stu-id="027f3-132">To specify a user account that has permission to connect to the computer that is specified by the **ComputerName** parameter, use the **LocalCredential** parameter.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="027f3-133">-Force</span><span class="sxs-lookup"><span data-stu-id="027f3-133">-Force</span></span>

<span data-ttu-id="027f3-134">Erzwingt die Ausführung des Befehls ohne Aufforderung zur Bestätigung durch den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="027f3-134">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="027f3-135">-Localcredential</span><span class="sxs-lookup"><span data-stu-id="027f3-135">-LocalCredential</span></span>

<span data-ttu-id="027f3-136">Gibt ein Benutzerkonto an, das über die Berechtigung zum Herstellen einer Verbindung mit dem durch den **ComputerName** -Parameter angegebenen Computer verfügt.</span><span class="sxs-lookup"><span data-stu-id="027f3-136">Specifies a user account that has permission to connect to the computer specified by the **ComputerName** parameter.</span></span> <span data-ttu-id="027f3-137">Der Standardwert ist der aktuelle Benutzer.</span><span class="sxs-lookup"><span data-stu-id="027f3-137">The default is the current user.</span></span>

<span data-ttu-id="027f3-138">Geben Sie einen Benutzernamen ein, z. b. `User01` oder `Domain01\User01` , oder geben Sie ein **PSCredential** -Objekt ein, z. b. ein vom `Get-Credential` Cmdlet generiertes Objekt.</span><span class="sxs-lookup"><span data-stu-id="027f3-138">Type a user name, such as `User01` or `Domain01\User01`, or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span>

<span data-ttu-id="027f3-139">Wenn Sie einen Benutzernamen eingeben, werden Sie von diesem Cmdlet zur Eingabe eines Kennworts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="027f3-139">If you type a user name, this cmdlet prompts you for a password.</span></span>

<span data-ttu-id="027f3-140">Geben Sie ein Benutzerkonto, das über die Berechtigung zum Herstellen einer Verbindung mit der Domäne verfügt, mit dem **DomainCredential** -Parameter an.</span><span class="sxs-lookup"><span data-stu-id="027f3-140">To specify a user account that has permission to connect to the domain, use the **DomainCredential** parameter.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current User
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="027f3-141">-Newname</span><span class="sxs-lookup"><span data-stu-id="027f3-141">-NewName</span></span>

<span data-ttu-id="027f3-142">Gibt einen neuen Namen für den Computer an.</span><span class="sxs-lookup"><span data-stu-id="027f3-142">Specifies a new name for the computer.</span></span>
<span data-ttu-id="027f3-143">Dieser Parameter ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="027f3-143">This parameter is required.</span></span>

<span data-ttu-id="027f3-144">Standard Namen dürfen Buchstaben ( `a-z` ), ( `A-Z` ), Zahlen ( `0-9` ) und Bindestriche ( `-` ), jedoch keine Leerzeichen oder Punkte ( `.` ) enthalten.</span><span class="sxs-lookup"><span data-stu-id="027f3-144">Standard names may contain letters (`a-z`), (`A-Z`), numbers (`0-9`), and hyphens (`-`), but no spaces or periods (`.`).</span></span> <span data-ttu-id="027f3-145">Der Name darf nicht vollständig aus Ziffern bestehen und darf nicht länger als 63 Zeichen sein.</span><span class="sxs-lookup"><span data-stu-id="027f3-145">The name may not consist entirely of digits, and may not be longer than 63 characters</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="027f3-146">-PassThru</span><span class="sxs-lookup"><span data-stu-id="027f3-146">-PassThru</span></span>

<span data-ttu-id="027f3-147">Gibt die Ergebnisse des Befehls zurück.</span><span class="sxs-lookup"><span data-stu-id="027f3-147">Returns the results of the command.</span></span>
<span data-ttu-id="027f3-148">Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="027f3-148">Otherwise, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="027f3-149">-Protocol</span><span class="sxs-lookup"><span data-stu-id="027f3-149">-Protocol</span></span>

<span data-ttu-id="027f3-150">Gibt an, welches Protokoll zum Umbenennen des Computers verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="027f3-150">Specifies which protocol to use to rename the computer.</span></span>
<span data-ttu-id="027f3-151">Die zulässigen Werte für diesen Parameter sind: WSMAN und DCOM.</span><span class="sxs-lookup"><span data-stu-id="027f3-151">The acceptable values for this parameter are: WSMan and DCOM.</span></span>
<span data-ttu-id="027f3-152">Der Standardwert ist DCOM.</span><span class="sxs-lookup"><span data-stu-id="027f3-152">The default value is DCOM.</span></span>

<span data-ttu-id="027f3-153">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="027f3-153">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: DCOM, WSMan

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="027f3-154">-Restart</span><span class="sxs-lookup"><span data-stu-id="027f3-154">-Restart</span></span>

<span data-ttu-id="027f3-155">Gibt an, dass mit diesem Cmdlet der umbenannte Computer neu gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="027f3-155">Indicates that this cmdlet restarts the computer that was renamed.</span></span>
<span data-ttu-id="027f3-156">Ein Neustart ist häufig erforderlich, damit die Änderung wirksam wird.</span><span class="sxs-lookup"><span data-stu-id="027f3-156">A restart is often required to make the change effective.</span></span>

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

### <span data-ttu-id="027f3-157">-Wsmanauthentication</span><span class="sxs-lookup"><span data-stu-id="027f3-157">-WsmanAuthentication</span></span>

<span data-ttu-id="027f3-158">Gibt den Mechanismus an, der verwendet wird, um die Benutzer Anmelde Informationen zu authentifizieren, wenn dieses Cmdlet das WSMAN-Protokoll verwendet.</span><span class="sxs-lookup"><span data-stu-id="027f3-158">Specifies the mechanism that is used to authenticate the user credentials when this cmdlet uses the WSMan protocol.</span></span> <span data-ttu-id="027f3-159">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="027f3-159">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="027f3-160">**Grundlegend**</span><span class="sxs-lookup"><span data-stu-id="027f3-160">**Basic**</span></span>
- <span data-ttu-id="027f3-161">**CredSSP**</span><span class="sxs-lookup"><span data-stu-id="027f3-161">**CredSSP**</span></span>
- <span data-ttu-id="027f3-162">**Standard**</span><span class="sxs-lookup"><span data-stu-id="027f3-162">**Default**</span></span>
- <span data-ttu-id="027f3-163">**Digest**</span><span class="sxs-lookup"><span data-stu-id="027f3-163">**Digest**</span></span>
- <span data-ttu-id="027f3-164">**Kerberos**</span><span class="sxs-lookup"><span data-stu-id="027f3-164">**Kerberos**</span></span>
- <span data-ttu-id="027f3-165">**Verhandelt**</span><span class="sxs-lookup"><span data-stu-id="027f3-165">**Negotiate**</span></span>

<span data-ttu-id="027f3-166">Der Standardwert lautet **Default** .</span><span class="sxs-lookup"><span data-stu-id="027f3-166">The default value is **Default** .</span></span>

<span data-ttu-id="027f3-167">Weitere Informationen zu den Werten dieses Parameters finden Sie unter [authenticationmechanism-Enumeration](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span><span class="sxs-lookup"><span data-stu-id="027f3-167">For more information about the values of this parameter, see [AuthenticationMechanism Enumeration](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span></span>

> [!WARNING]
> <span data-ttu-id="027f3-168">Die Authentifizierung des Anmelde Informations Diensts (Credential Security Service Provider, kredssp), in der die Benutzer Anmelde Informationen an einen Remote Computer übergeben werden, der authentifiziert werden soll, wurde für Befehle entworfen, die eine Authentifizierung auf mehreren Ressourcen erfordern</span><span class="sxs-lookup"><span data-stu-id="027f3-168">Credential Security Service Provider (CredSSP) authentication, in which the user credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span>
> <span data-ttu-id="027f3-169">Dieser Mechanismus erhöht das Sicherheitsrisiko des Remotevorgangs.</span><span class="sxs-lookup"><span data-stu-id="027f3-169">This mechanism increases the security risk of the remote operation.</span></span>
> <span data-ttu-id="027f3-170">Wenn der Remote Computer kompromittiert ist, können die an ihn weiter gegebenen Anmelde Informationen verwendet werden, um > die Netzwerksitzung zu steuern.</span><span class="sxs-lookup"><span data-stu-id="027f3-170">If the remote computer is compromised, the credentials that are passed to it can be used to control > the network session.</span></span>

<span data-ttu-id="027f3-171">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="027f3-171">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Default, Basic, Negotiate, CredSSP, Digest, Kerberos

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="027f3-172">-Confirm</span><span class="sxs-lookup"><span data-stu-id="027f3-172">-Confirm</span></span>

<span data-ttu-id="027f3-173">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="027f3-173">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="027f3-174">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="027f3-174">-WhatIf</span></span>

<span data-ttu-id="027f3-175">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="027f3-175">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="027f3-176">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="027f3-176">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="027f3-177">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="027f3-177">CommonParameters</span></span>

<span data-ttu-id="027f3-178">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="027f3-178">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="027f3-179">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="027f3-179">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="027f3-180">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="027f3-180">INPUTS</span></span>

### <span data-ttu-id="027f3-181">Keine</span><span class="sxs-lookup"><span data-stu-id="027f3-181">None</span></span>

<span data-ttu-id="027f3-182">Dieses Cmdlet enthält keine Parameter, die eine Eingabe nach Wert annehmen.</span><span class="sxs-lookup"><span data-stu-id="027f3-182">This cmdlet does not have parameters that take input by value.</span></span>
<span data-ttu-id="027f3-183">Sie können jedoch die Werte der Eigenschaften **ComputerName** und **NewName** von Objekten über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="027f3-183">However, you can pipe the values of the **ComputerName** and **NewName** properties of objects to this cmdlet.</span></span>

## <span data-ttu-id="027f3-184">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="027f3-184">OUTPUTS</span></span>

### <span data-ttu-id="027f3-185">Microsoft. PowerShell. Commands. computerchangeingefo</span><span class="sxs-lookup"><span data-stu-id="027f3-185">Microsoft.PowerShell.Commands.ComputerChangeInfo</span></span>

<span data-ttu-id="027f3-186">Dieses Cmdlet gibt ein **computerchangeinfo** -Objekt zurück, wenn Sie den **passthru** -Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="027f3-186">This cmdlet returns a **ComputerChangeInfo** object, if you specify the **PassThru** parameter.</span></span>
<span data-ttu-id="027f3-187">Andernfalls wird keine Ausgabe zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="027f3-187">Otherwise, it does not return any output.</span></span>

## <span data-ttu-id="027f3-188">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="027f3-188">NOTES</span></span>

## <span data-ttu-id="027f3-189">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="027f3-189">RELATED LINKS</span></span>

[<span data-ttu-id="027f3-190">Add-Computer</span><span class="sxs-lookup"><span data-stu-id="027f3-190">Add-Computer</span></span>](Add-Computer.md)

[<span data-ttu-id="027f3-191">Remove-Computer</span><span class="sxs-lookup"><span data-stu-id="027f3-191">Remove-Computer</span></span>](Remove-Computer.md)

[<span data-ttu-id="027f3-192">Reset-ComputerMachinePassword</span><span class="sxs-lookup"><span data-stu-id="027f3-192">Reset-ComputerMachinePassword</span></span>](Reset-ComputerMachinePassword.md)

[<span data-ttu-id="027f3-193">Restart-Computer</span><span class="sxs-lookup"><span data-stu-id="027f3-193">Restart-Computer</span></span>](Restart-Computer.md)

[<span data-ttu-id="027f3-194">Stop-Computer</span><span class="sxs-lookup"><span data-stu-id="027f3-194">Stop-Computer</span></span>](Stop-Computer.md)