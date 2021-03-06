---
title: 'Vorgehensweise: Richten Sie automatische Zusammenführen von Menüs für MDI-Anwendungen'
ms.date: 03/30/2017
helpviewer_keywords:
- MenuStrip [Windows Forms], merging
- Merging [Windows Forms], automatic menu
ms.assetid: 55e32cad-1141-4a56-aa33-d9543ca3d393
ms.openlocfilehash: 3aeaf9ee4818b6689905c10d2bd46fc887609c35
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54549823"
---
# <a name="how-to-set-up-automatic-menu-merging-for-mdi-applications"></a>Vorgehensweise: Richten Sie automatische Zusammenführen von Menüs für MDI-Anwendungen
Das folgende Verfahren bietet die grundlegenden Schritte zum Einrichten der automatischen Zusammenführen in einer Anwendung Multiple Document Interface (MDI) mit <xref:System.Windows.Forms.MenuStrip>.  
  
### <a name="to-set-up-automatic-menu-merging"></a>Zum Einrichten des automatischem Zusammenführens von  
  
1.  Erstellen von übergeordneten MDI-Formulars durch Festlegen seiner <xref:System.Windows.Forms.Form.IsMdiContainer%2A> Eigenschaft `true`.  
  
2.  Hinzufügen einer <xref:System.Windows.Forms.MenuStrip> zum übergeordneten MDI-Fensters, Festlegen der <xref:System.Windows.Forms.Form.MainMenuStrip%2A> Eigenschaft mit dem <xref:System.Windows.Forms.MenuStrip>.  
  
3.  Erstellen Sie ein untergeordnetes MDI-Formular, und legen dessen <xref:System.Windows.Forms.Form.MdiParent%2A> -Eigenschaft auf den Namen des übergeordneten Formulars.  
  
4.  Hinzufügen einer <xref:System.Windows.Forms.MenuStrip> , untergeordneten MDI-Formulars.  
  
5.  Im untergeordneten Formular, legen Sie die <xref:System.Windows.Forms.ToolStripItem.Visible%2A> Eigenschaft der <xref:System.Windows.Forms.MenuStrip> zu `false`.  
  
6.  Hinzufügen von Menüelementen des untergeordneten Formulars <xref:System.Windows.Forms.MenuStrip> , die Sie mit des übergeordneten Formulars zusammenführen möchten <xref:System.Windows.Forms.MenuStrip> Wenn das untergeordnete Formular aktiviert ist.  
  
7.  Verwenden der <xref:System.Windows.Forms.ToolStripItem.MergeAction%2A> Eigenschaft, die Sie im Menü des untergeordneten Formulars Elemente <xref:System.Windows.Forms.MenuStrip> steuern, wie sie mit dem übergeordneten Formular zusammenführen.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [Übersicht über das MenuStrip-Steuerelement](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)
