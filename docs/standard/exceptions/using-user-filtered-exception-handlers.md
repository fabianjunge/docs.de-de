---
title: Verwenden benutzergefilterter Ausnahmehandler
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- user-filtered exceptions
- exceptions, user-filtered
ms.assetid: aa80d155-060d-41b4-a636-1ceb424afee8
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d1e771a95542153dfad0981d3198e6b4c31cdeb9
ms.sourcegitcommit: 700b9003ea6bdd83a53458bbc436c9b5778344f1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/03/2018
ms.locfileid: "48261419"
---
# <a name="using-user-filtered-exception-handlers"></a>Verwenden benutzergefilterter Ausnahmehandler
Visual Basic unterstützt benutzergefilterte Ausnahmen. Benutzergefilterte Handler fangen und behandeln Ausnahmen gemäß benutzerdefinierten Ausnahmeanforderungen. In diesen Handlern wird die **Catch**-Anweisung mit dem Schlüsselwort **When** verwendet.  
  
 Dieses Verfahren ist nützlich, wenn ein bestimmtes Ausnahmeobjekt mehreren Fehlern entspricht. In diesem Fall hat das Objekt in der Regel eine Eigenschaft, die den speziellen Fehlercode enthält, der mit dem Fehler verknüpft ist. Sie können die Eigenschaft, die den Fehlercode enthält, im Ausdruck dazu verwenden, nur den bestimmten Fehler auszuwählen, den Sie in dieser **Catch**-Klausel behandeln möchten.  
  
 Im folgenden Visual Basic-Beispiel wird die **Catch/When**-Anweisung veranschaulicht.  
  
```  
Try  
      'Try statements.  
   Catch When Err = VBErr_ClassLoadException  
      'Catch statements.  
End Try  
```  
  
 Der Ausdruck der benutzergefilterten Klausel ist in keiner Weise eingeschränkt. Tritt während der Ausführung des benutzergefilterten Ausdrucks eine Ausnahme auf, wird diese Ausnahme verworfen, und der Filterausdruck wird so bewertet, als habe er das Ergebnis „false“ gehabt. In diesem Fall setzt die Common Language Runtime die Suche nach einem Handler für die aktuelle Ausnahme fort.  
  
## <a name="combining-the-specific-exception-and-the-user-filtered-clauses"></a>Kombinieren der speziellen Ausnahme und der benutzergefilterten Klauseln  
 Eine Catch-Anweisung kann sowohl die spezielle Ausnahme als auch die benutzergefilterten Klauseln enthalten. Die Runtime prüft zuerst die spezielle Ausnahme. Wird die spezielle Ausnahme erfolgreich abgefangen, führt die Runtime den Benutzerfilter aus. Der allgemeine Filter kann einen Verweis auf die Variable enthalten, die im Klassenfilter deklariert ist. Die Reihenfolge der beiden Filterklauseln nicht umgekehrt werden.  
  
 Im folgenden Visual Basic-Beispiel werden die spezielle Ausnahme `ClassLoadException` in der **Catch**-Anweisung sowie die benutzergefilterte Klausel mit dem Schlüsselwort **When** veranschaulicht.  
  
```  
Try  
      'Try statements.  
   Catch cle As ClassLoadException When cle.IsRecoverable()  
      'Catch statements.  
End Try  
```  

## <a name="see-also"></a>Siehe auch

- [Ausnahmen](index.md)
