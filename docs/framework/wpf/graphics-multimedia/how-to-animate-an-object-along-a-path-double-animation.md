---
title: 'Vorgehensweise: Verschieben eines Objekts auf einem Pfad (DoubleAnimation)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], objects along paths (double animation)
- double animation [WPF]
ms.assetid: 5a3c4a99-f303-42ad-a52a-e4794bb1798e
ms.openlocfilehash: a57b21e3f05f90e756c46c167bb419b5bc9068f4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54600411"
---
# <a name="how-to-animate-an-object-along-a-path-double-animation"></a>Vorgehensweise: Verschieben eines Objekts auf einem Pfad (DoubleAnimation)
Dieses Beispiel zeigt, wie Sie mit der <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> Klasse, um ein Objekt entlang eines Pfads durch Verschieben einer <xref:System.Windows.Media.PathGeometry>.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel verwendet zwei <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> Objekte ein Rechteck entlang eines geometrischen Pfads verschoben:  
  
-   Die erste <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> animiert die <xref:System.Windows.Media.TranslateTransform.X%2A> von der <xref:System.Windows.Media.TranslateTransform> auf das Rechteck angewendet. Das Rechteck wird hierdurch horizontal am Pfad entlang verschoben.  
  
-   Die zweite <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> animiert die <xref:System.Windows.Media.TranslateTransform.Y%2A> von der <xref:System.Windows.Media.TranslateTransform> auf das Rechteck angewendet. Das Rechteck wird hierdurch vertikal am Pfad entlang verschoben.  
  
 [!code-xaml[PathAnimationGallery_snippet#DoubleAnimationUsingPathWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/doubleanimationusingpathexample.xaml#doubleanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#DoubleAnimationUsingPathWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/DoubleAnimationUsingPathExample.cs#doubleanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#DoubleAnimationUsingPathWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/DoubleAnimationUsingPathExample.vb#doubleanimationusingpathwholepage)]  
  
 Das vollständige Beispiel finden Sie unter [Beispiel zu Textanimation](https://go.microsoft.com/fwlink/?LinkID=160028).  
  
 Eine weitere Möglichkeit zum Verschieben eines Objekts mithilfe eines geometrischen Pfads ist die Verwendung einer <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> Objekt. Ein Beispiel finden Sie unter [animieren Sie ein Objekt auf einem Pfad (Matrixanimation)](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-an-object-along-a-path-matrix-animation.md).  
  
## <a name="see-also"></a>Siehe auch
- [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
- [Path Animation How-to Topics (Themen zur Vorgehensweise zur Pfadanimation)](../../../../docs/framework/wpf/graphics-multimedia/path-animation-how-to-topics.md)
