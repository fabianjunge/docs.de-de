---
title: '*=-Operator (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.*=
helpviewer_keywords:
- operator *=
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- '*= operator [Visual Basic]'
- compound assignment statements [Visual Basic]
ms.assetid: 96c86509-6eb8-4682-8226-3852e049376f
ms.openlocfilehash: 3aa1d563b9657d4e80425b8c2d29e069ca2ef06a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54601882"
---
# <a name="-operator-visual-basic"></a>*=-Operator (Visual Basic)
Multipliziert den Wert einer Variablen oder die Eigenschaft durch den Wert eines Ausdrucks und weist das Ergebnis der Variablen oder Eigenschaft.  
  
## <a name="syntax"></a>Syntax  
  
```  
variableorproperty *= expression  
```  
  
## <a name="parts"></a>Teile  
 `variableorproperty`  
 Erforderlich. Alle numerischen Variablen oder Eigenschaft.  
  
 `expression`  
 Erforderlich. Ein beliebiger numerischer Ausdruck.  
  
## <a name="remarks"></a>Hinweise  
 Das Element auf der linken Seite von der `*=` Operator kann eine einfache skalare Variable, eine Eigenschaft oder ein Element eines Arrays sein. Die Variable oder Eigenschaft kann nicht [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).  
  
 Die `*=` Operator multipliziert zunächst den Wert des Ausdrucks (auf der rechten Seite des Operators) durch den Wert der Variablen oder Eigenschaft (auf der linken Seite des Operators). Der Operator weist das Ergebnis des Vorgangs klicken Sie dann die Variable oder Eigenschaft.  
  
## <a name="overloading"></a>Überladen  
 Die [*-Operator](../../../visual-basic/language-reference/operators/multiplication-operator.md) kann *überladen*, was bedeutet, dass eine Klasse oder Struktur sein Verhalten definieren kann, wenn ein Operand den Typ der Klasse oder Struktur hat. Das Überladen der `*` Operator beeinflusst das Verhalten von der `*=` Operator. Wenn Ihr Code verwendet `*=` für eine Klasse oder Struktur, die Überladungen `*`, werden Sie sicher, dass Sie verstehen, dass das neu definierte Verhalten. Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `*=` Operator, um eine Multiplizieren `Integer` Variable, indem Sie das zweite und das Ergebnis der ersten Variablen zuzuweisen.  
  
 [!code-vb[VbVbalrOperators#5](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/multiplication-assignment-operator_1.vb)]  
  
## <a name="see-also"></a>Siehe auch
- [*-Operator](../../../visual-basic/language-reference/operators/multiplication-operator.md)
- [Zuweisungsoperatoren](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [Arithmetische Operatoren](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Nach Funktionalität sortierte Operatoren](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Anweisungen](../../../visual-basic/programming-guide/language-features/statements.md)
