---
title: Anwendbarkeit der funktionalen Transformation (C#)
ms.date: 07/20/2015
ms.assetid: c78107bd-b006-4574-a3d4-bbf808388ff3
ms.openlocfilehash: 72027dadfd2b9a4596c68507535301a8a20741fb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54598146"
---
# <a name="applicability-of-functional-transformation-c"></a>Anwendbarkeit der funktionalen Transformation (C#)
Reine funktionale Transformationen können in vielen Situationen angewendet werden.  
  
 Funktionale Transformationen sind hervorragend für das Abfragen und Bearbeiten strukturierter Daten geeignet, sodass dieser Ansatz gut zu LINQ-Technologien passt. Die Palette der Anwendungsmöglichkeiten der funktionalen Transformation ist aber viel größer als die bloße Verwendung mit LINQ. Alle Prozesse, bei denen es hauptsächlich um das Transformieren von Daten von einer Form in eine andere Form geht, sollten als potenzielle Kandidaten für die funktionale Transformation angesehen werden.  
  
 Dieser Ansatz ist auf viele Probleme anwendbar, die zunächst als nicht geeignet erscheinen mögen. Funktionale Transformationen können &#150; in Verbindung mit oder separat von LINQ &#150; für die folgenden Bereiche in Erwägung gezogen werden:  
  
-   XML-basierte Dokumente: Wohlgeformte Daten eines beliebigen XML-Dialekts können durch funktionale Transformation leicht bearbeitet werden. Weitere Informationen finden Sie unter [Functional Transformation of XML (C#) (Funktionale Transformation von XML (C#))](../../../../csharp/programming-guide/concepts/linq/functional-transformation-of-xml.md).  
  
-   Andere strukturierte Dateiformate: Angefangen bei <legacyBold>Windows.ini</legacyBold>-Dateien bis hin zu Nur-Text-Dokumenten besitzen die meisten Dateien eine gewisse Struktur, die zu Analyse- und Transformationszwecken verwendet werden kann.  
  
-   Datenstreamingprotokolle: Das Codieren von Daten in und das Decodieren von Daten aus Kommunikationsprotokollen kann häufig als einfache funktionale Transformation dargestellt werden.  
  
-   RDBMS- und OODBMS-Daten: Relationale und objektorientierte Datenbanken sind, wie XML, häufig verwendete strukturierte Datenquellen.  
  
-   Mathematische, statistische und naturwissenschaftliche Lösungen: In diesen Bereichen werden gern große Datensätze bearbeitet, um den Benutzer bei der Visualisierung, Schätzung oder eigentlichen Lösung schwieriger Probleme zu unterstützen.  
  
 Wie in [Refactoring Into Pure Functions (Refactoring in reine Funktionen (C#))](../../../../csharp/programming-guide/concepts/linq/refactoring-into-pure-functions.md) beschrieben, ist die Verwendung von reinen Funktionen ein Beispiel für die funktionale Programmierung. Neben ihren unmittelbaren Vorteilen sorgt die Verwendung reiner Funktionen auch für wertvolle Erfahrungen, wenn es darum geht, Probleme aus der Perspektive einer funktionalen Transformation zu betrachten. Dieser Ansatz kann sich auch signifikant auf die Programm- und Klassenentwicklung auswirken. Dies gilt insbesondere dann, wenn sich ein Problem für eine Datentransformationslösung geradezu anbietet (siehe oben).  
  
 Da eine weitere Erläuterung dieses Themas den Rahmen dieses Lehrprogramms sprengen würde, sei hier nur so viel gesagt: Entwürfe, die von der Perspektive der funktionalen Transformation beeinflusst sind, sind tendenziell mehr auf Prozesse als auf Objekte als Hauptakteure ausgerichtet. Die sich so ergebende Lösung wird zumeist als Serie groß angelegter Transformationen implementiert, statt in Form individueller Objektzustandsänderungen.  
  
 Vergessen Sie bei allem nicht: C# unterstützt sowohl den imperativen als auch den funktionalen Ansatz. Der beste Entwurf für Ihre Anwendung ist daher möglicherweise ein Entwurf, der beide Elemente beinhaltet.  
  
## <a name="see-also"></a>Siehe auch

- [Introduction to Pure Functional Transformations (C#) (Einführung in reine funktionale Transformationen (c#))](../../../../csharp/programming-guide/concepts/linq/introduction-to-pure-functional-transformations.md)
- [Funktionale Transformation von XML (C#)](../../../../csharp/programming-guide/concepts/linq/functional-transformation-of-xml.md)
- [Refactoring in reine Funktionen (C#)](../../../../csharp/programming-guide/concepts/linq/refactoring-into-pure-functions.md)
