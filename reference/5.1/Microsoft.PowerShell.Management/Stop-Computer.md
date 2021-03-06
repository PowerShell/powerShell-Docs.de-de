---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 12/11/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/stop-computer?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-Computer
ms.openlocfilehash: 8062210aa94cb46d5e5557ede1bac672cae39622
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2020
ms.locfileid: "93218255"
---
# Stop-Computer

## ZUSAMMENFASSUNG
Beendet den lokalen Computer und Remotecomputer (fährt sie herunter).

## SYNTAX

### Alle

```
Stop-Computer [-AsJob] [-DcomAuthentication <AuthenticationLevel>] [-WsmanAuthentication <String>]
 [-Protocol <String>] [[-ComputerName] <String[]>] [[-Credential] <PSCredential>]
 [-Impersonation <ImpersonationLevel>] [-ThrottleLimit <Int32>] [-Force] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION

Mit dem `Stop-Computer` -Cmdlet werden der lokale Computer und Remote Computer heruntergefahren.

Mit den Parametern von können Sie `Stop-Computer` die Vorgänge zum Herunterfahren als Hintergrund Auftrag ausführen, die Authentifizierungs Ebenen und Alternative Anmelde Informationen angeben, die gleichzeitigen Verbindungen einschränken, die zum Ausführen des Befehls erstellt werden, und ein sofortiges Herunterfahren erzwingen.

Für dieses Cmdlet ist PowerShell-Remoting nur erforderlich, wenn Sie den **AsJob** -Parameter verwenden.

## BEISPIELE

### Beispiel 1: Herunterfahren des lokalen Computers

In diesem Beispiel wird der lokale Computer heruntergefahren.

```powershell
Stop-Computer -ComputerName localhost
```

### Beispiel 2: Herunterfahren von zwei Remote Computern und dem lokalen Computer

In diesem Beispiel werden zwei Remote Computer und der lokale Computer angehalten.

```powershell
Stop-Computer -ComputerName "Server01", "Server02", "localhost"
```

`Stop-Computer` verwendet den **Computername** -Parameter, um zwei Remote Computer und den lokalen Computer anzugeben. Jeder Computer wird heruntergefahren.

### Beispiel 3: Herunterfahren von Remote Computern als Hintergrund Auftrag

In diesem Beispiel wird `Stop-Computer` als Hintergrund Auftrag auf zwei Remote Computern ausgeführt.

```powershell
$j = Stop-Computer -ComputerName "Server01", "Server02" -AsJob
$results = $j | Receive-Job
$results
```

`Stop-Computer` verwendet den **Computername** -Parameter, um zwei Remote Computer anzugeben. Der **AsJob** -Parameter führt den Befehl als Hintergrund Auftrag aus. Die Auftrags Objekte werden in der `$j` Variablen gespeichert.

Die Auftrags Objekte in der `$j` Variablen werden an die Pipeline gesendet `Receive-Job` , die die Auftrags Ergebnisse abruft. Die-Objekte werden in der- `$results` Variable gespeichert. Die `$results` Variable zeigt die Auftrags Informationen in der PowerShell-Konsole an.

Da **AsJob** den Auftrag auf dem lokalen Computer erstellt und die Ergebnisse automatisch an den lokalen Computer zurückgibt, können Sie ihn `Receive-Job` als lokalen Befehl ausführen.

### Beispiel 4: Herunterfahren eines Remote Computers

In diesem Beispiel wird ein Remote Computer mithilfe der angegebenen Authentifizierung heruntergefahren.

```powershell
Stop-Computer -ComputerName "Server01" -Impersonation Anonymous -DcomAuthentication PacketIntegrity
```

`Stop-Computer` verwendet den **Computername** -Parameter, um den Remote Computer anzugeben. Der Identitätswechsel Parameter gibt einen angepassten Identitätswechsel an, und der **dcomauthentication** **-Parameter gibt** Einstellungen auf Authentifizierungs Ebene an.

### Beispiel 5: Herunterfahren von Computern in einer Domäne

In diesem Beispiel erzwingen die Befehle ein sofortiges Herunterfahren aller Computer in einer angegebenen Domäne.

```powershell
$s = Get-Content -Path ./Domain01.txt
$c = Get-Credential -Credential Domain01\Admin01
Stop-Computer -ComputerName $s -Force -ThrottleLimit 10 -Credential $c
```

`Get-Content` verwendet den **path** -Parameter, um eine Datei im aktuellen Verzeichnis mit der Liste der Domänen Computer zu erhalten. Die-Objekte werden in der- `$s` Variable gespeichert.

`Get-Credential` verwendet den **Credential** -Parameter, um die Anmelde Informationen eines Domänen Administrators anzugeben. Die Anmelde Informationen werden in der `$c` Variablen gespeichert.

`Stop-Computer` fährt die Computer herunter, die mit der Liste der Computer des Computer **Name** -Parameters in der Variablen angegeben werden `$s` . Der **Force** -Parameter erzwingt ein sofortiges Herunterfahren. Der **throttlelimit** -Parameter schränkt den Befehl auf 10 gleichzeitige Verbindungen ein. Mit dem **Credential** -Parameter werden die in der Variablen gespeicherten Anmelde Informationen übermittelt `$c` .

## PARAMETERS

### -AsJob

Gibt an, dass dieses Cmdlet als Hintergrund Auftrag ausgeführt wird.

Um diesen Parameter verwenden zu können, müssen die lokalen Computer und Remote Computer für Remoting konfiguriert sein. unter Windows Vista und höheren Versionen des Windows-Betriebssystems müssen Sie PowerShell mit der Option **als Administrator ausführen** öffnen. Weitere Informationen finden Sie unter [about_Remote_Requirements](..//microsoft.powershell.core/about/about_remote_requirements.md).

Wenn Sie den **AsJob** -Parameter angeben, gibt der Befehl sofort ein Objekt zurück, das den Hintergrund Auftrag darstellt. Sie können die Sitzung weiterhin verwenden, während der Auftrag abgeschlossen wird. Der Auftrag wird auf dem lokalen Computer erstellt, und die Ergebnisse von Remotecomputern werden automatisch an den lokalen Computer zurückgegeben. Um die Auftragsergebnisse abzurufen, verwenden Sie das Cmdlet `Receive-Job`.

Weitere Informationen zu PowerShell-Hintergrund Aufträgen finden Sie unter [about_Jobs](..//microsoft.powershell.core/about/about_jobs.md) und [about_Remote_Jobs](../microsoft.powershell.core/about/about_remote_jobs.md).

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName

Gibt die zu stoppenden Computer an. Die Standardeinstellung ist der lokale Computer.

Geben Sie den NetBIOS-Namen, die IP-Adresse oder den vollqualifizierten Domänennamen eines Computers oder mehrerer Computer in einer durch Trennzeichen getrennten Liste ein. Geben Sie den Computernamen oder localhost ein, um den lokalen Computer anzugeben.

Dieser Parameter beruht nicht auf PowerShell-Remoting. Sie können den **Computername** -Parameter auch dann verwenden, wenn der Computer nicht für das Ausführen von Remote Befehlen konfiguriert ist.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: CN, __SERVER, Server, IPAddress

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Confirm

Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.

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

### -Credential

Gibt ein Benutzerkonto an, das über die Berechtigung zum Ausführen dieser Aktion verfügt. Der Standardwert ist der aktuelle Benutzer.

Geben Sie einen Benutzernamen ein, z. b. **USER01** oder **Domain01\User01** , oder geben Sie ein **PSCredential** -Objekt ein, das vom `Get-Credential` Cmdlet generiert wurde. Wenn Sie einen Benutzernamen eingeben, werden Sie zur Eingabe des Kennworts aufgefordert.

Anmelde Informationen werden in einem [PSCredential](/dotnet/api/system.management.automation.pscredential) -Objekt gespeichert, und das Kennwort wird als [SecureString](/dotnet/api/system.security.securestring)gespeichert.

> [!NOTE]
> Weitere Informationen zum Schutz von **SecureString** -Daten finden Sie unter [wie sicher ist SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### -Dcomauthentication

Gibt die Authentifizierungs Ebene an, die dieses Cmdlet mit WMI verwendet. `Stop-Computer` verwendet WMI. Der Standardwert ist " **Paket** ".

Zulässige Werte für diesen Parameter:

- **Standard** : Windows-Authentifizierung.
- **None** : keine com-Authentifizierung.
- **Connect** : com-Authentifizierung auf Verbindungs Ebene.
- **Aufzurufen** : com-Authentifizierung auf Aufrufebene.
- **Paket** : com-Authentifizierung auf Paketebene.
- **Packetintegrity** : com-Authentifizierung auf Paket Integritäts Ebene.
- **PacketPrivacy** : com-Authentifizierung auf Paketdaten Schutz Ebene.
- **Unverändert** : identisch mit dem vorherigen Befehl.

Weitere Informationen zu den Werten dieses Parameters finden Sie unter [AuthenticationLevel](/dotnet/api/system.management.authenticationlevel).

```yaml
Type: System.Management.AuthenticationLevel
Parameter Sets: (All)
Aliases: Authentication
Accepted values: Default, None, Connect, Call, Packet, PacketIntegrity, PacketPrivacy, Unchanged

