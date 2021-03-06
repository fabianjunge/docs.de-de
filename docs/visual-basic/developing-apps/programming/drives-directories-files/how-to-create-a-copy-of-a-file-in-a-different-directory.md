---
title: 'Vorgehensweise: Erstellen einer Kopie einer Datei in einem anderen Verzeichnis in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- My.Computer.FileSystem.CopyFile method, copying files [Visual Basic]
- files [Visual Basic], copying
- CopyFile method [Visual Basic], copying files in Visual Basic
- I/O [Visual Basic], copying files
ms.assetid: 88e2145c-d414-45a5-ad03-6f5d58ecca26
ms.openlocfilehash: f14658cedd18aa22f354c0b7d9cca08960cd7690
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54722122"
---
# <a name="how-to-create-a-copy-of-a-file-in-a-different-directory-in-visual-basic"></a>Vorgehensweise: Erstellen einer Kopie einer Datei in einem anderen Verzeichnis in Visual Basic
Mit der `My.Computer.FileSystem.CopyFile`-Methode können Sie Dateien kopieren. Die Parameter der Methode bieten die Möglichkeit, vorhandene Dateien zu überschreiben, die Datei umzubenennen, den Fortschritt des Vorgangs anzuzeigen sowie den Benutzer zu erlauben, den Vorgang abzubrechen.  
  
### <a name="to-copy-a-text-file-to-another-folder"></a>So kopieren Sie eine Textdatei in einen anderen Ordner  
  
-   Verwenden Sie die `CopyFile`-Methode zum Kopieren einer Datei, und geben Sie eine Quelldatei sowie das Zielverzeichnis an. Mit dem `overwrite`-Parameter können Sie angeben, ob vorhandene Dateien überschrieben werden sollen oder nicht. In den folgenden Codebeispielen wird veranschaulicht, wie `CopyFile` verwendet wird.  
  
     [!code-vb[VbFileIOMisc#24](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-create-a-copy-of-a-file-in-a-different-directory_1.vb)]  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Die folgenden Bedingungen können eine Ausnahme auslösen:  
  
-   Der Pfad ist aus einem der folgenden Gründe ungültig: Er ist eine Zeichenfolge der Länge 0, er enthält nur Leerzeichen, er enthält ungültige Zeichen, oder er ist ein Gerätepfad (beginnt mit \\\\.\\) (<xref:System.ArgumentException>).  
  
-   Das System konnte den absoluten Pfad nicht abrufen (<xref:System.ArgumentException>).  
  
-   Der Pfad ist ungültig, da er `Nothing` ist (<xref:System.ArgumentNullException>).  
  
-   Die Quelldatei ist ungültig oder nicht vorhanden (<xref:System.IO.FileNotFoundException>).  
  
-   Der kombinierte Pfad verweist auf ein vorhandenes Verzeichnis (<xref:System.IO.IOException>).  
  
-   Die Zieldatei ist vorhanden und `overwrite` ist auf `False` festgelegt (<xref:System.IO.IOException>).  
  
-   Der Benutzer hat keine ausreichende Berechtigungen für den Dateizugriff (<xref:System.IO.IOException>).  
  
-   Eine Zielordner mit dem gleichen Namen ist in Gebrauch (<xref:System.IO.IOException>).  
  
-   Der Pfad eines Datei- oder Ordnernamens enthält einen Doppelpunkt (:) oder weist ein ungültiges Format auf (<xref:System.NotSupportedException>).  
  
-   `ShowUI` ist auf `True` festgelegt, `onUserCancel` ist auf `ThrowException` festgelegt, und der Benutzer hat den Vorgang abgebrochen (<xref:System.OperationCanceledException>).  
  
-   `ShowUI` ist auf `True` festgelegt, `onUserCancel` ist auf `ThrowException` festgelegt, und ein nicht angegebener E/A-Fehler tritt auf (<xref:System.OperationCanceledException>).  
  
-   Der Pfad überschreitet die im System definierte maximale Länge (<xref:System.IO.PathTooLongException>).  
  
-   Der Benutzer verfügt nicht über die erforderliche Berechtigung (<xref:System.UnauthorizedAccessException>).  
  
-   Dem Benutzer fehlen die erforderlichen Berechtigungen zum Anzeigen des Pfades (<xref:System.Security.SecurityException>).  
  
## <a name="see-also"></a>Siehe auch
- <xref:Microsoft.VisualBasic.FileIO.FileSystem>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%2A>
- <xref:Microsoft.VisualBasic.FileIO.UICancelOption>
- [Vorgehensweise: Kopieren von Dateien mit einem bestimmten Muster in ein Verzeichnis](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-copy-files-with-a-specific-pattern-to-a-directory.md)
- [Vorgehensweise: Erstellen einer Kopie einer Datei im gleichen Verzeichnis](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-create-a-copy-of-a-file-in-the-same-directory.md)
- [Vorgehensweise: Kopieren eines Verzeichnisses in ein anderes Verzeichnis](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-copy-a-directory-to-another-directory.md)
- [Vorgehensweise: Umbenennen einer Datei](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-rename-a-file.md)
