---
ms.date: 07/16/2020
ms.topic: reference
title: DSC-Ressource „WindowsOptionalFeatureSet“
description: DSC-Ressource „WindowsOptionalFeatureSet“
ms.openlocfilehash: f72cc27bfc8847d2c87cfb289f3e2c729a21d1f4
ms.sourcegitcommit: 196c7f8cd24560cac70c88acc89909f17a86aea9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2020
ms.locfileid: "93143040"
---
# <a name="dsc-windowsoptionalfeatureset-resource"></a>DSC-Ressource „WindowsOptionalFeatureSet“

> Gilt für: Windows PowerShell 5.x

Die Ressource **WindowsOptionalFeatureSet** in Windows PowerShell DSC (Desired State Configuration) bietet einen Mechanismus, um sicherzustellen, dass optionale Features auf einem Zielknoten aktiviert werden. Diese Ressource ist eine [zusammengesetzte Ressource](../../../resources/authoringResourceComposite.md), die die Ressource [WindowsOptionalFeature](windowsOptionalFeatureResource.md) für jedes Feature aufruft, das in der **Name** -Eigenschaft angegeben ist.

Verwenden Sie diese Ressource, wenn Sie verschiedene optionale Windows-Features mit demselben Status konfigurieren möchten.

[!INCLUDE [Updated DSC Resources](../../../../../includes/dsc-resources.md)]

## <a name="syntax"></a>Syntax

```Syntax
WindowsOptionalFeatureSet [string] #ResourceName
{
    Name = [string[]]
    [ RemoveFilesOnDisable = [bool] ]
    [ LogPath = [string] ]
    [ NoWindowsUpdateCheck = [bool] ]
    [ LogLevel = [string] { ErrorsOnly | ErrorsAndWarning | ErrorsAndWarningAndInformation }  ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Enable | Disable }  ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a>Eigenschaften

|Eigenschaft |BESCHREIBUNG |
|---|---|
|Name |Gibt den Namen der Features an, die aktiviert oder deaktiviert werden sollen. |
|NoWindowsUpdateCheck |Gibt an, ob Windows Update (WU) von DISM kontaktiert wird, wenn die Quelldateien zum Aktivieren von Features gesucht werden. Falls `$true`, wird WU nicht von DISM kontaktiert. |
|RemoveFilesOnDisable |Legen Sie diese Einstellung auf `$true` fest, um alle zu den Features gehörigen Dateien zu entfernen, wenn **Ensure** auf **Absent** festgelegt wird. |
|LogLevel |Die maximale Ausgabeebene, die in den Protokollen angezeigt wird. Zulässige Werte: **ErrorsOnly** , **ErrorsAndWarning** und **ErrorsAndWarningAndInformation** . |
|LogPath |Der Pfad zu einer Protokolldatei, in der der Ressourcenanbieter den Vorgang protokollieren soll. |

## <a name="common-properties"></a>Allgemeine Eigenschaften

|Eigenschaft |BESCHREIBUNG |
|---|---|
|DependsOn |Gibt an, dass die Konfiguration einer anderen Ressource ausgeführt werden muss, bevor diese Ressource konfiguriert wird. Wenn beispielsweise die ID des Skriptblocks mit der Ressourcenkonfiguration, den Sie zuerst ausführen möchten, „ResourceName“ und dessen Typ „ResourceType“ ist, lautet die Syntax für das Verwenden dieser Eigenschaft `DependsOn = "[ResourceType]ResourceName"`. |
|Ensure |Gibt an, ob die Features aktiviert sind. Um sicherzustellen, dass die Features aktiviert sind, legen Sie diese Eigenschaft auf **Enable** fest. Um sicherzustellen, dass die Features deaktiviert sind, legen Sie die Eigenschaft auf **Disable** fest. Der Standardwert ist **Enable** . |
|PsDscRunAsCredential |Legt die Anmeldeinformationen für die Ausführung der gesamten Ressource fest. |

> [!NOTE]
> Die allgemeine Eigenschaft **PsDscRunAsCredential** wurde in WMF 5.0 hinzugefügt, um das Ausführen einer beliebigen DSC-Ressource in Verbindung mit anderen Anmeldeinformationen zu ermöglichen. Weitere Informationen finden Sie unter [Use Credentials with DSC Resources](../../../configurations/runasuser.md) (Verwenden von Anmeldeinformationen mit DSC-Ressourcen).