Required: False
Position: Named
Default value: Packet
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

Erzwingt ein sofortiges Herunterfahren des Computers.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Identitätswechsel

Gibt die Identitätswechsel Ebene an, die verwendet werden soll, wenn dieses Cmdlet WMI aufruft. Der Standard **Wert ist "** Identitätswechsel".

`Stop-Computer` verwendet WMI. Zulässige Werte für diesen Parameter:

- **Standard** : Standard Identitätswechsel.
- **Anonymous** : Blendet die Identität des Aufrufers aus.
- **Identifizieren** : ermöglicht es Objekten, die Anmelde Informationen des Aufrufers abzufragen.
- Identität **annehmen: ermöglicht** es Objekten, die Anmelde Informationen des Aufrufers zu verwenden.

```yaml
Type: System.Management.ImpersonationLevel
Parameter Sets: (All)
Aliases:
Accepted values: Default, Anonymous, Identify, Impersonate, Delegate

Required: False
Position: Named
Default value: Impersonate
Accept pipeline input: False
Accept wildcard characters: False
```

### -Protocol

Gibt an, welches Protokoll zum Neustarten der Computer verwendet werden soll. Die zulässigen Werte für diesen Parameter sind: **WSMAN** und **DCOM**. Der Standardwert ist **DCOM**.

