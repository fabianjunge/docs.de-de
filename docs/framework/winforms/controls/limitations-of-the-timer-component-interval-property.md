---
title: Einschränkungen für die Interval-Eigenschaft der Timer-Komponente in Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- timers [Windows Forms], event intervals
- Interval property [Windows Forms], limitations
- timers [Windows Forms], Windows-based
- Timer component [Windows Forms], limitations of Interval property
ms.assetid: 7e5fb513-77e7-4046-a8e8-aab94e61ca0f
ms.openlocfilehash: 2d8e25d9d27c0908f2d794a0c3c9646024984764
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55269671"
---
# <a name="limitations-of-the-windows-forms-timer-components-interval-property"></a>Einschränkungen für die Interval-Eigenschaft der Timer-Komponente in Windows Forms
Die Windows-Formulare <xref:System.Windows.Forms.Timer> Komponente weist eine <xref:System.Windows.Forms.Timer.Interval%2A> Eigenschaft, die die Anzahl der Millisekunden angibt, die zwischen einem Timer-Ereignishandler und dem nächsten übergeben. Wenn die Komponente deaktiviert wird, wird ein Zeitgeber erhalten die <xref:System.Windows.Forms.Timer.Tick> Ereignis zu ungefähr gleichen Intervallen Zeit.  
  
 Diese Komponente wurde für eine Windows Forms-Umgebung entwickelt. Wenn Sie einen für eine Serverumgebung geeigneten Timer benötigen, lesen Sie die Informationen unter [Introduction to Server-Based Timers (Einführung in serverbasierte Timer)](https://msdn.microsoft.com/library/adc0bc0a-a519-4812-bafc-fb9d1a5801fc).  
  
## <a name="the-interval-property"></a>Die Interval-Eigenschaft  
 Die <xref:System.Windows.Forms.Timer.Interval%2A> Eigenschaft weist einige Einschränkungen zu beachten, wenn Sie Programmieren eine <xref:System.Windows.Forms.Timer> Komponente:  
  
-   Wenn Ihre Anwendung oder einer anderen Anwendung einer hohen auf dem System herstellt, wird – wie lange Schleifen, intensiven Berechnungen oder Laufwerk, Netzwerk oder Portzugriff – Ihre Anwendung kann nicht abgerufen werden Ereignisse für Timer so oft wie die <xref:System.Windows.Forms.Timer.Interval%2A> Eigenschaft gibt an.  
  
-   Das Intervall ist nicht unbedingt genau an der Zeit verstreichen. Um Genauigkeit zu gewährleisten, sollen der Timer die Systemuhr je nach Bedarf überprüfen, sondern versuchen, die bisher abgelaufene Zeit intern mitverfolgen.  
  
-   Die Genauigkeit der <xref:System.Windows.Forms.Timer.Interval%2A> Eigenschaft wird in Millisekunden angegeben. Einige Computer Geben Sie einen hochauflösenden Indikator, der einer höher als Millisekunden Auflösung. Die Verfügbarkeit solcher Zähler hängt von der Prozessorhardware des Computers ab.
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Forms.Timer>
- [Timer-Komponente](../../../../docs/framework/winforms/controls/timer-component-windows-forms.md)
- [Übersicht über die Timer-Komponente](../../../../docs/framework/winforms/controls/timer-component-overview-windows-forms.md)
