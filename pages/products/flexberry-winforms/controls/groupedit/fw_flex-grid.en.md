---
title: FlexGrid
sidebar: flexberry-winforms_sidebar
keywords: Windows UI (Контролы)
summary: Описание FlexGrid и пример получения из Gr
toc: true
permalink: en/fw_flex-grid.html
folder: products/flexberry-winforms/
lang: en
---

## Описание
[FlexGrid](http://www.componentone.com/SuperProducts/FlexGridWinForms/) - простой в использовании контрол-таблица от компании ComponentOne. Позволяет отображать, редактировать, форматировать, организовывать и печатать данные в виде таблицы.

Контрол используется в [GroupEdit](fw_group-edit.html), [ObjectListView](fw_objectlistview.html), а также в Статиторе.


## Документация
Документацию можно найти на официальном сайте компонента.

## Получение FlexGrid из GroupEdit

```csharp
public static C1.Win.C1FlexGrid.C1FlexGrid GetGridFromGE(ICSSoft.STORMNET.Windows.Forms.GroupEditBase groupEdit)
// Ищем FlexGrid 
{
 for(int i =0; i < groupEdit.Controls.Count;i++)
 {
  if (groupEdit.Controls[i] is System.Windows.Forms.GroupBox)
  {
   for(int j =0; j < groupEdit.Controls[i].Controls.Count;j++)
   {
    if (groupEdit.Controls[i].Controls[j] is C1.Win.C1FlexGrid.C1FlexGrid)
    {
     return (C1.Win.C1FlexGrid.C1FlexGrid)groupEdit.Controls[i].Controls[j];
    }
   }
  }
 }
 return null;
}
```
