---
ms.date: 09/13/2016
ms.topic: reference
title: Beispiele für Windows PowerShell-APIs
description: Beispiele für Windows PowerShell-APIs
ms.openlocfilehash: b6336ae7a2abb98cbbaa69bf6c9455f893db2d94
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92657543"
---
# <a name="windows-powershell-api-samples"></a>Beispiele für Windows PowerShell-APIs

Dieser Abschnitt enthält Beispielcode, der zeigt, wie Sie Runspaces erstellen, die die Funktionalität einschränken, und wie Sie Befehle asynchron ausführen, indem Sie einen Runspace-Pool verwenden, um die Runspaces bereitzustellen. Mit Microsoft Visual Studio können Sie eine Konsolenanwendung erstellen und dann den Code aus den Themen in diesem Abschnitt in die Host Anwendung kopieren.

## <a name="in-this-section"></a>In diesem Abschnitt

[PowerShell01-Beispiel](./windows-powershell01-sample.md) In diesem Beispiel wird gezeigt, wie ein [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) -Objekt verwendet wird, um die Funktionalität eines Runspace einzuschränken. In der Ausgabe dieses Beispiels wird veranschaulicht, wie der Sprachmodus des Runspace eingeschränkt wird, wie ein Cmdlet als privat markiert wird, wie Cmdlets und Anbieter hinzugefügt und entfernt werden, wie ein Proxy Befehl hinzugefügt wird und vieles mehr.

[PowerShell02-Beispiel](./windows-powershell02-sample.md) In diesem Beispiel wird gezeigt, wie Befehle asynchron mit den Runspaces eines Runspace-Pools ausgeführt werden. Das Beispiel generiert eine Liste mit Befehlen und führt diese Befehle aus, während die Windows PowerShell-Engine einen Runspace aus dem Pool öffnet, wenn Sie benötigt wird.
