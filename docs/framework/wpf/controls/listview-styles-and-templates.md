---
title: ListView-Stile und -Vorlagen
ms.date: 03/30/2017
helpviewer_keywords:
- parts [WPF], ListView
- states [WPF], ListView
- ControlTemplate [WPF], ListView
- styles [WPF], ListView
- ListView [WPF], styles and templates
- templates [WPF], ListView
ms.assetid: d2387356-2171-4785-822a-7247e024b4ee
ms.openlocfilehash: 66e9f5d45a4c9b3a04291a8ebbf054ebc055b5a2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54643636"
---
# <a name="listview-styles-and-templates"></a>ListView-Stile und -Vorlagen
In diesem Thema wird beschrieben, die Stile und Vorlagen für die <xref:System.Windows.Controls.ListView> Steuerelement. Sie können den Standardwert ändern <xref:System.Windows.Controls.ControlTemplate> auf dem Steuerelement eine unverwechselbare Darstellung verleihen. Weitere Informationen finden Sie unter [Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).  
  
## <a name="listview-parts"></a>ListView-Komponenten  
 Die <xref:System.Windows.Controls.ListView> Steuerelement enthält keine benannten Teile.  
  
 Bei der Erstellung einer <xref:System.Windows.Controls.ControlTemplate> für eine <xref:System.Windows.Controls.ListView>, Ihrer Vorlage enthalten möglicherweise ein <xref:System.Windows.Controls.ItemsPresenter> innerhalb einer <xref:System.Windows.Controls.ScrollViewer>. (Die <xref:System.Windows.Controls.ItemsPresenter> stellt jedes Element in der <xref:System.Windows.Controls.ListView>; die <xref:System.Windows.Controls.ScrollViewer> ermöglicht das Scrollen innerhalb des Steuerelements).  Wenn die <xref:System.Windows.Controls.ItemsPresenter> ist kein direkte untergeordnetes Element von der <xref:System.Windows.Controls.ScrollViewer>, geben Sie die <xref:System.Windows.Controls.ItemsPresenter> den Namen, `ItemsPresenter`.  
  
## <a name="listview-states"></a>ListView-Status  
 Die folgende Tabelle enthält die visuellen Zustände für die <xref:System.Windows.Controls.ListView> Steuerelement.  
  
|VisualState-Name|VisualStateGroup-Name|Beschreibung|  
|-|-|-|  
|Gültig|ValidationStates|Das Steuerelement verwendet die <xref:System.Windows.Controls.Validation> Klasse und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `false`.|  
|InvalidFocused|ValidationStates|Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement den Fokus besitzt.|  
|InvalidUnfocused|ValidationStates|Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement keinen Fokus besitzt.|  
  
## <a name="listviewitem-parts"></a>ListViewItem Teilen  
 Die <xref:System.Windows.Controls.ListViewItem> Steuerelement enthält keine benannten Teile.  
  
## <a name="listviewitem-states"></a>ListViewItem-Zustände  
 Die folgende Tabelle enthält die Zustände für die <xref:System.Windows.Controls.ListViewItem> Steuerelement.  
  
|VisualState-Name|VisualStateGroup-Name|Beschreibung|  
|-|-|-|  
|Normal|CommonStates|Der Standardzustand|  
|Deaktiviert|CommonStates|Das Steuerelement ist deaktiviert.|  
|MouseOver|CommonStates|Der Mauszeiger befindet, über die <xref:System.Windows.Controls.ComboBox> Steuerelement.|  
|Focused|FocusStates|Der Fokus liegt auf dem Steuerelement.|  
|Ohne Fokus|FocusStates|Der Fokus liegt nicht auf dem Steuerelement.|  
|Ausgewählt|SelectionStates|Derzeit ist das Element ausgewählt.|  
|Nicht markiert|SelectionStates|Das Element ist nicht ausgewählt.|  
|SelectedUnfocused|SelectionStates|Das Element ist ausgewählt, besitzt jedoch keinen Fokus.|  
|Gültig|ValidationStates|Das Steuerelement verwendet die <xref:System.Windows.Controls.Validation> Klasse und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `false`.|  
|InvalidFocused|ValidationStates|Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement den Fokus besitzt.|  
|InvalidUnfocused|ValidationStates|Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement keinen Fokus besitzt.|  
  
## <a name="listview-controltemplate-examples"></a>ListView-ControlTemplate-Beispiele  
 Das folgende Beispiel zeigt, wie Sie definieren eine <xref:System.Windows.Controls.ControlTemplate> für die <xref:System.Windows.Controls.ListView> -Steuerelement und seine zugehörigen Typen.  
  
 [!code-xaml[ControlTemplateExamples#ListView](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/listview.xaml#listview)]  
  
 Die <xref:System.Windows.Controls.ControlTemplate> Beispiele verwenden eine oder mehrere der folgenden Ressourcen.  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 Das vollständige Beispiel finden Sie unter [Beispiel zum Formatieren mit ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [Steuerelementformate und -vorlagen](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)
- [Anpassung von Steuerelementen](../../../../docs/framework/wpf/controls/control-customization.md)
- [Erstellen von Formaten und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md)
- [Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
