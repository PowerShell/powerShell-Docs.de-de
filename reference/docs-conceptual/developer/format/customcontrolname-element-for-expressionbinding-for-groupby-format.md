---
ms.date: 09/13/2016
ms.topic: reference
title: Element „CustomControlName“ für ExpressionBinding für GroupBy (Format)
description: Element „CustomControlName“ für ExpressionBinding für GroupBy (Format)
ms.openlocfilehash: bb7dbd449137628da1794628c5a7d7e10158dd46
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655431"
---
# <a name="customcontrolname-element-for-expressionbinding-for-groupby-format"></a>Element „CustomControlName“ für ExpressionBinding für GroupBy (Format)

Gibt den Namen eines allgemeinen Steuer Elements oder eines Ansichts Steuer Elements an. Dieses Element wird verwendet, wenn definiert wird, wie eine neue Gruppe von Objekten angezeigt wird.

Konfigurationselement (Format) viewdefinitions-Element (Format) Ansichts Element (Format) GroupBy-Element für View (Format) CustomControl-Element für GroupBy (Format) customentries-Element für CustomControl für GroupBy (Format) customentry-Element für CustomControl für GroupBy (Format) customItem-Element für customentry für GroupBy (Format) ExpressionBinding-Element für customItem für GroupBy (Format) customcontrolname-Element für ExpressionBinding für GroupBy (Format)

## <a name="syntax"></a>Syntax

```xml
<CustomControlName>NameofCustomControl</CustomControlName>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `CustomControlName` Elements beschrieben.

### <a name="attributes"></a>Attribute

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

Keine

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Element „ExpressionBinding“ für CustomItem für GroupBy (Format)](./expressionbinding-element-for-customitem-for-groupby-format.md)|Definiert die Daten, die vom-Steuerelement angezeigt werden.|

## <a name="text-value"></a>Textwert

Geben Sie den Namen des Steuer Elements an.

## <a name="remarks"></a>Bemerkungen

Sie können allgemeine Steuerelemente erstellen, die von allen Ansichten einer Formatierungs Datei verwendet werden können, und Sie können Ansichts Steuerelemente erstellen, die von einer bestimmten Ansicht verwendet werden können. Die folgenden Elemente geben die Namen dieser Steuerelemente an:

- [Element „Name“ für Control für Controls für Configuration (Format)](./name-element-for-control-for-controls-for-configuration-format.md)

- [Element „Name“ für Control für Controls für View (Format)](./name-element-for-control-for-controls-for-view-format.md)

## <a name="see-also"></a>Weitere Informationen

[Element „Name“ für Control für Controls für Configuration (Format)](./name-element-for-control-for-controls-for-configuration-format.md)

[Element „Name“ für Control für Controls für View (Format)](./name-element-for-control-for-controls-for-view-format.md)

[Element „ExpressionBinding“ für CustomItem für GroupBy (Format)](./expressionbinding-element-for-customitem-for-groupby-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
