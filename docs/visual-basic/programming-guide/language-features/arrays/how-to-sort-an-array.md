---
title: 'Vorgehensweise: Sortieren eines Arrays in Visual Basic'
ms.date: 07/20/2015
f1_keywords:
- Array.Sort
helpviewer_keywords:
- arrays [Visual Basic], sorting
- examples [Visual Basic], arrays
ms.assetid: 9289aeaa-9626-4698-94a7-1d1fd3702b87
ms.openlocfilehash: 0b04bfbedf9d7266d1b2e190fa85b8a64cf6efbf
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54558435"
---
# <a name="how-to-sort-an-array-in-visual-basic"></a>Vorgehensweise: Sortieren eines Arrays in Visual Basic
In diesem Beispiel deklariert einen Array von `String` Objekte, die mit dem Namen `zooAnimals`, füllt es und sortiert es anschließend alphabetisch.  
  
## <a name="example"></a>Beispiel  
  
```  
Private Sub sortAnimals()  
    Dim zooAnimals(2) As String  
    zooAnimals(0) = "lion"  
    zooAnimals(1) = "turtle"  
    zooAnimals(2) = "ostrich"  
    Array.Sort(zooAnimals)  
End Sub  
```  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Zugriff auf "mscorlib.dll" und die <xref:System> Namespace.  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Die folgenden Bedingungen können einen Ausnahmefehler verursachen:  
  
-   Array ist leer (<xref:System.ArgumentNullException> Klasse)  
  
-   Array ist mehrdimensional (<xref:System.RankException> Klasse)  
  
-   Ein oder mehrere Elemente des Arrays implementiert nicht die <xref:System.IComparable> Schnittstelle (<xref:System.InvalidOperationException> Klasse)  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Array.Sort%2A?displayProperty=nameWithType>
- [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [Problembehandlung bei Arrays](../../../../visual-basic/programming-guide/language-features/arrays/troubleshooting-arrays.md)
- [Sammlungen](../../concepts/collections.md)
- [For Each...Next-Anweisung](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)
