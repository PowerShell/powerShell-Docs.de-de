---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 5/1/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/rename-computer?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Rename-Computer
ms.openlocfilehash: e2d4f321609a386c6795949a4a706323b4889f69
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93216103"
---
# <span data-ttu-id="48c74-103">Rename-Computer</span><span class="sxs-lookup"><span data-stu-id="48c74-103">Rename-Computer</span></span>

## <span data-ttu-id="48c74-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="48c74-104">SYNOPSIS</span></span>
<span data-ttu-id="48c74-105">Benennt einen Computer um.</span><span class="sxs-lookup"><span data-stu-id="48c74-105">Renames a computer.</span></span>

## <span data-ttu-id="48c74-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="48c74-106">SYNTAX</span></span>

```
Rename-Computer [-ComputerName <String>] [-PassThru] [-DomainCredential <PSCredential>]
 [-LocalCredential <PSCredential>] [-NewName] <String> [-Force] [-Restart] [-WsmanAuthentication <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="48c74-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="48c74-107">DESCRIPTION</span></span>

<span data-ttu-id="48c74-108">Das `Rename-Computer` Cmdlet benennt den lokalen Computer oder einen Remote Computer um.</span><span class="sxs-lookup"><span data-stu-id="48c74-108">The `Rename-Computer` cmdlet renames the local computer or a remote computer.</span></span>
<span data-ttu-id="48c74-109">Es benennt einen Computer in jedem Befehl um.</span><span class="sxs-lookup"><span data-stu-id="48c74-109">It renames one computer in each command.</span></span>

<span data-ttu-id="48c74-110">Dieses Cmdlet wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="48c74-110">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="48c74-111">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="48c74-111">EXAMPLES</span></span>

### <span data-ttu-id="48c74-112">Beispiel 1: Umbenennen des lokalen Computers</span><span class="sxs-lookup"><span data-stu-id="48c74-112">Example 1: Rename the local computer</span></span>

<span data-ttu-id="48c74-113">Mit diesem Befehl wird der lokale Computer in umbenannt `Server044` und dann neu gestartet, damit die Änderung wirksam wird.</span><span class="sxs-lookup"><span data-stu-id="48c74-113">This command renames the local computer to `Server044` and then restarts it to make the change effective.</span></span>

```powershell
Rename-Computer -NewName "Server044" -DomainCredential Domain01\Admin01 -Restart
```

### <span data-ttu-id="48c74-114">Beispiel 2: Umbenennen eines Remote Computers</span><span class="sxs-lookup"><span data-stu-id="48c74-114">Example 2: Rename a remote computer</span></span>

<span data-ttu-id="48c74-115">Mit diesem Befehl wird der `Srv01` Computer in umbenannt `Server001` .</span><span class="sxs-lookup"><span data-stu-id="48c74-115">This command renames the `Srv01` computer to `Server001`.</span></span> <span data-ttu-id="48c74-116">Der Computer wird nicht neu gestartet.</span><span class="sxs-lookup"><span data-stu-id="48c74-116">The computer is not restarted.</span></span>

<span data-ttu-id="48c74-117">Mit dem **domaincredential** -Parameter werden die Anmelde Informationen eines Benutzers angegeben, der über die Berechtigung zum Umbenennen von Computern in der Domäne verfügt.</span><span class="sxs-lookup"><span data-stu-id="48c74-117">The **DomainCredential** parameter specifies the credentials of a user who has permission to rename computers in the domain.</span></span>

<span data-ttu-id="48c74-118">Der **Force** -Parameter unterdrückt die Bestätigungsaufforderung.</span><span class="sxs-lookup"><span data-stu-id="48c74-118">The **Force** parameter suppresses the confirmation prompt.</span></span>

```powershell
Rename-Computer -ComputerName "Srv01" -NewName "Server001" -DomainCredential Domain01\Admin01 -Force
```

## <span data-ttu-id="48c74-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="48c74-119">PARAMETERS</span></span>

### <span data-ttu-id="48c74-120">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="48c74-120">-ComputerName</span></span>

<span data-ttu-id="48c74-121">Benennt den angegebenen Remotecomputer um.</span><span class="sxs-lookup"><span data-stu-id="48c74-121">Renames the specified remote computer.</span></span>
<span data-ttu-id="48c74-122">Die Standardeinstellung ist der lokale Computer.</span><span class="sxs-lookup"><span data-stu-id="48c74-122">The default is the local computer.</span></span>

<span data-ttu-id="48c74-123">Geben Sie den NetBIOS-Namen, eine IP-Adresse oder den vollqualifizierten Domänennamen eines Remotecomputers ein.</span><span class="sxs-lookup"><span data-stu-id="48c74-123">Type the NetBIOS name, an IP address, or a fully qualified domain name of a remote computer.</span></span>
<span data-ttu-id="48c74-124">Um den lokalen Computer anzugeben, geben Sie den Computernamen, einen Punkt ( `.` ) oder ein `localhost` .</span><span class="sxs-lookup"><span data-stu-id="48c74-124">To specify the local computer, type the computer name, a dot (`.`), or `localhost`.</span></span>

<span data-ttu-id="48c74-125">Dieser Parameter beruht nicht auf PowerShell-Remoting.</span><span class="sxs-lookup"><span data-stu-id="48c74-125">This parameter does not rely on PowerShell remoting.</span></span>
<span data-ttu-id="48c74-126">Sie können den **Computername** -Parameter `Rename-Computer` auch dann verwenden, wenn der Computer nicht für das Ausführen von Remote Befehlen konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="48c74-126">You can use the **ComputerName** parameter of `Rename-Computer` even if your computer is not configured to run remote commands.</span></span>

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

### <span data-ttu-id="48c74-127">-Domaincredential</span><span class="sxs-lookup"><span data-stu-id="48c74-127">-DomainCredential</span></span>

<span data-ttu-id="48c74-128">Gibt ein Benutzerkonto an, das über die Berechtigung zum Herstellen einer Verbindung mit der Domäne verfügt.</span><span class="sxs-lookup"><span data-stu-id="48c74-128">Specifies a user account that has permission to connect to the domain.</span></span>
<span data-ttu-id="48c74-129">Zum Umbenennen eines der Domäne hinzugefügten Computers sind explizite Anmeldeinformationen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="48c74-129">Explicit credentials are required to rename a computer that is joined to a domain.</span></span>

<span data-ttu-id="48c74-130">Geben Sie einen Benutzernamen ein, z. b. `User01` oder `Domain01\User01` , oder geben Sie ein **PSCredential** -Objekt ein, z. b. ein vom `Get-Credential` Cmdlet generiertes Objekt.</span><span class="sxs-lookup"><span data-stu-id="48c74-130">Type a user name, such as `User01` or `Domain01\User01`, or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span>

<span data-ttu-id="48c74-131">Wenn Sie einen Benutzernamen eingeben, werden Sie von diesem Cmdlet zur Eingabe eines Kennworts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="48c74-131">If you type a user name, this cmdlet prompts you for a password.</span></span>

<span data-ttu-id="48c74-132">Geben Sie ein Benutzerkonto, das über die Berechtigung zum Herstellen einer Verbindung mit dem durch den **ComputerName** -Parameter angegebenen Computer verfügt, mit dem **LocalCredential** -Parameter an.</span><span class="sxs-lookup"><span data-stu-id="48c74-132">To specify a user account that has permission to connect to the computer that is specified by the **ComputerName** parameter, use the **LocalCredential** parameter.</span></span>

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

### <span data-ttu-id="48c74-133">-Force</span><span class="sxs-lookup"><span data-stu-id="48c74-133">-Force</span></span>

<span data-ttu-id="48c74-134">Erzwingt die Ausführung des Befehls ohne Aufforderung zur Bestätigung durch den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="48c74-134">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="48c74-135">-Localcredential</span><span class="sxs-lookup"><span data-stu-id="48c74-135">-LocalCredential</span></span>

<span data-ttu-id="48c74-136">Gibt ein Benutzerkonto an, das über die Berechtigung zum Herstellen einer Verbindung mit dem durch den **ComputerName** -Parameter angegebenen Computer verfügt.</span><span class="sxs-lookup"><span data-stu-id="48c74-136">Specifies a user account that has permission to connect to the computer specified by the **ComputerName** parameter.</span></span> <span data-ttu-id="48c74-137">Der Standardwert ist der aktuelle Benutzer.</span><span class="sxs-lookup"><span data-stu-id="48c74-137">The default is the current user.</span></span>

<span data-ttu-id="48c74-138">Geben Sie einen Benutzernamen ein, z. b. `User01` oder `Domain01\User01` , oder geben Sie ein **PSCredential** -Objekt ein, z. b. ein vom `Get-Credential` Cmdlet generiertes Objekt.</span><span class="sxs-lookup"><span data-stu-id="48c74-138">Type a user name, such as `User01` or `Domain01\User01`, or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span>

<span data-ttu-id="48c74-139">Wenn Sie einen Benutzernamen eingeben, werden Sie von diesem Cmdlet zur Eingabe eines Kennworts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="48c74-139">If you type a user name, this cmdlet prompts you for a password.</span></span>

<span data-ttu-id="48c74-140">Geben Sie ein Benutzerkonto, das über die Berechtigung zum Herstellen einer Verbindung mit der Domäne verfügt, mit dem **DomainCredential** -Parameter an.</span><span class="sxs-lookup"><span data-stu-id="48c74-140">To specify a user account that has permission to connect to the domain, use the **DomainCredential** parameter.</span></span>

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

### <span data-ttu-id="48c74-141">-Newname</span><span class="sxs-lookup"><span data-stu-id="48c74-141">-NewName</span></span>

<span data-ttu-id="48c74-142">Gibt einen neuen Namen für den Computer an.</span><span class="sxs-lookup"><span data-stu-id="48c74-142">Specifies a new name for the computer.</span></span>
<span data-ttu-id="48c74-143">Dieser Parameter ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="48c74-143">This parameter is required.</span></span>

<span data-ttu-id="48c74-144">Standard Namen dürfen Buchstaben ( `a-z` ), ( `A-Z` ), Zahlen ( `0-9` ) und Bindestriche ( `-` ), jedoch keine Leerzeichen oder Punkte ( `.` ) enthalten.</span><span class="sxs-lookup"><span data-stu-id="48c74-144">Standard names may contain letters (`a-z`), (`A-Z`), numbers (`0-9`), and hyphens (`-`), but no spaces or periods (`.`).</span></span> <span data-ttu-id="48c74-145">Der Name darf nicht vollständig aus Ziffern bestehen und darf nicht länger als 63 Zeichen sein.</span><span class="sxs-lookup"><span data-stu-id="48c74-145">The name may not consist entirely of digits, and may not be longer than 63 characters</span></span>

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

### <span data-ttu-id="48c74-146">-PassThru</span><span class="sxs-lookup"><span data-stu-id="48c74-146">-PassThru</span></span>

<span data-ttu-id="48c74-147">Gibt die Ergebnisse des Befehls zurück.</span><span class="sxs-lookup"><span data-stu-id="48c74-147">Returns the results of the command.</span></span>
<span data-ttu-id="48c74-148">Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="48c74-148">Otherwise, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="48c74-149">-Restart</span><span class="sxs-lookup"><span data-stu-id="48c74-149">-Restart</span></span>

<span data-ttu-id="48c74-150">Gibt an, dass mit diesem Cmdlet der umbenannte Computer neu gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="48c74-150">Indicates that this cmdlet restarts the computer that was renamed.</span></span>
<span data-ttu-id="48c74-151">Ein Neustart ist häufig erforderlich, damit die Änderung wirksam wird.</span><span class="sxs-lookup"><span data-stu-id="48c74-151">A restart is often required to make the change effective.</span></span>

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

### <span data-ttu-id="48c74-152">-Wsmanauthentication</span><span class="sxs-lookup"><span data-stu-id="48c74-152">-WsmanAuthentication</span></span>

<span data-ttu-id="48c74-153">Gibt den Mechanismus an, der verwendet wird, um die Benutzer Anmelde Informationen zu authentifizieren, wenn dieses Cmdlet das WSMAN-Protokoll verwendet.</span><span class="sxs-lookup"><span data-stu-id="48c74-153">Specifies the mechanism that is used to authenticate the user credentials when this cmdlet uses the WSMan protocol.</span></span> <span data-ttu-id="48c74-154">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="48c74-154">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="48c74-155">**Grundlegend**</span><span class="sxs-lookup"><span data-stu-id="48c74-155">**Basic**</span></span>
- <span data-ttu-id="48c74-156">**CredSSP**</span><span class="sxs-lookup"><span data-stu-id="48c74-156">**CredSSP**</span></span>
- <span data-ttu-id="48c74-157">**Standard**</span><span class="sxs-lookup"><span data-stu-id="48c74-157">**Default**</span></span>
- <span data-ttu-id="48c74-158">**Digest**</span><span class="sxs-lookup"><span data-stu-id="48c74-158">**Digest**</span></span>
- <span data-ttu-id="48c74-159">**Kerberos**</span><span class="sxs-lookup"><span data-stu-id="48c74-159">**Kerberos**</span></span>
- <span data-ttu-id="48c74-160">**Verhandelt**</span><span class="sxs-lookup"><span data-stu-id="48c74-160">**Negotiate**</span></span>

<span data-ttu-id="48c74-161">Der Standardwert lautet **Default** .</span><span class="sxs-lookup"><span data-stu-id="48c74-161">The default value is **Default** .</span></span>

<span data-ttu-id="48c74-162">Weitere Informationen zu den Werten dieses Parameters finden Sie unter [authenticationmechanism-Enumeration](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span><span class="sxs-lookup"><span data-stu-id="48c74-162">For more information about the values of this parameter, see [AuthenticationMechanism Enumeration](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span></span>

> [!WARNING]
> <span data-ttu-id="48c74-163">Die Authentifizierung des Anmelde Informations Diensts (Credential Security Service Provider, kredssp), in der die Benutzer Anmelde Informationen an einen Remote Computer übergeben werden, der authentifiziert werden soll, wurde für Befehle entworfen, die eine Authentifizierung auf mehreren Ressourcen erfordern</span><span class="sxs-lookup"><span data-stu-id="48c74-163">Credential Security Service Provider (CredSSP) authentication, in which the user credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span>
> <span data-ttu-id="48c74-164">Dieser Mechanismus erhöht das Sicherheitsrisiko des Remotevorgangs.</span><span class="sxs-lookup"><span data-stu-id="48c74-164">This mechanism increases the security risk of the remote operation.</span></span>
> <span data-ttu-id="48c74-165">Wenn der Remote Computer kompromittiert ist, können die an ihn weiter gegebenen Anmelde Informationen verwendet werden, um > die Netzwerksitzung zu steuern.</span><span class="sxs-lookup"><span data-stu-id="48c74-165">If the remote computer is compromised, the credentials that are passed to it can be used to control > the network session.</span></span>

<span data-ttu-id="48c74-166">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="48c74-166">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="48c74-167">-Confirm</span><span class="sxs-lookup"><span data-stu-id="48c74-167">-Confirm</span></span>

<span data-ttu-id="48c74-168">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="48c74-168">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="48c74-169">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="48c74-169">-WhatIf</span></span>

<span data-ttu-id="48c74-170">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="48c74-170">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="48c74-171">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="48c74-171">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="48c74-172">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="48c74-172">CommonParameters</span></span>

<span data-ttu-id="48c74-173">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="48c74-173">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="48c74-174">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="48c74-174">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="48c74-175">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="48c74-175">INPUTS</span></span>

### <span data-ttu-id="48c74-176">Keine</span><span class="sxs-lookup"><span data-stu-id="48c74-176">None</span></span>

<span data-ttu-id="48c74-177">Dieses Cmdlet enthält keine Parameter, die eine Eingabe nach Wert annehmen.</span><span class="sxs-lookup"><span data-stu-id="48c74-177">This cmdlet does not have parameters that take input by value.</span></span>
<span data-ttu-id="48c74-178">Sie können jedoch die Werte der Eigenschaften **ComputerName** und **NewName** von Objekten über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="48c74-178">However, you can pipe the values of the **ComputerName** and **NewName** properties of objects to this cmdlet.</span></span>

## <span data-ttu-id="48c74-179">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="48c74-179">OUTPUTS</span></span>

### <span data-ttu-id="48c74-180">Microsoft. PowerShell. Commands. computerchangeingefo</span><span class="sxs-lookup"><span data-stu-id="48c74-180">Microsoft.PowerShell.Commands.ComputerChangeInfo</span></span>

<span data-ttu-id="48c74-181">Dieses Cmdlet gibt ein **computerchangeinfo** -Objekt zurück, wenn Sie den **passthru** -Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="48c74-181">This cmdlet returns a **ComputerChangeInfo** object, if you specify the **PassThru** parameter.</span></span>
<span data-ttu-id="48c74-182">Andernfalls wird keine Ausgabe zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="48c74-182">Otherwise, it does not return any output.</span></span>

## <span data-ttu-id="48c74-183">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="48c74-183">NOTES</span></span>

## <span data-ttu-id="48c74-184">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="48c74-184">RELATED LINKS</span></span>

[<span data-ttu-id="48c74-185">Restart-Computer</span><span class="sxs-lookup"><span data-stu-id="48c74-185">Restart-Computer</span></span>](Restart-Computer.md)

[<span data-ttu-id="48c74-186">Stop-Computer</span><span class="sxs-lookup"><span data-stu-id="48c74-186">Stop-Computer</span></span>](Stop-Computer.md)