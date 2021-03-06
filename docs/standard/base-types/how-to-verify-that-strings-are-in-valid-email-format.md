---
title: 'Vorgehensweise: Überprüfen, ob Zeichenfolgen ein gültiges E-Mail-Format aufweisen'
ms.date: 12/10/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- regular expressions, examples
- user input, examples
- Regex.IsMatch method
- regular expressions [.NET Framework], examples
- examples [Visual Basic], strings
- IsValidEmail
- validation, email strings
- input, checking
- strings [.NET Framework], examples [Visual Basic]
- email [.NET Framework], validating
- IsMatch method
ms.assetid: 7536af08-4e86-4953-98a1-a8298623df92
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9ed0721f2bfa8e272822740cf26173c1592de428
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2018
ms.locfileid: "53236647"
---
# <a name="how-to-verify-that-strings-are-in-valid-email-format"></a>Vorgehensweise: Überprüfen, ob Zeichenfolgen ein gültiges E-Mail-Format aufweisen
Im folgenden Beispiel wird mit einem regulären Ausdruck geprüft, ob eine Zeichenfolge ein gültiges E-Mail-Format aufweist.  

## <a name="example"></a>Beispiel  
 Im Beispiel wird eine `IsValidEmail` -Methode definiert, die `true` zurückgibt, wenn die Zeichenfolge eine gültige E-Mail-Adresse enthält und andernfalls `false` ; es wird jedoch keine andere Aktion ausgeführt.  
  
 Um die Gültigkeit der E-Mail-Adresse zu überprüfen ruft die `IsValidEmail` -Methode die <xref:System.Text.RegularExpressions.Regex.Replace%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.MatchEvaluator%29?displayProperty=nameWithType> -Methode mit dem regulären Ausdruck `(@)(.+)$` auf, um den Domänennamen von der E-Mail-Adresse zu trennen. Der dritte Parameter ist ein <xref:System.Text.RegularExpressions.MatchEvaluator> -Delegat, der die Methode darstellt, die den gefundenen Text verarbeitet und ersetzt. Das Muster des regulären Ausdrucks wird wie folgt interpretiert:  
  
