---
title: 'Vorgehensweise: Wiedergeben eines in eine Ressource aus Windows Form eingebetteten Sounds'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sounds [Windows Forms], playing from resources
- resources [Windows Forms], playing sounds
- playing sounds [Windows Forms], from resources
- SoundPlayer class [Windows Forms], playing sounds from resources
ms.assetid: 7d148bb6-8a1e-47d7-a08d-35828d2e688f
ms.openlocfilehash: 390f70acc99d8950a23ce514d90c79c3da765f2a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54631333"
---
# <a name="how-to-play-a-sound-embedded-in-a-resource-from-a-windows-form"></a>Vorgehensweise: Wiedergeben eines in eine Ressource aus Windows Form eingebetteten Sounds
Sie können die <xref:System.Media.SoundPlayer> Klasse zum Abspielen eines Sounds aus einer eingebetteten Ressource.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[System.Windows.Forms.Sound#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Sound/CS/soundtestform.cs#10)]
 [!code-vb[System.Windows.Forms.Sound#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Sound/VB/soundtestform.vb#10)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
 Importieren der <xref:System.Media?displayProperty=nameWithType> Namespace.  
  
 Die Sounddatei wird als eingebettete Ressource in das Projekt aufgenommen.  
  
 „\<AssemblyName>“ wird durch den Namen der Assembly ersetzt, in die die Sounddatei eingebettet ist. Das Suffix „.dll“ wird nicht angegeben.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Media.SoundPlayer>
- [Vorgehensweise: Wiedergabe von Sound in Windows Forms](../../../../docs/framework/winforms/controls/how-to-play-a-sound-from-a-windows-form.md)
- [Vorgehensweise: Schleife ein wiedergegebenen Sounds in Windows Forms](../../../../docs/framework/winforms/controls/how-to-loop-a-sound-playing-on-a-windows-form.md)
