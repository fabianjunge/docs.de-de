---
title: 'Vorgehensweise: Hinzufügen und Entfernen von Registerkarten zu TabControls in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- tabs [Windows Forms], removing from pages
- TabPage control
- TabControl control [Windows Forms], adding and removing tabs
- tabs [Windows Forms], adding to pages
- tab pages
ms.assetid: 66d4dfca-41e8-44e3-9c80-fb7ac4cb1619
ms.openlocfilehash: eb3c59a29c9539bcba8827e1a1e9ea807ed44826
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54640740"
---
# <a name="how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol"></a>Vorgehensweise: Hinzufügen und Entfernen von Registerkarten zu TabControls in Windows Forms
Standardmäßig eine <xref:System.Windows.Forms.TabControl> Steuerelement enthält zwei <xref:System.Windows.Forms.TabPage> Steuerelemente. Sie können auf zugreifen, diese mit der Tabulatortaste die <xref:System.Windows.Forms.TabControl.TabPages%2A> Eigenschaft.  
  
### <a name="to-add-a-tab-programmatically"></a>Programmgesteuertes Hinzufügen eine Registerkarte  
  
-   Verwenden der <xref:System.Windows.Forms.TabControl.TabPageCollection.Add%2A> Methode der <xref:System.Windows.Forms.TabControl.TabPages%2A> Eigenschaft.  
  
    ```vb  
    Dim myTabPage As New TabPage()  
    myTabPage.Text = "TabPage" & (TabControl1.TabPages.Count + 1)  
    TabControl1.TabPages.Add(myTabPage)  
    ```  
  
    ```csharp  
    string title = "TabPage " + (tabControl1.TabCount + 1).ToString();  
    TabPage myTabPage = new TabPage(title);  
    tabControl1.TabPages.Add(myTabPage);  
    ```  
  
    ```cpp  
    String^ title = String::Concat("TabPage ",  
       (tabControl1->TabCount + 1).ToString());  
    TabPage^ myTabPage = gcnew TabPage(title);  
    tabControl1->TabPages->Add(myTabPage);  
    ```  
  
### <a name="to-remove-a-tab-programmatically"></a>Das programmgesteuerte Entfernen von einer Registerkarte  
  
-   Verwenden Sie zum Entfernen ausgewählte Registerkarten der <xref:System.Windows.Forms.TabControl.TabPageCollection.Remove%2A> Methode der <xref:System.Windows.Forms.TabControl.TabPages%2A> Eigenschaft.  
  
     - oder -   
  
-   Verwenden Sie zum Entfernen aller Registerkarten der <xref:System.Windows.Forms.TabControl.TabPageCollection.Clear%2A> Methode der <xref:System.Windows.Forms.TabControl.TabPages%2A> Eigenschaft.  
  
    ```vb  
    ' Removes the selected tab:  
    TabControl1.TabPages.Remove(TabControl1.SelectedTab)  
    ' Removes all the tabs:  
    TabControl1.TabPages.Clear()  
    ```  
  
    ```csharp  
    // Removes the selected tab:  
    tabControl1.TabPages.Remove(tabControl1.SelectedTab);  
    // Removes all the tabs:  
    tabControl1.TabPages.Clear();  
    ```  
  
    ```cpp  
    // Removes the selected tab:  
    tabControl1->TabPages->Remove(tabControl1->SelectedTab);  
    // Removes all the tabs:  
    tabControl1->TabPages->Clear();  
    ```  
  
## <a name="see-also"></a>Siehe auch
- [Übersicht über das TabControl-Steuerelement](../../../../docs/framework/winforms/controls/tabcontrol-control-overview-windows-forms.md)
- [Vorgehensweise: Hinzufügen eines Steuerelements zu einer Registerkarte](../../../../docs/framework/winforms/controls/how-to-add-a-control-to-a-tab-page.md)
- [Vorgehensweise: Deaktivieren von Registerkarten](../../../../docs/framework/winforms/controls/how-to-disable-tab-pages.md)
- [Vorgehensweise: Ändern der Darstellung der TabControl-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