|Muster|Beschreibung |  
|-------------|-----------------|  
|`(@)`|Das @ Zeichen wird als Übereinstimmung verwendet. Dies ist die erste Erfassungsgruppe.|  
|`(.+)`|Ein- oder mehrmalige Übereinstimmung mit beliebigem Zeichen. Dies ist die zweite Erfassungsgruppe.|  
|`$`|Beendet die Suche am Ende der Zeichenfolge.|  
  
 Der Domänenname wird zusammen mit dem @ Zeichen der `DomainMapper` -Methode übergeben, die die <xref:System.Globalization.IdnMapping> -Klasse verwendet, um Unicode-Zeichen in ihre Punycode-Entsprechungen zu übersetzen, die außerhalb des 7-Bit-ASCII-Zeichenbereichs liegen. Darüber hinaus wird die Methode auch das `invalid`-Flag auf `True` fest, wenn die <xref:System.Globalization.IdnMapping.GetAscii%2A?displayProperty=nameWithType>-Methode ein unzulässiges Zeichen im Domänennamen erkennt. Diese Methode gibt den Punycode-Domänennamen, der dem @ Zeichen vorangestellt ist, an die `IsValidEmail` -Methode zurück.  
  
 Die `IsValidEmail`-Methode ruft dann die <xref:System.Text.RegularExpressions.Regex.IsMatch%28System.String%2CSystem.String%29?displayProperty=nameWithType>-Methode auf, um zu überprüfen, ob die Adresse dem Muster eines regulären Ausdrucks entspricht.  
  
 Beachten Sie, dass die `IsValidEmail` -Methode keine Authentifizierung zur Überprüfung der E-Mail-Adresse durchführt. Sie bestimmt nur, ob das Format für eine E-Mail-Adresse gültig ist. Außerdem überprüft die `IsValidEmail` -Methode nicht, ob der Domänenname der obersten Ebene ein gültiger Domänenname ist, der in der [IANA Root Zone Database](https://www.iana.org/domains/root/db)aufgelistet ist, was einen Suchvorgang erfordern würde. Stattdessen verifiziert der reguläre Ausdruck nur, dass der Domänenname der obersten Ebene aus zwei bis 24 ASCII-Zeichen besteht, wobei das erste und letzte Zeichen alphanumerisch und die übrigen Zeichen alphanumerisch oder ein Bindestrich (-) sein müssen.  
  
 [!code-csharp[RegularExpressions.Examples.Email#7](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.Email/cs/example4.cs#7)]
 [!code-vb[RegularExpressions.Examples.Email#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.Email/vb/example4.vb#7)]  
  
 In diesem Beispiel kann das Muster des regulären Ausdrucks ``^(?(")(".+?(?<!\\)"@)|(([0-9a-z]((\.(?!\.))|[-!#\$%&'\*\+/=\?\^`{}|~\w])*)(?<=[0-9a-z])@))(?([)([(\d{1,3}.){3}\d{1,3}])|(([0-9a-z][-0-9a-z]*[0-9a-z]*.)+[a-z0-9][-a-z0-9]{0,22}[a-z0-9]))$`` wie in der folgenden Tabelle dargestellt interpretiert werden. Beachten Sie, dass der reguläre Ausdruck mit dem Flag <xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase?displayProperty=nameWithType> kompiliert wurde.  
  
|Muster|Beschreibung |  
|-------------|-----------------|  
|`^`|Starten Sie den Vergleich am Beginn der Zeichenfolge.|  
|`(?(")`|Ermittelt, ob es sich beim ersten Zeichen um ein Anführungszeichen handelt. `(?(")` ist der Anfang eines Alternierungskonstrukts.|  
|`(?("")("".+?(?<!\\)""@)`|Wenn es sich beim ersten Zeichen um ein Anführungszeichen handelt, wird ein öffnendes Anführungszeichen als Übereinstimmung verwendet, dem mindestens ein beliebiges Zeichen und ein schließendes Anführungszeichen folgen. Dem schließenden Anführungszeichen darf kein umgekehrter Schrägstrich (\\) vorangestellt sein. `(?<!` ist der Anfang einer negativen Lookbehindassertion mit einer Breite von Null. Die Zeichenfolge muss mit einem @-Zeichen enden.|  
|<code>&#124;(([0-9a-z]</code>|Wenn es sich beim ersten Zeichen um kein Anführungszeichen handelt, wird ein beliebiges Buchstabenzeichen von a bis z oder A bis Z (die Groß-/Kleinschreibung wird nicht beachtet) oder ein beliebiges numerisches Zeichen von 0 bis 9 als Übereinstimmung verwendet.|  
|`(\.(?!\.))`|Wenn es sich beim nächsten Zeichen um einen Punkt handelt, wird dieser als Übereinstimmung verwendet. Wenn es sich um keinen Punkt handelt, wird bis zum nächsten Zeichen weitergesucht und der Vergleich fortsetzt. `(?!\.)` ist eine negative Lookaheadassertion mit einer Breite von 0 (Null), die verhindert, dass im lokalen Teil einer E-Mail-Adresse zwei aufeinander folgende Punkte enthalten sind.|  
|<code>&#124;[-!#\$%&'\*\+/=\?\^\`{}\&#124;~\w]</code>|Wenn es sich beim nächsten Zeichen nicht um einen Punkt handelt, wird ein beliebiges Wortzeichen oder eines der folgenden Zeichen als Übereinstimmung verwendet: -!#$%'*+=?^\`{}&#124;~.|  
|<code>((\.(?!\.))&#124;[-!#\$%'\*\+/=\?\^\`{}\&#124;~\w])*</code>|0 oder mehr Vorkommen des Alternierungsmusters werden als Übereinstimmung verwendet (ein Punkt, dem ein anderes Zeichen als ein Punkt oder eines aus einer Reihe von Zeichen folgt).|  
|`@`|Das @ Zeichen wird als Übereinstimmung verwendet.|  
|`(?<=[0-9a-z])`|Die Suche wird fortgesetzt, wenn es sich bei dem Zeichen, das dem @ Zeichen vorausgeht, ist, um eines der Zeichen A bis Z, a bis z oder 0 bis 9 handelt. Das `(?<=[0-9a-z])` -Konstrukt definiert eine positive Lookbehindassertion mit einer Breite von 0 (Null).|  
|`(?(\[)`|Überprüfen Sie, ob es sich bei dem Zeichen, das @ folgt, um eine eckige Klammer links handelt.|  
|`(\[(\d{1,3}\.){3}\d{1,3}\])`|Wenn es sich um eine eckige Klammer links handelt, wird die eckige Klammer links als Übereinstimmung verwendet, der eine IP-Adresse (vier Gruppen aus einer bis drei Ziffern, jeweils durch einen Punkt getrennt) und eine eckige Klammer rechts folgen.|  
|<code>&#124;(([0-9a-z][-0-9a-z]*[0-9a-z]*\.)+</code>|Wenn es sich bei dem Zeichen, das @ folgt, um keine öffnende eckige Klammer handelt, wird ein alphanumerisches Zeichen mit einem Wert von A-Z, a-z oder 0-9 als Übereinstimmung verwendet, dem null oder mehr Vorkommen eines Bindestrichs und kein oder ein alphanumerisches Zeichen mit einem Wert von A-Z, a-z oder 0-9 sowie ein Punkt folgen. Dieses Muster kann ein- oder mehrmals wiederholt werden und der Domänenname der obersten Ebene muss darauf folgen.|  
|`[a-z0-9][\-a-z0-9]{0,22}[a-z0-9]))`|Der Domänenname der obersten Ebene muss mit einem alphanumerischen Zeichen (a-z, A-Z und 0-9) beginnen und enden. Er kann außerdem 0 bis 22 ASCII-Zeichen enthalten, die entweder alphanumerische Zeichen oder Bindestriche sind.|  
|`$`|Beendet die Suche am Ende der Zeichenfolge.|  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Die `IsValidEmail` -Methode und die `DomainMapper` -Methode können in einer Bibliothek von Hilfsprogrammmethoden für reguläre Ausdrücke oder als private statische oder Instanzmethoden in der Anwendungsklasse enthalten sein.  
  
 Um sie in einer Bibliothek für reguläre Ausdrücke einzubeziehen, kopieren und fügen Sie den Code in ein Visual Studio-Klassenbibliotheksprojekt ein, oder kopieren und fügen Sie den Code in eine Textdatei ein, und kompilieren Sie ihn über die Befehlszeile mit einem Befehl wie dem folgenden (vorausgesetzt der Name der Quellcodedatei ist "RegexUtilities.cs" oder "RegexUtilities.vb"):  
  
```csharp  
csc /t:library RegexUtilities.cs  
```  
  
```vb  
vbc /t:library RegexUtilities.vb  
```  
  
 Sie können auch die <xref:System.Text.RegularExpressions.Regex.CompileToAssembly%2A?displayProperty=nameWithType> -Methode verwenden, um diesen regulären Ausdruck in eine Bibliothek für reguläre Ausdrücke einzuschließen.  
  
 Wenn sie in einer Bibliothek für reguläre Ausdrücke verwendet werden, können Sie die Methoden mit dem folgenden Code aufrufen:  
  
 [!code-csharp[RegularExpressions.Examples.Email#8](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.Email/cs/example4.cs#8)]
 [!code-vb[RegularExpressions.Examples.Email#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.Email/vb/example4.vb#8)]  
  
 Wenn Sie eine Klassenbibliothek mit dem Namen "RegexUtilities.dll" erstellt haben, die den regulären Ausdruck zur E-Mail-Gültigkeitsprüfung enthält, können Sie dieses Beispiel mit einer der folgenden Methoden kompilieren:  
  
-   In Visual Studio durch Erstellen eine Konsolenanwendung und Hinzufügen eines Verweises auf RegexUtilities.dll zum Projekt.  
  
-   Über die Befehlszeile durch Kopieren und Einfügen des Quellcodes in eine Textdatei und durch Kompilieren mit einem Befehl wie dem folgenden (vorausgesetzt der Name der Quellcodedatei ist "Example.cs" oder "Example.vb"):  
  
    ```csharp  
    csc Example.cs /r:RegexUtilities.dll  
    ```  
  
    ```vb  
    vbc Example.vb /r:RegexUtilities.dll  
    ```  
  
## <a name="see-also"></a>Siehe auch

- [Reguläre Ausdrücke von .NET Framework](../../../docs/standard/base-types/regular-expressions.md)
