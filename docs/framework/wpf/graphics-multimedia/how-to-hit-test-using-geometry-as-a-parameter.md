---
title: 'Vorgehensweise: Treffertest mit Geometrie als Parameter'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hit tests [WPF], on visual objects using Geometry objects [WPF]
- visual objects [WPF], hit tests on
- Geometry objects [WPF], hit tests on visual objects [WPF]
ms.assetid: 6c8bdbf2-19e0-4fbb-bf89-c1252b2ebc61
ms.openlocfilehash: d52f8da891ecdf632952c441f94aab4c0b56da7f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54564252"
---
# <a name="how-to-hit-test-using-geometry-as-a-parameter"></a>Vorgehensweise: Treffertest mit Geometrie als Parameter
Dieses Beispiel zeigt, wie Sie einen Treffertest durchführen, auf einem visuellen Objekt mit einem <xref:System.Windows.Media.Geometry> Parameter als Treffer zu testen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie ein Treffertest eingerichtet <xref:System.Windows.Media.GeometryHitTestParameters> für die <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> Methode. Die <xref:System.Windows.Point> Wert an der `OnMouseDown` -Methode zum Erstellen einer <xref:System.Windows.Media.Geometry> Objekt um den Bereich des Treffertests zu erweitern.  
  
 [!code-csharp[HitTestingOverview#HitTestingOverviewSnippet10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/GeometryHitTest.cs#hittestingoverviewsnippet10)]
 [!code-vb[HitTestingOverview#HitTestingOverviewSnippet10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/geometryhittest.vb#hittestingoverviewsnippet10)]  
  
 Die <xref:System.Windows.Media.GeometryHitTestResult.IntersectionDetail%2A> -Eigenschaft des <xref:System.Windows.Media.GeometryHitTestResult> enthält Informationen über die Ergebnisse eines Treffertests verwendet eine <xref:System.Windows.Media.Geometry> als Hit test Parameter. In der folgenden Abbildung wird die Beziehung zwischen der Treffertestgeometrie (blauer Kreis) und dem gerenderten Inhalt des Zielobjekts (rotes Quadrat) dargestellt.  
  
 ![Diagramm von IntersectionDetail bei Treffertests](../../../../docs/framework/wpf/graphics-multimedia/media/intersectiondetail01.png "IntersectionDetail01")  
Schnittmenge einer Treffertestgeometrie und eines Zielobjekts  
  
 Das folgende Beispiel zeigt, wie Sie einen Treffertestrückruf implementieren bei einem <xref:System.Windows.Media.Geometry> als Treffertestparameter verwendet wird. Die `result` Parameter der Umwandlung in einen <xref:System.Windows.Media.GeometryHitTestResult> zum Abrufen des Werts der <xref:System.Windows.Media.GeometryHitTestResult.IntersectionDetail%2A> Eigenschaft. Den Wert der Eigenschaft können Sie bestimmen, ob die <xref:System.Windows.Media.Geometry> -Treffertestparameter ganz oder teilweise enthalten ist in den gerenderten Inhalt des Treffertestziels. In diesem Fall fügt der Beispielcode der Liste visueller Objekte nur Treffertestergebnisse hinzu, die vollständig im Zielbereich enthalten sind.  
  
 [!code-csharp[HitTestingOverview#HitTestingOverviewSnippet11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/GeometryHitTest.cs#hittestingoverviewsnippet11)]
 [!code-vb[HitTestingOverview#HitTestingOverviewSnippet11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/geometryhittest.vb#hittestingoverviewsnippet11)]  
  
> [!NOTE]
>  Die <xref:System.Windows.Media.HitTestResult> Rückruf nicht aufgerufen werden soll, wenn die Schnittmenge aufweist <xref:System.Windows.Media.IntersectionDetail.Empty>.  
  
## <a name="see-also"></a>Siehe auch
- [Treffertests in der visuellen Ebene](../../../../docs/framework/wpf/graphics-multimedia/hit-testing-in-the-visual-layer.md)
- [Vorgehensweise: Treffertest für eine Geometrie in einem visuellen Objekt](../../../../docs/framework/wpf/graphics-multimedia/how-to-hit-test-geometry-in-a-visual.md)
