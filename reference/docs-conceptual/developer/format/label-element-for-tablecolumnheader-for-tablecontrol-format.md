---
ms.date: 09/13/2016
ms.topic: reference
title: Element „Label“ für TableColumnHeader für TableControl (Format)
description: Element „Label“ für TableColumnHeader für TableControl (Format)
ms.openlocfilehash: fe4c209903c04e683b44e2bdcbf381adb6874ace
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667792"
---
# <a name="label-element-for-tablecolumnheader-for-tablecontrol-format"></a>Element „Label“ für TableColumnHeader für TableControl (Format)

Definiert die Bezeichnung, die oben in einer Spalte angezeigt wird. Dieses Element wird verwendet, wenn eine Tabellen Sicht definiert wird.

Configuration-Element (Format) viewdefinitions-Element (Format) View-Element (Format) tablecontrol-Element (Format) tableHeaders-Element für tablecontrol (Format) tablecolumnheader-Element für tableHeaders für tablecontrol (Format) Label-Element für tablecolumnheader für tablecontrol (Format)

## <a name="syntax"></a>Syntax

```xml
<Label>DisplayedLabel</Label>

```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden die Attribute, untergeordneten Elemente und das übergeordnete Element des- `Label` Elements beschrieben. Für jede Spalte ist nur eine Bezeichnung zulässig.

### <a name="attributes"></a>Attribute

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

Keine

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Tablecolumnheader-Element für tableHeaders für tablecontrol (Format)](./tablecolumnheader-element-format.md)|Definiert eine Bezeichnung, die Breite und die Ausrichtung der Daten für eine Spalte der Tabelle.|

## <a name="text-value"></a>Textwert

Geben Sie den Text an, der oben in der Spalte der Tabelle angezeigt wird. Es sind keine eingeschränkten Zeichen für die Spalten Bezeichnung vorhanden.

## <a name="remarks"></a>Bemerkungen

Wenn keine Bezeichnung angegeben ist, wird der Name der Eigenschaft verwendet, deren Wert in den Zeilen angezeigt wird.

Weitere Informationen zu den Komponenten einer Tabellenansicht finden Sie unter [Erstellen einer Tabellen Sicht](./creating-a-table-view.md).

## <a name="example"></a>Beispiel

Dieses Beispiel zeigt ein- `TableColumnHeader` Element, dessen Bezeichnung "Column 1" ist.

```xml
<TableColumnHeader>
  <Label>Column 1</Label)
  <Width>16</Width>
  <Alignment>Left</Alignment>
</TableColumnHeader>
```

## <a name="see-also"></a>Weitere Informationen

[Erstellen einer Tabellenansicht](./creating-a-table-view.md)

[Element „TableColumnHeader“ (Format)](./tablecolumnheader-element-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
