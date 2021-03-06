---
title: 'Vorgehensweise: Erstellen Sie ein Kennwort-Textfeld mit dem TextBox-Steuerelement in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- TextBox control [Windows Forms], entering passwords
- password boxes [Windows Forms], creating
- PasswordChar property in text boxes
- passwords [Windows Forms], input mask
- passwords [Windows Forms], password text box
ms.assetid: d105d6b9-3d50-44cd-80d8-2c0e2f486727
ms.openlocfilehash: b6fe0e615cc5bbd0f549505ed9e6add8d7a51433
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54523986"
---
# <a name="how-to-create-a-password-text-box-with-the-windows-forms-textbox-control"></a>Vorgehensweise: Erstellen Sie ein Kennwort-Textfeld mit dem TextBox-Steuerelement in Windows Forms
Ein Kennwortfeld ist ein Windows Forms-Textfeld ein, die Platzhalterzeichen zeigt an, wenn ein Benutzer eine Zeichenfolge eingibt.  
  
### <a name="to-create-a-password-text-box"></a>Erstellen Sie ein Kennwort-Textfeld  
  
1.  Legen Sie die <xref:System.Windows.Forms.TextBox.PasswordChar%2A> Eigenschaft der <xref:System.Windows.Forms.TextBox> Steuerelement auf ein bestimmtes Zeichen.  
  
     Die <xref:System.Windows.Forms.TextBox.PasswordChar%2A> Eigenschaft gibt das Zeichen, die Sie im Textfeld angezeigt. Wenn Sternchen im Kennwortfeld angezeigt werden sollen, z. B. Geben Sie * für die <xref:System.Windows.Forms.TextBox.PasswordChar%2A> Eigenschaft im Eigenschaftenfenster angezeigt. Unabhängig davon, welche Zeichen, die ein Benutzer in das Textfeld eingibt, wird dann ein Sternchen angezeigt.  
  
2.  (Optional) Legen Sie die <xref:System.Windows.Forms.TextBoxBase.MaxLength%2A> Eigenschaft. Die Eigenschaft wird bestimmt, wie viele Zeichen in das Textfeld eingegeben werden können. Wenn die maximale Länge überschritten wird, wird das System gibt einen Signalton aus, und im Textfeld akzeptiert keine weiteren Zeichen. Beachten Sie, dass Sie nicht dazu, wie die maximale Länge eines Kennworts für Hacker sein kann, die das Kennwort zu erraten versuchen möchten.  
  
     Im folgenden Codebeispiel wird veranschaulicht, ein Textfeld zu initialisieren, der akzeptiert einer Zeichenfolge mit bis zu 14 Zeichen lang sein und durch Sternchen anstelle der Zeichenfolge. Die `InitializeMyControl` -Prozedur wird nicht automatisch ausgeführt; muss aufgerufen werden.  
  
    > [!IMPORTANT]
    >  Mithilfe der <xref:System.Windows.Forms.TextBox.PasswordChar%2A> Eigenschaft in einem Textfeld können Sie sicherstellen, dass andere Personen nicht das Kennwort eines Benutzers zu bestimmen, wenn sie die Beobachtung. Durch diese Sicherheitsmaßnahme deckt keine Art von gespeichert oder übertragen des Kennworts, die aufgrund Ihrer Anwendungslogik auftreten können. Da der eingegebene Text in keiner Weise nicht verschlüsselt ist, sollten Sie sie behandeln, wie alle anderen vertraulichen Daten. Obwohl es nicht als solche angezeigt wird, wird das Kennwort (es sei denn, Sie einige zusätzliche Sicherheitsmaßnahme implementiert haben) immer noch als nur-Text-Zeichenfolge behandelt.  
  
    ```vb  
    Private Sub InitializeMyControl()  
       ' Set to no text.  
       TextBox1.Text = ""  
       ' The password character is an asterisk.  
       TextBox1.PasswordChar = "*"  
       ' The control will allow no more than 14 characters.  
       TextBox1.MaxLength = 14  
    End Sub  
    ```  
  
    ```csharp  
    private void InitializeMyControl()  
    {  
       // Set to no text.  
       textBox1.Text = "";  
       // The password character is an asterisk.  
       textBox1.PasswordChar = '*';  
       // The control will allow no more than 14 characters.  
       textBox1.MaxLength = 14;  
    }  
    ```  
  
    ```cpp  
    private:  
       void InitializeMyControl()  
       {  
          // Set to no text.  
          textBox1->Text = "";  
          // The password character is an asterisk.  
          textBox1->PasswordChar = '*';  
          // The control will allow no more than 14 characters.  
          textBox1->MaxLength = 14;  
       }  
    ```  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Forms.TextBox>
- [Übersicht über das TextBox-Steuerelement](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)
- [Vorgehensweise: Steuern der Einfügemarke in einem TextBox-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [Vorgehensweise: Erstellen eines schreibgeschützten Textfelds](../../../../docs/framework/winforms/controls/how-to-create-a-read-only-text-box-windows-forms.md)
- [Vorgehensweise: Setzen von Anführungszeichen in Zeichenfolgen](../../../../docs/framework/winforms/controls/how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [Vorgehensweise: Wählen Sie Text im TextBox-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/how-to-select-text-in-the-windows-forms-textbox-control.md)
- [Vorgehensweise: Zeigen Sie mehrerer Zeilen in der TextBox-Steuerelement in Windows Forms an](../../../../docs/framework/winforms/controls/how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [TextBox-Steuerelement](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)
