---
title: TryCast-Operator (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.trycast
- trycast
helpviewer_keywords:
- TryCast keyword [Visual Basic]
ms.assetid: d1ef5d47-fef4-491e-b014-1d910628f65c
ms.openlocfilehash: 1bd92428927927a84c1de8f88d176a8f0aba4af2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54524942"
---
# <a name="trycast-operator-visual-basic"></a>TryCast-Operator (Visual Basic)
Führt einen Typkonvertierungsvorgang, der keine Ausnahme auslöst.  
  
## <a name="remarks"></a>Hinweise  
 Wenn eine versuchte einer Konvertierung ein Fehler auftritt, `CType` und `DirectCast` sowohl Auslösen einer <xref:System.InvalidCastException> Fehler. Dies kann die Leistung Ihrer Anwendung beeinträchtigen. `TryCast` Gibt [nichts](../../../visual-basic/language-reference/nothing.md), sodass anstatt um eine mögliche Ausnahme zu behandeln, Sie nur das zurückgegebene Ergebnis mit testen müssen `Nothing`.  
  
 Sie verwenden die `TryCast` Schlüsselwort die gleiche Weise, die Sie verwenden die [CType-Funktion](../../../visual-basic/language-reference/functions/ctype-function.md) und [DirectCast-Operator](../../../visual-basic/language-reference/operators/directcast-operator.md) Schlüsselwort. Sie geben einen Ausdruck als erstes Argument und einen Typ als das zweite Argument konvertiert. `TryCast` kann nur bei Verweistypen, z. B. Klassen und Schnittstellen. Es ist eine Beziehung vererbungs- oder implementierungsbeziehung zwischen den beiden Typen erforderlich. Dies bedeutet, dass ein Typ erben oder den anderen implementieren muss.  
  
## <a name="errors-and-failures"></a>Fehler und Ausfälle  
 `TryCast` generiert einen Compilerfehler, wenn er erkennt, dass keine vererbungs- oder implementierungsbeziehung Beziehung vorhanden ist. Der Mangel an einen Compilerfehler gewährleistet jedoch keine erfolgreiche Konvertierung. Wenn die gewünschte Konvertierung einschränkend ist, kann sie zur Laufzeit fehlschlagen. In diesem Fall `TryCast` gibt [nichts](../../../visual-basic/language-reference/nothing.md).  
  
## <a name="conversion-keywords"></a>Konvertierungsschlüsselwörter  
 Ein Vergleich der Schlüsselwörter für die typkonvertierung lautet wie folgt aus:  
  
|Stichwort|Datentypen|Argument-Beziehung|Laufzeitfehler|  
|---|---|---|---|  
|[CType-Funktion](../../../visual-basic/language-reference/functions/ctype-function.md)|Alle Datentypen|Erweiternde oder einschränkende Konvertierung muss zwischen den beiden Datentypen definiert werden|Löst aus <xref:System.InvalidCastException>|  
|[DirectCast-Operator](../../../visual-basic/language-reference/operators/directcast-operator.md)|Alle Datentypen|Einem Typ muss erben oder implementieren Sie den anderen Typ|Löst aus <xref:System.InvalidCastException>|  
|`TryCast`|Nur Verweistypen|Einem Typ muss erben oder implementieren Sie den anderen Typ|Gibt ["Nothing"](../../../visual-basic/language-reference/nothing.md)|  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht die Verwendung von `TryCast`.  
  
 [!code-vb[VbVbalrKeywords#6](../../../visual-basic/language-reference/codesnippet/VisualBasic/trycast-operator_1.vb)]  
  
## <a name="see-also"></a>Siehe auch
- [Erweiternde und eingrenzende Konvertierungen](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [Implizite und explizite Konvertierungen](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
