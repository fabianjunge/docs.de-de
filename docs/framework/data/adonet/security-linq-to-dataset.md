---
title: Sicherheit (LINQ to DataSet)
ms.date: 03/30/2017
ms.assetid: 6116b2b8-75f4-4d8b-aea6-c13e55cda50b
ms.openlocfilehash: e0b71dd3628e0bbc4c11e7b9f62a4833ce6fa811
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54604123"
---
# <a name="security-linq-to-dataset"></a>Sicherheit (LINQ to DataSet)
In diesem Thema werden Fragen der Sicherheit in [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] behandelt.  
  
## <a name="passing-a-query-to-an-untrusted-component"></a>Übergeben einer Abfrage an eine nicht vertrauenswürdige Komponente  
 Ein [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] Abfrage formuliert wird, an einem Punkt eines Programms und in einem anderen Konto ausgeführt werden kann. An dem Punkt, an dem die Abfrage formuliert wird, kann die Abfrage auf jedes beliebige Element verweisen, das an diesem Punkt sichtbar ist, z. B. private Member der Klasse, zu der die aufrufende Methode gehört, oder Symbole, die lokale Variablen/Argumente darstellen. Zum Zeitpunkt der Ausführung ist die Abfrage wirksam in der Lage, auf die Member zuzugreifen, auf die von der Abfrage bei der Formulierung verwiesen wurde, selbst wenn der aufrufende Code diese gar nicht einsehen kann. Der Code, der die Abfrage ausführt, besitzt insofern keine willkürlich hinzugefügte Sichtbarkeit, als dass er nicht wählen kann, worauf er zugreift. Er kann nur auf die Elemente zugreifen, auf die die Abfrage zugreift, und dies auch nur über die Abfrage selbst.  
  
 Das bedeutet, wenn ein Verweis auf eine Abfrage an ein anderes Stück Code übergeben wird, wird der Komponente, die die Abfrage empfängt, so vertraut, dass sie auf alle öffentlichen und privaten Member zugreifen darf, auf die die Abfrage verweist. Im allgemeinen [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] Abfragen darf nicht auf nicht vertrauenswürdigen Komponenten übergeben werden, es sei denn, die Abfrage sehr sorgfältig konstruiert wurde, so, dass es keine Informationen verfügbar macht, die privat bleiben sollten.  
  
## <a name="external-input"></a>Externe Eingabe  
 Anwendungen verwenden häufig externe Eingaben (eines Benutzers oder eines anderen externen Agenten) und führen entsprechend dieser Eingabe Aktionen aus.  Im Fall von [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)], die Anwendung möglicherweise erstellen Sie eine Abfrage auf eine bestimmte Weise basierend auf externe Eingabe oder die externe Eingabe in der Abfrage. [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]-Abfragen akzeptieren Parameter an allen Stellen, an denen Literale akzeptiert werden. Anwendungsentwicklern wird empfohlen, parametrisierte Abfragen zu verwenden, anstatt Literale aus einem externen Agent direkt in die Abfrage einzuschleusen.  
  
 Jede direkt oder indirekt vom Benutzer oder einem externen Agenten abgeleitete Eingabe kann Inhalt besitzen, der die Syntax der Zielsprache nutzt, um nicht genehmigte Aktionen auszuführen. Dieses Verhalten wird als SQL Injection-Angriff bezeichnet. Diese Bezeichnung leitet sich aus einem Angriffsmuster ab, bei dem die Zielsprache Transact-SQL ist. Das Einschleusen von Benutzereingaben direkt in die Abfrage führt zum Löschen einer Datenbanktabelle oder zur Dienstverweigerung (Denial of Service) oder ändert auf andere Art und Weise die auszuführende Operation. Obwohl das Zusammensetzen von Abfragen in [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] möglich ist, wird dieser Vorgang über die Objektmodell-API ausgeführt. [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] Abfragen werden nicht erstellt, indem Zeichenfolgen manipuliert oder verkettet werden, befinden sich in Transact-SQL, und sind nicht anfällig für SQL-Injection-Angriffe im herkömmlichen Sinn.  
  
## <a name="see-also"></a>Siehe auch
- [Programmierhandbuch](../../../../docs/framework/data/adonet/programming-guide-linq-to-dataset.md)
