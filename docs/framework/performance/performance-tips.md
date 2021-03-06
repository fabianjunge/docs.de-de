---
title: .NET-Leistungstipps
ms.date: 03/30/2017
helpviewer_keywords:
- C# language, performance
- performance [C#]
- Visual Basic, performance
- performance [Visual Basic]
ms.assetid: ae275793-857d-4102-9095-b4c2a02d57f4
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: b998240b6ecf692b00e16c2ad311c804edc0d7e1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54518220"
---
# <a name="net-performance-tips"></a>.NET-Leistungstipps
Der Begriff *Leistung* bezieht sich im Allgemeinen auf die Ausführungsgeschwindigkeit eines Programms. In manchen Fällen können Sie die Ausführungsgeschwindigkeit erhöhen, indem Sie im Quellcode bestimmte Grundregeln befolgen. In einigen Programmen müssen Sie den Code genau untersuchen und mithilfe von Profilern sicherstellen, dass dieser so schnell wie möglich ausgeführt wird. In anderen Programmen müssen Sie keine solche Optimierung ausführen, da Code in der aktuellen Form mit akzeptabler Geschwindigkeit ausgeführt wird. Dieser Artikel beschreibt einige häufige Bereiche, in denen die Leistung abnehmen kann, und enthält Tipps zur Verbesserung sowie Links zu weiteren Leistungsthemen. Weitere Informationen zum Planen und Messen der Leistung finden Sie unter [Performance](../../../docs/framework/performance/index.md).  
  
## <a name="boxing-and-unboxing"></a>Boxing und Unboxing  
 Am besten verwenden Sie keine Werttypen in Situationen, in denen sie öfter geschachtelt werden müssen, z. B. in nicht generischen Auflistungsklassen wie <xref:System.Collections.ArrayList?displayProperty=nameWithType>. Sie können die Schachtelung von Werttypen vermeiden, indem Sie generische Auflistungen, z. B. <xref:System.Collections.Generic.List%601?displayProperty=nameWithType>, verwenden. Boxing und Unboxing sind rechenintensive Prozesse. Wenn ein Werttyp geschachtelt wird, muss ein völlig neues Objekt erstellt werden. Dies kann bis zu 20-mal länger dauern als eine einfache Zuweisung eines Verweises. Eine Umwandlung durch Unboxing kann vier Mal mehr Zeit beanspruchen als eine Zuweisung. Weitere Informationen finden Sie unter [Boxing und Unboxing](~/docs/csharp/programming-guide/types/boxing-and-unboxing.md).  
  
## <a name="strings"></a>Zeichenfolgen  
 Wenn Sie eine große Anzahl von Zeichenfolgenvariablen verketten, z.B. in einer dichten Schleife, verwenden Sie <xref:System.Text.StringBuilder?displayProperty=nameWithType> anstelle des [+ Operators](~/docs/csharp/language-reference/operators/addition-operator.md) in C# oder der Visual Basic-[Verkettungsoperatoren](~/docs/visual-basic/language-reference/operators/concatenation-operators.md). Weitere Informationen finden Sie unter [Vorgehensweise: Verketten von mehreren Zeichenfolgen](../../csharp/how-to/concatenate-multiple-strings.md) und [Verkettungsoperatoren in Visual Basic](~/docs/visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md).  
  
## <a name="destructors"></a>Destruktoren  
 Leere Destruktoren sollten nicht verwendet werden. Wenn eine Klasse einen Destruktor enthält, wird ein Eintrag in der Finalize-Warteschlange erstellt. Wenn der Destruktor aufgerufen wird, wird der Garbage Collector aufgerufen, um die Warteschlange zu verarbeiten. Wenn der Destruktor leer ist, führt dies einfach zu einem Leistungsverlust. Weitere Informationen finden Sie unter [Destruktoren](~/docs/csharp/programming-guide/classes-and-structs/destructors.md) und [Object Lifetime: Wie die Objekte erstellt und zerstört werden](~/docs/visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).  
  
## <a name="other-resources"></a>Weitere Ressourcen  
  
-   [Writing Faster Managed Code: Know What Things Cost](https://go.microsoft.com/fwlink/?LinkId=99294)  
  
-   [Schreiben von Hochleistungs-verwalteten Anwendungen Eine Einführung](https://go.microsoft.com/fwlink/?LinkId=99295)  
  
-   [Garbage Collector-Grundlagen und Tipps zur Leistung](https://go.microsoft.com/fwlink/?LinkId=99296)  
  
-   [Performance Tips and Tricks in .NET Applications (Tipps und Tricks zur Leistung in .NET-Anwendungen)](https://go.microsoft.com/fwlink/?LinkId=99297)  

-   [Rico Mariani's Performance Tidbits (Rico Marianis spezielle Leistungstipps)](https://go.microsoft.com/fwlink/?LinkId=115679)  

-   [Blog von Vance morrisons](https://blogs.msdn.microsoft.com/vancem/)
  
## <a name="see-also"></a>Siehe auch
- [Leistung](../../../docs/framework/performance/index.md)
- [Programmierkonzepte](https://msdn.microsoft.com/library/65c12cca-af4f-4017-886e-2dbc00a189d6)
- [Visual Basic-Programmierhandbuch](../../visual-basic/programming-guide/index.md)
- [C#-Programmierhandbuch](../../csharp/programming-guide/index.md)
