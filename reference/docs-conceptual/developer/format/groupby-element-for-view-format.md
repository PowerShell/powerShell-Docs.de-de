---
ms.date: 09/13/2016
ms.topic: reference
title: Element „GroupBy“ für View (Format)
description: Element „GroupBy“ für View (Format)
ms.openlocfilehash: d8ca93a3b2c1490928885579919c07f5eb274cd8
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652106"
---
# <a name="groupby-element-for-view-format"></a>Element „GroupBy“ für View (Format)

Definiert, wie eine neue Gruppe von Objekten angezeigt wird. Dieses Element wird verwendet, wenn eine Tabelle, eine Liste, eine Breite oder eine benutzerdefinierte Steuerelement Ansicht definiert wird.

Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) GroupBy-Element für Ansicht (Format)

## <a name="syntax"></a>Syntax

```xml
<GroupBy>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
  <Label>TextToDisplay</Label>
  <CustomControl>...</CustomControl>
  <CustomControlName>NameOfControl</CustomControlName>
</GroupBy>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.

### <a name="attributes"></a>Attribute

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Element „CustomControl“ für GroupBy (Format)](./customcontrol-element-for-groupby-format.md)|Optionales Element.<br /><br /> Definiert das benutzerdefinierte Steuerelement, das neue Gruppen anzeigt.|
|[Element „CustomControlName“ für GroupBy (Format)](./customcontrolname-element-for-groupby-format.md)|Optionales Element.<br /><br /> Gibt den Namen eines Steuer Elements an, das zum Anzeigen der neuen Gruppe verwendet wird.|
|[Element „Label“ für GroupBy (Format)](./label-element-for-groupby-format.md)|Optionales Element.<br /><br /> Gibt eine Bezeichnung an, die beim Auftreten einer neuen Gruppe angezeigt wird.|
|[Element „PropertyName“ für GroupBy (Format)](./propertyname-element-for-groupby-format.md)|Optionales Element.<br /><br /> Gibt an, dass die .net-Eigenschaft eine neue Gruppe startet, wenn sich der Wert ändert.|
|[Element „ScriptBlock“ für GroupBy (Format)](./scriptblock-element-for-groupby-format.md)|Optionales Element.<br /><br /> Gibt das Skript an, das eine neue Gruppe startet, wenn sich der Wert ändert.|

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Element „View“ (Format)](./view-element-format.md)|Definiert eine Ansicht, in der ein oder mehrere .NET-Objekte angezeigt werden.|

## <a name="remarks"></a>Bemerkungen

Wenn Sie definieren, wie eine neue Gruppe von Objekten angezeigt wird, müssen Sie die Eigenschaft oder das Skript angeben, mit der die neue Gruppe gestartet wird. Es ist jedoch nicht möglich, beides anzugeben.

## <a name="see-also"></a>Weitere Informationen

[Element „CustomControlName“ für GroupBy (Format)](./customcontrolname-element-for-groupby-format.md)

[Element „Label“ für GroupBy (Format)](./label-element-for-groupby-format.md)

[Element „PropertyName“ für GroupBy (Format)](./propertyname-element-for-groupby-format.md)

[Element „ScriptBlock“ für GroupBy (Format)](./scriptblock-element-for-groupby-format.md)

[Element „View“ (Format)](./view-element-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