Dieser Parameter wurde in PowerShell 3,0 eingeführt.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: DCOM, WSMan

Required: False
Position: Named
Default value: DCOM
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit

Gibt die maximale Anzahl von gleichzeitigen Verbindungen an, die zum Ausführen dieses Befehls hergestellt werden können.
Wenn Sie diesen Parameter weglassen oder den Wert %%amp;quot;0%%amp;quot; eingeben, wird der Standardwert %%amp;quot;32%%amp;quot; verwendet.

Die Drosselungsgrenze gilt nur für den aktuellen Befehl und nicht für die Sitzung oder den Computer.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Wsmanauthentication

Gibt den Mechanismus an, der verwendet wird, um die Benutzer Anmelde Informationen zu authentifizieren, wenn dieses Cmdlet das WSMAN-Protokoll verwendet. Der Standardwert lautet **Default**.

Zulässige Werte für diesen Parameter:

- Basic
- CredSSP
- Standard
- Digest
- Kerberos
- Negotiate

Weitere Informationen zu den Werten dieses Parameters finden Sie unter [authenticationmechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).

> [!CAUTION]
> Die Authentifizierung des Anmelde Informations Diensts (Credential Security Service Provider, kredssp), in der die Benutzer Anmelde Informationen an einen Remote Computer übergeben werden, der authentifiziert werden soll, wurde für Befehle entworfen, die eine Authentifizierung auf mehreren Ressourcen erfordern Dieser Mechanismus erhöht das Sicherheitsrisiko des Remotevorgangs. Wenn die Sicherheit des Remotecomputers gefährdet ist, können die an ihn übergebenen Anmeldeinformationen zum Steuern der Netzwerksitzung verwendet werden.

Dieser Parameter wurde in PowerShell 3,0 eingeführt.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Default, Basic, Negotiate, CredSSP, Digest, Kerberos

Required: False
Position: Named
Default value: Default
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird. Das Cmdlet wird nicht ausgeführt.

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

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### Keine

Eingaben können nicht an dieses Cmdlet übergeben werden.

## AUSGABEN

### None oder System. Management. Automation. remotingjob

Das-Cmdlet gibt ein **System. Management. Automation. remotingjob** -Objekt zurück, wenn Sie den **AsJob** -Parameter angeben. Andernfalls wird keine Ausgabe generiert.

## HINWEISE

Dieses Cmdlet verwendet die **Win32Shutdown** -Methode der WMI-Klasse **Win32_OperatingSystem** . Diese Methode erfordert, dass die **SeShutdownPrivilege** -Berechtigung für das Benutzerkonto aktiviert ist, mit dem der Computer neu gestartet wird.

## VERWANDTE LINKS

[Add-Computer](Add-Computer.md)

[Checkpoint-Computer](Checkpoint-Computer.md)

[Remove-Computer](Remove-Computer.md)

[Rename-Computer](Rename-Computer.md)

[Restart-Computer](Restart-Computer.md)

[Restore-Computer](Restore-Computer.md)

[Test-Connection](Test-Connection.md)
