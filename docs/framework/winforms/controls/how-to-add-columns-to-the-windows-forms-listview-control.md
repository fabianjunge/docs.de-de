---
title: 'Vorgehensweise: Hinzufügen von Spalten zu dem ListView-Steuerelement in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView control [Windows Forms], adding column headers
- columns [Windows Forms], adding to ListView controls
- list views [Windows Forms], adding columns
ms.assetid: 79174274-12ee-4a5d-80db-6ec02976d010
ms.openlocfilehash: eed032ec0bacd50666c30979b33362dabf00d565
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54700194"
---
# <a name="how-to-add-columns-to-the-windows-forms-listview-control"></a>Vorgehensweise: Hinzufügen von Spalten zu dem ListView-Steuerelement in Windows Forms
In der Detailansicht der <xref:System.Windows.Forms.ListView> Steuerelement kann mehrere Spalten für jedes Listenelement anzeigen. Sie können die Spalten verwenden, um dem Benutzer verschiedene Arten von Informationen zu jedem Listenelement anzuzeigen. Beispielsweise kann eine Liste der Dateien angezeigt, der Dateiname, Typ, Größe und Datum, an der letzten der Datei Änderung. Informationen zum Auffüllen der Spalten, nachdem sie erstellt wurden, finden Sie unter [Vorgehensweise: Anzeigen von Unterelementen in Spalten mit dem Windows Forms-ListView-Steuerelement](../../../../docs/framework/winforms/controls/how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md).  
  
### <a name="to-add-columns-programmatically"></a>Das programmgesteuerte Hinzufügen von Spalten  
  
1.  Legen Sie die <xref:System.Windows.Forms.ListView.View%2A> Eigenschaft <xref:System.Windows.Forms.View.Details>.  
  
2.  Verwenden der <xref:System.Windows.Forms.ListView.ColumnHeaderCollection.Add%2A> Methode der Listenansicht <xref:System.Windows.Forms.ListView.Columns%2A> Eigenschaft.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#31)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#31)]  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Forms.ListView>
- [ListView-Steuerelement](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)
- [Übersicht über das ListView-Steuerelement](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)
