---
title: MsgBox-Beispiel
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- marshaling, MsgBox sample
- data marshaling, MsgBox sample
ms.assetid: 9e0edff6-cc0d-4d5c-a445-aecf283d9c3a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bef8ce86a3dba5449e50c890b09acdee1375317c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54719546"
---
# <a name="msgbox-sample"></a>MsgBox-Beispiel
Dieses Beispiel demonstriert, wie Zeichenfolgentypen durch einen Wert als In-Parameter übergeben werden und wann das <xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint>-Feld, das <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet>-Feld und das <xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling>-Feld zu verwenden sind.  
  
 Das MsgBox-Beispiel verwendet die folgende nicht verwaltete Funktion, die zusammen mit ihrer ursprünglichen Funktionsdeklaration aufgeführt wird:  
  
-   **MessageBox** aus „User32.dll“ exportiert.  
  
    ```  
    int MessageBox(HWND hWnd, LPCTSTR lpText, LPCTSTR lpCaption,   
       UINT uType);  
    ```  
  
 In diesem Beispiel enthält die `LibWrap`-Klasse einen verwalteten Prototyp für jede nicht verwaltete Funktion, die durch die `MsgBoxSample`-Klasse aufgerufen wird. Die verwalteten Prototypmethoden `MsgBox`, `MsgBox2` und `MsgBox3` verfügen über unterschiedliche Deklarationen für ein und dieselbe nicht verwaltete Funktion.  
  
 Die Deklaration für `MsgBox2` erzeugt eine falsche Ausgabe im Meldungsfeld, da der als ANSI angegebene Zeichentyp nicht mit dem Einstiegspunkt `MessageBoxW` übereinstimmt, der dem Namen der Unicode-Funktion entspricht. Die Deklaration für `MsgBox3` erzeugt einen Übereinstimmungsfehler zwischen den Feldern **EntryPoint**, **CharSet** und **ExactSpelling**. Die `MsgBox3` -Methode löst bei ihrem Aufruf eine Ausnahme aus. Ausführliche Informationen zur Benennung von Zeichenfolgen und zum Namensmarshallen finden Sie unter [Specifying a Character Set (Angeben eines Zeichensatzes)](specifying-a-character-set.md).  
  
## <a name="declaring-prototypes"></a>Deklarieren von Prototypen  
 [!code-cpp[Conceptual.Interop.Marshaling#5](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/msgbox.cpp#5)]
 [!code-csharp[Conceptual.Interop.Marshaling#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/msgbox.cs#5)]
 [!code-vb[Conceptual.Interop.Marshaling#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/msgbox.vb#5)]  
  
## <a name="calling-functions"></a>Aufrufen von Funktionen  
 [!code-cpp[Conceptual.Interop.Marshaling#6](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/msgbox.cpp#6)]
 [!code-csharp[Conceptual.Interop.Marshaling#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/msgbox.cs#6)]
 [!code-vb[Conceptual.Interop.Marshaling#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/msgbox.vb#6)]  
  
## <a name="see-also"></a>Siehe auch
- [Marshallen von Zeichenfolgen](marshaling-strings.md)
- [Datentypen für den Plattformaufruf](https://msdn.microsoft.com/library/16014d9f-d6bd-481e-83f0-df11377c550f(v=vs.100))
- [Standardmäßiges Marshalling für Zeichenfolgen](default-marshaling-for-strings.md)
- [Creating Prototypes in Managed Code (Erstellen von Prototypen in verwaltetem Code)](creating-prototypes-in-managed-code.md)
- [Specifying a Character Set (Angeben eines Zeichensatzes)](specifying-a-character-set.md)
