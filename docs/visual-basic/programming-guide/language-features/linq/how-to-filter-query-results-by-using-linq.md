---
title: 'Vorgehensweise: Filtern von Abfrageergebnissen unter Verwendung von LINQ (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- filtering [Visual Basic]
- filtering data [LINQ in Visual Basic]
- filtering [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], filtering results
- querying databases [LINQ]
- queries [LINQ in Visual Basic], how-to topics
- query samples [Visual Basic]
- filtering data [Visual Basic]
ms.assetid: ef103092-9bed-4134-97f4-2db696e83c12
ms.openlocfilehash: d0260e53be421d36cdc8d351d30d7f8a4ac4fa84
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54684170"
---
# <a name="how-to-filter-query-results-by-using-linq-visual-basic"></a>Vorgehensweise: Filtern von Abfrageergebnissen unter Verwendung von LINQ (Visual Basic)
Language Integrated Query (LINQ) erleichtert den Zugriff auf Informationen und Ausführen von Abfragen.  
  
 Das folgende Beispiel zeigt, wie Sie eine neue Anwendung zu erstellen, führt Abfragen in SQL Server-Datenbank und filtert die Ergebnisse nach einem bestimmten Wert mithilfe, der `Where` Klausel. Weitere Informationen finden Sie unter [Where-Klausel](../../../../visual-basic/language-reference/queries/where-clause.md).  
  
 In die Beispielen in diesem Thema verwenden die Beispieldatenbank Northwind. Wenn Sie diese Datenbank nicht auf dem Entwicklungscomputer gespeichert haben, können Sie es aus dem Microsoft Download Center herunterladen. Anweisungen hierzu finden Sie unter [Herunterladen von Beispieldatenbanken](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a>Um eine Verbindung mit einer Datenbank zu erstellen.  
  
1.  Öffnen Sie in Visual Studio **Server-Explorer**/**Datenbank-Explorer** durch Klicken auf **Server-Explorer**/**Datenbank Explorer** auf die **Ansicht** Menü.  
  
2.  Mit der rechten Maustaste **Datenverbindungen** in **Server-Explorer**/**Datenbank-Explorer** , und klicken Sie dann auf **Verbindung hinzufügen**.  
  
3.  Geben Sie eine gültige Verbindung mit der Beispieldatenbank Northwind.  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a>Zum Hinzufügen eines Projekts, das eine LINQ to SQL-Datei enthält.  
  
1.  Zeigen Sie in Visual Studio im Menü **Datei** auf **Neu**, und klicken Sie auf **Projekt**. Wählen Sie Visual Basic **Windows Forms-Anwendung** als Projekttyp.  
  
2.  Klicken Sie im Menü **Projekt** auf **Neues Element hinzufügen**. Wählen Sie die **LINQ to SQL-Klassen** Elementvorlage.  
  
3.  Nennen Sie die Datei `northwind.dbml`. Klicken Sie auf **Hinzufügen**. Für die Datei northwind.dbml wird der Object Relational Designer (O/R Designer) geöffnet.  
  
### <a name="to-add-tables-to-query-to-the-or-designer"></a>Hinzufügen von Tabellen zu Abfragen in den O/R-Designer  
  
1.  In **Server-Explorer**/**Datenbank-Explorer**, erweitern Sie die Verbindung zur Northwind-Datenbank. Erweitern Sie die **Tabellen** Ordner.  
  
     Wenn Sie den O/R-Designer geschlossen haben, können Sie sie durch Doppelklicken auf die Datei northwind.dbml, die Sie zuvor hinzugefügt haben erneut öffnen.  
  
2.  Klicken Sie auf der Customers-Tabelle aus, und ziehen Sie es in den linken Bereich des Designers. Klicken Sie auf der Orders-Tabelle aus, und ziehen Sie es in den linken Bereich des Designers.  
  
     Der Designer erstellt neue `Customer` und `Order` Objekte für Ihr Projekt. Beachten Sie, dass der Designer Beziehungen zwischen den Tabellen erkennt und untergeordnete Eigenschaften für verknüpfte Objekte erstellt automatisch aus. Z. B. IntelliSense angezeigt, die die `Customer` Objekt verfügt über eine `Orders` -Eigenschaft für alle Bestellungen für diesen Kunden beziehen.  
  
3.  Speichern Sie die Änderungen zu und schließen Sie den Designer.  
  
4.  Speichern Sie das Projekt.  
  
### <a name="to-add-code-to-query-the-database-and-display-the-results"></a>Hinzufügen von Code aus, um die Datenbank abzufragen und die Ergebnisse werden angezeigt  
  
1.  Von der **Toolbox**, ziehen Sie eine <xref:System.Windows.Forms.DataGridView> Steuerelement auf das Standard-Windows-Formular für das Projekt, Form1.  
  
2.  Doppelklicken Sie auf Form1, um zum Hinzufügen von Code die `Load` -Ereignis des Formulars.  
  
3.  Wenn Sie Tabellen in den O/R-Designer hinzugefügt haben, wird der Designer hinzugefügt eine <xref:System.Data.Linq.DataContext> Objekt für das Projekt. Dieses Objekt enthält den Code, den Sie für den Zugriff auf diese Tabellen, zusätzlich zu einzelnen Objekte und Auflistungen für jede Tabelle benötigen. Die <xref:System.Data.Linq.DataContext> Objekt für das Projekt mit dem Namen wird anhand des Namens der DBML-Datei. Für dieses Projekt die <xref:System.Data.Linq.DataContext> Objekt mit dem Namen `northwindDataContext`.  
  
     Sie können eine Instanz von erstellen die <xref:System.Data.Linq.DataContext> in Ihrem Code und die Abfrage der Tabellen, die vom O/R-Designer angegeben.  
  
     Fügen Sie den folgenden Code der `Load` Ereignis, um die Tabellen zu Abfragen, die als Eigenschaften des Datenkontexts verfügbar gemacht werden. Die Abfrage filtert die Ergebnisse und gibt nur die Kunden, die in befinden `London`.  
  
     [!code-vb[VbLINQToSQLHowTos#11](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-filter-query-results-by-using-linq_1.vb)]  
  
4.  Drücken Sie F5, um das Projekt ausführen und die Ergebnisse anzuzeigen.  
  
5.  Im folgenden werden einige weitere Filter, die Sie ausprobieren können.  
  
     [!code-vb[VbLINQToSQLHowTos#12](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-filter-query-results-by-using-linq_2.vb)]  
  
## <a name="see-also"></a>Siehe auch
- [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [Abfragen](../../../../visual-basic/language-reference/queries/index.md)
- [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)
- [DataContext-Methoden (O/R-Designer)](/visualstudio/data-tools/datacontext-methods-o-r-designer)
