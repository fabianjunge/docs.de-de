---
title: 'Vorgehensweise: Steuern des Typs einer Projektion (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: a0171276-0b46-4817-aee5-a8d5191b12fe
ms.openlocfilehash: e892e6328576a9727a13a4c1acd951d44ce4daa8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54628874"
---
# <a name="how-to-control-the-type-of-a-projection-visual-basic"></a>Vorgehensweise: Steuern des Typs einer Projektion (Visual Basic)
Bei einer Projektion wird ein Satz von Daten gefiltert und in der Form und sogar im Typ geändert. Die meisten Abfrageausdrücke führen Projektionen aus. Bei den meisten Abfrageausdrücken in diesem Abschnitt ist das Ergebnis der Auswertung eine <xref:System.Collections.Generic.IEnumerable%601> von <xref:System.Xml.Linq.XElement>, aber Sie können festlegen, welcher Projektionstyp verwendet werden soll, um Auflistungen eines anderen Typs zu erstellen. In diesem Thema wird gezeigt, wie Sie dazu vorgehen müssen.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel definiert einen neuen Typ: `Customer`. Der Abfrageausdruck instanziiert dann in der `Customer`-Klausel neue `Select`-Objekte. Damit ist der Typ des Abfrageausdrucks eine <xref:System.Collections.Generic.IEnumerable%601> von `Customer`.  
  
 In diesem Beispiel wird die folgende XML-Dokument verwendet: [XML-Beispieldatei: Kunden und Bestellungen (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml.md).  
  
```vb  
Public Class Customer  
    Private customerIDValue As String  
    Public Property CustomerID() As String  
        Get  
            Return customerIDValue  
        End Get  
        Set(ByVal value As String)  
            customerIDValue = value  
        End Set  
    End Property  
  
    Private companyNameValue As String  
    Public Property CompanyName() As String  
        Get  
            Return companyNameValue  
        End Get  
        Set(ByVal value As String)  
            companyNameValue = value  
        End Set  
    End Property  
  
    Private contactNameValue As String  
    Public Property ContactName() As String  
        Get  
            Return contactNameValue  
        End Get  
        Set(ByVal value As String)  
            contactNameValue = value  
        End Set  
    End Property  
  
    Public Sub New(ByVal customerID As String, _  
                   ByVal companyName As String, _  
                   ByVal contactName As String)  
        CustomerIDValue = customerID  
        CompanyNameValue = companyName  
        ContactNameValue = contactName  
    End Sub  
  
    Public Overrides Function ToString() As String  
        Return String.Format("{0}:{1}:{2}", Me.CustomerID, Me.CompanyName, Me.ContactName)  
    End Function  
End Class  
  
Sub Main()  
    Dim custOrd As XElement = XElement.Load("CustomersOrders.xml")  
    Dim custList As IEnumerable(Of Customer) = _  
        From el In custOrd.<Customers>.<Customer> _  
        Select New Customer( _  
            el.@<CustomerID>, _  
            el.<CompanyName>.Value, _  
            el.<ContactName>.Value _  
        )  
    For Each cust In custList  
        Console.WriteLine(cust)  
    Next  
End Sub  
```  
  
 Dieser Code erzeugt die folgende Ausgabe:  
  
```  
GREAL:Great Lakes Food Market:Howard Snyder  
HUNGC:Hungry Coyote Import Store:Yoshi Latimer  
LAZYK:Lazy K Kountry Store:John Steel  
LETSS:Let's Stop N Shop:Jaime Yorres  
```  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Linq.Enumerable.Select%2A>
- [Projektionen und Transformationen (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/projections-and-transformations-linq-to-xml.md)
