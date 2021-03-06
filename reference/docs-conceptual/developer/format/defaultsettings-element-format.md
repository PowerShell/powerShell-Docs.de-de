---
ms.date: 09/13/2016
ms.topic: reference
title: Element „DefaultSettings“ (Format)
description: Element „DefaultSettings“ (Format)
ms.openlocfilehash: 1c2055b38a416fe2d75fa20c6c87e92d9eed4285
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666721"
---
# <a name="defaultsettings-element-format"></a>Element „DefaultSettings“ (Format)

Definiert allgemeine Einstellungen, die für alle Sichten der Formatierungs Datei gelten. Zu den allgemeinen Einstellungen gehören das Anzeigen von Fehlern, das umschließen von Text in Tabellen, das Definieren der Erweiterung von Sammlungen und vieles mehr.

Configuration-Element (Format) DefaultSettings-Element (Format)

## <a name="syntax"></a>Syntax

```xml
<DefaultSettings>
  <ShowError/>
  <DisplayError/>
 <PropertyCountForTable>NumberOfProperties</PropertyCountFortable>
  <WrapTables/>
  <EnumerableExpansions>...</EnumerableExpansions>
</DefaultSettings>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `DefaultSettings` Elements beschrieben.

### <a name="attributes"></a>Attribute

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Element „DisplayError“ (Format)](./displayerror-element-format.md)|Optionales Element.<br /><br /> Gibt an, dass die Zeichenfolge #Err angezeigt wird, wenn ein Fehler auftritt, während ein Datenelement angezeigt wird.|
|[Element „EnumerableExpansions“ (Format)](./enumerableexpansions-element-format.md)|Optionales Element.<br /><br /> Definiert die verschiedenen Möglichkeiten, wie .NET-Objekte erweitert werden, wenn Sie in einer Ansicht angezeigt werden.|
|[PropertyCountForTable (Format)](./propertycountfortable-element-format.md)|Optionales Element.<br /><br /> Gibt die Mindestanzahl von Eigenschaften an, die ein Objekt besitzen muss, um das Objekt in einer Tabellenansicht anzuzeigen.|
|[Element „ShowError“ (Format)](./showerror-element-format.md)|Optionales Element.<br /><br /> Gibt an, dass der vollständige Fehler Daten Satz angezeigt wird, wenn ein Fehler auftritt, während ein Datenelement angezeigt wird.|
|[Element „WrapTables“ (Format)](./wraptables-element-format.md)|Optionales Element.<br /><br /> Gibt an, dass Daten in einer Tabelle in die nächste Zeile verschoben werden, wenn Sie nicht in die Spaltenbreite passt.|

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Configuration-Element](./configuration-element-format.md)|Stellt das Element der obersten Ebene einer Formatierungs Datei dar.|

## <a name="remarks"></a>Bemerkungen

## <a name="see-also"></a>Weitere Informationen

[Konfigurationselement](./configuration-element-format.md)

[Element „DisplayError“ (Format)](./displayerror-element-format.md)

[Element „EnumerableExpansions“ (Format)](./enumerableexpansions-element-format.md)

[PropertyCountForTable (Format)](./propertycountfortable-element-format.md)

[Element „ShowError“ (Format)](./showerror-element-format.md)

[Element „WrapTables“ (Format)](./wraptables-element-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
