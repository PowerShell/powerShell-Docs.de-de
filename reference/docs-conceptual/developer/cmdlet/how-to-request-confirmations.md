---
ms.date: 09/13/2016
ms.topic: reference
title: Anfordern von Bestätigungen
description: Anfordern von Bestätigungen
ms.openlocfilehash: 3e29803407bd9fbf13e6db0d0a02239c34e9c4fa
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666993"
---
# <a name="how-to-request-confirmations"></a>Anfordern von Bestätigungen

In diesem Beispiel wird gezeigt, wie die Methoden [System. Management. Automation. Cmdlet. Schulter dprocess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) und [System. Management. Automation. Cmdlet. undcontinue aufgerufen werden](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) , um Bestätigungen des Benutzers anzufordern, bevor eine Aktion durchgeführt wird.

> [!IMPORTANT]
> Weitere Informationen dazu, wie diese Anforderungen von Windows PowerShell verarbeitet werden, finden Sie unter [Anfordern einer Bestätigung](./requesting-confirmation-from-cmdlets.md).

## <a name="to-request-confirmation"></a>Zum Anfordern einer Bestätigung

1. Stellen Sie sicher, dass der- `SupportsShouldProcess` Parameter des Cmdlet-Attributs auf festgelegt ist `true` . (Für Functions handelt es sich hierbei um einen Parameter des cmdletbinding-Attributs.)

    ```csharp
    [Cmdlet(VerbsDiagnostic.Test, "RequestConfirmationTemplate1",
            SupportsShouldProcess = true)]
    ```

2. Fügen Sie dem `Force` Cmdlet einen Parameter hinzu, damit der Benutzer eine Bestätigungs Anforderung außer Kraft setzen kann.

    ```csharp
    [Parameter()]
    public SwitchParameter Force
    {
      get { return force; }
      set { force = value; }
    }
    private bool force;
    ```

3. Fügen Sie eine- `if` Anweisung hinzu, die den Rückgabewert der [System. Management. Automation. Cmdlet. undprocess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) -Methode verwendet, um zu bestimmen, ob die [System. Management. Automation. Cmdlet. Schulter dcontinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) -Methode aufgerufen wird.

4. Fügen Sie eine zweite `if` Anweisung hinzu, die den Rückgabewert der [System. Management. Automation. Cmdlet. dendcontinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) -Methode und den Wert des- `Force` Parameters verwendet, um zu bestimmen, ob der Vorgang ausgeführt werden soll.

## <a name="example"></a>Beispiel

Im folgenden Codebeispiel werden die Methoden " [System. Management. Automation. Cmdlet. Schulter dprocess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) " und " [System. Management. Automation. Cmdlet. daudcontinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) " innerhalb der Überschreibung der [System. Management. Automation. Cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) -Methode aufgerufen. Sie können diese Methoden jedoch auch aus den anderen Eingabe Verarbeitungsmethoden aufzurufen.

```csharp
protected override void ProcessRecord()
{
  if (ShouldProcess("ShouldProcess target"))
  {
    if (Force || ShouldContinue("", ""))
    {
      // Add code that performs the operation.
    }
  }
}
```

## <a name="see-also"></a>Weitere Informationen

[Schreiben eines Windows PowerShell-Cmdlets](./writing-a-windows-powershell-cmdlet.md)
