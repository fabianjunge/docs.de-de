---
title: 'Vorgehensweise: Erstellen eines Workflowdiensts mit Messagingaktivitäten'
ms.date: 03/30/2017
ms.assetid: 53d094e2-6901-4aa1-88b8-024b27ccf78b
ms.openlocfilehash: a90f525e23fcad0e46ebc378d22b8282e613643a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54584976"
---
# <a name="how-to-create-a-workflow-service-with-messaging-activities"></a>Vorgehensweise: Erstellen eines Workflowdiensts mit Messagingaktivitäten
In diesem Thema wird beschrieben, wie Sie mithilfe der Messagingaktivitäten einen einfachen Workflowdienst erstellen. Der Schwerpunkt des Themas liegt auf der Mechanik zum Erstellen eines Workflowdiensts. Der Dienst besteht ausschließlich aus Messagingaktivitäten. In einem realen Dienst enthält der Workflow noch viele andere Aktivitäten. Der Dienst implementiert einen Vorgang mit dem Namen "Echo", der eine Zeichenfolge verwendet und diese an den Aufrufer zurückgibt. Dieses Thema ist das erste von zwei Themen, die zusammengehören. Im nächsten Thema [so wird's gemacht: Zugreifen auf einen Dienst aus einer Workflowanwendung](../../../../docs/framework/wcf/feature-details/how-to-access-a-service-from-a-workflow-application.md) wird erläutert, wie eine workflowanwendung erstellen, die den in diesem Thema erstellten Dienst aufrufen kann.  
  
### <a name="to-create-a-workflow-service-project"></a>So erstellen Sie ein Workflowdienstprojekt  
  
1.  Starten Sie Visual Studio 2012.  
  
2.  Klicken Sie auf die **Datei** , wählen Sie im Menü **neu**, und klicken Sie dann **Projekt** zum Anzeigen der **Dialogfeld "Neues Projekt"**. Wählen Sie **Workflow** aus der Liste der installierten Vorlagen und **WCF-Workflowdienstanwendung** aus der Liste der Projekttypen zur Verfügung. Nennen Sie das Projekt `MyWFService` und verwenden Sie den Standardspeicherort, wie in der folgenden Abbildung dargestellt.  
  
     Klicken Sie auf die **OK** Schaltfläche zum Schließen der **Dialogfeld "Neues Projekt"**.  
  
3.  Nachdem das Projekt erstellt wurde, wird die Datei "Service1.xamlx" im Designer geöffnet. Dies ist in der folgenden Abbildung dargestellt.  
  
     ![Im Designer angezeigte Standardworkflow](../../../../docs/framework/wcf/feature-details/media/defaultworkflowservice.JPG "DefaultWorkflowService")  
  
     Mit der rechten Maustaste in der Aktivität, die mit der Bezeichnung **sequenzieller Dienst** , und wählen Sie **löschen**.  
  
### <a name="to-implement-the-workflow-service"></a>So implementiert Sie den Workflowdienst  
  
1.  Wählen Sie die **Toolbox** Registerkarte auf der linken Seite des Bildschirms, um die Toolbox anzuzeigen, und klicken Sie auf das Pinsymbol, damit das Fenster geöffnet bleibt. Erweitern Sie die **Messaging** Abschnitt der Toolbox auf die messagingaktivitäten und die Vorlagen für messagingaktivitäten anzuzeigen, wie in der folgenden Abbildung dargestellt.  
  
     ![Erweitert die Toolbox mit](../../../../docs/framework/wcf/feature-details/media/wfdesignertoolbox.JPG "WFDesignerToolbox")  
  
2.  Drag & drop eine **ReceiveAndSendReply** Vorlage zum Workflow-Designer. Erstellt eine <xref:System.Activities.Statements.Sequence> Aktivität mit einer **empfangen** -Aktivität gefolgt von einer <xref:System.ServiceModel.Activities.SendReply> Aktivität, wie in der folgenden Abbildung dargestellt.  
  
     ![ReceiveAndSendReply-Vorlage im Designer](../../../../docs/framework/wcf/feature-details/media/receiveandsendreply.JPG "ReceiveAndSendReply")  
  
     Beachten Sie, dass die <xref:System.ServiceModel.Activities.SendReply>-Eigenschaft der <xref:System.ServiceModel.Activities.SendReply.Request%2A>-Aktivität auf `Receive` festgelegt ist, also auf den Namen der <xref:System.ServiceModel.Activities.Receive>-Aktivität, auf die die <xref:System.ServiceModel.Activities.SendReply>-Aktivität antwortet.  
  
3.  In der <xref:System.ServiceModel.Activities.Receive> Aktivitätstyp `Echo` in das Textfeld ein, die mit der Bezeichnung **OperationName**. Dadurch wird der Name des Vorgangs definiert, den der Dienst implementiert.  
  
     ![Geben Sie den Namen des Vorgangs](../../../../docs/framework/wcf/feature-details/media/defineoperation.JPG "DefineOperation")  
  
4.  Mit der <xref:System.ServiceModel.Activities.Receive> Aktivität ausgewählt haben, öffnen Sie das Fenster "Eigenschaften", wenn nicht bereits geöffnet, indem Sie auf die **Ansicht** Menü und auswählen **Fenster "Eigenschaften"**. In der **Fenster "Eigenschaften"** einen Bildlauf nach unten, bis Sie sehen **CanCreateInstance** , und klicken Sie auf das Kontrollkästchen, wie in der folgenden Abbildung dargestellt. Mit dieser Einstellung wird es dem Workflowdiensthost ermöglicht, (bei Bedarf) eine neue Instanz des Diensts zu erstellen, wenn eine Meldung empfangen wird.  
  
     ![CanCreateInstance-Eigenschaft](../../../../docs/framework/wcf/feature-details/media/cancreateinstance.JPG "CanCreateInstance")  
  
5.  Wählen Sie die <xref:System.Activities.Statements.Sequence> -Aktivität, und klicken Sie auf die **Variablen** Schaltfläche in der unteren linken Ecke des Designers. Der Variablen-Editor wird angezeigt. Klicken Sie auf die **Variable erstellen** Link, um eine Variable zum Speichern der Zeichenfolge gesendet, um den Vorgang hinzuzufügen. Benennen Sie die Variable `msg` und legen Sie dessen **Variable** Geben Sie in eine Zeichenfolge, wie in der folgenden Abbildung gezeigt.  
  
     ![Fügen Sie eine Variable](../../../../docs/framework/wcf/feature-details/media/addvariable.JPG "AddVariable")  
  
     Klicken Sie auf die **Variablen** Schaltfläche erneut aus, um den Variablen-Editor zu schließen.  
  
6.  Klicken Sie auf die **definieren...** -Link in der **Content** Textfeld in die <xref:System.ServiceModel.Activities.Receive> Aktivität zum Anzeigen der **Inhaltsdefinition** Dialogfeld. Wählen Sie die **Parameter** Optionsfeld, klicken Sie auf die **hinzufügen neuen Parameter** verknüpfen, geben Sie `inMsg` in die **Namen** wählen Sie im Text **Zeichenfolge**in die **Typ** Dropdown-Listenfeld, und geben `msg` in die **zuordnen zu** Textfeld wie in der folgenden Abbildung dargestellt.  
  
     ![Hinzufügen von Parameterinhalt](../../../../docs/framework/wcf/feature-details/media/parameterscontent.jpg "ParametersContent")  
  
     Dadurch wird angegeben, dass die Empfangsaktivität Zeichenfolgenparameter empfängt und dass diese Daten an die `msg`-Variable gebunden werden. Klicken Sie auf **OK** schließen die **Inhaltsdefinition** Dialogfeld.  
  
7.  Klicken Sie auf die **definieren...**  -link in der **Content** im Feld der <xref:System.ServiceModel.Activities.SendReply> Aktivität zum Anzeigen der **Inhaltsdefinition** Dialogfeld. Wählen Sie die **Parameter** Optionsfeld, klicken Sie auf die **hinzufügen neuen Parameter** verknüpfen, geben Sie `outMsg` in die **Namen** wählen Sie im Textfeld **Zeichenfolge**in die **Typ** im Dropdown-Listenfeld und `msg` in die **Wert** Textfeld wie in der folgenden Abbildung dargestellt.  
  
     ![Hinzufügen von Parameterinhalt](../../../../docs/framework/wcf/feature-details/media/parameterscontent2.jpg "ParametersContent2")  
  
     Dadurch wird angegeben, dass die <xref:System.ServiceModel.Activities.SendReply>-Aktivität eine Nachricht oder einen Nachrichtenvertragstyp sendet und dass die Daten an die `msg`-Variable gebunden werden. Da dies eine <xref:System.ServiceModel.Activities.SendReply>-Aktivität ist, werden die Daten von `msg` verwendet, um die von der Aktivität an den Client zurückgesendete Nachricht aufzufüllen. Klicken Sie auf **OK** schließen die **Inhaltsdefinition** Dialogfeld.  
  
8.  Speichern und erstellen Sie die Projektmappe, indem Sie auf die **erstellen** Menü und auswählen **Projektmappe**.  
  
## <a name="configure-the-workflow-service-project"></a>Konfigurieren des Workflowdienstprojekts  
 Der Workflowdienst wurde abgeschlossen. In diesem Abschnitt wird erklärt, wie Sie die Workflowdienstprojektmappe so konfigurieren, dass sie auf einfache Weise gehostet und ausgeführt werden kann. Diese Projektmappe verwendet den ASP.NET Development Server zum Hosten des Diensts.  
  
#### <a name="to-set-project-start-up-options"></a>So legen Sie Projektstartoptionen fest  
  
1.  In der **Projektmappen-Explorer**, mit der rechten Maustaste **MyWFService** , und wählen Sie **Eigenschaften** zum Anzeigen der **Projekteigenschaften** Dialogfeld.  
  
2.  Wählen Sie die **Web** Registerkarte, und wählen Sie **bestimmte Seite** unter **Startaktion** und `Service1.xamlx` in das Textfeld ein, wie in der folgenden Abbildung dargestellt.  
  
     ![Das Dialogfeld mit Projekteigenschaften](../../../../docs/framework/wcf/feature-details/media/projectpropertiesdlg.JPG "ProjectPropertiesDlg")  
  
     Der in "Service1.xamlx" definierte Dienst wird dann unter ASP.NET Development Server gehostet.  
  
3.  Drücken Sie STRG+F5, um den Dienst zu starten. Das Symbol "ASP.NET Development Server" wird in der unteren rechten Ecke des Desktops angezeigt. Dies ist in der folgenden Abbildung dargestellt.  
  
     ![Das Serversymbol ASP.NET-Entwickler](../../../../docs/framework/wcf/feature-details/media/aspnetdevservericon.JPG "ASPNETDEVServerIcon")  
  
     Außerdem zeigt Internet Explorer für den Dienst die Hilfeseite für WCF-Dienste an.  
  
     ![WCF-Hilfeseite](../../../../docs/framework/wcf/feature-details/media/wcfhelppate.JPG "WCFHelpPate")  
  
4.  Fortfahren mit der [Vorgehensweise: Zugreifen auf einen Dienst aus einer Workflowanwendung](../../../../docs/framework/wcf/feature-details/how-to-access-a-service-from-a-workflow-application.md) Thema, um einen workflowclient zu erstellen, die diesen Dienst aufruft.  
  
## <a name="see-also"></a>Siehe auch
- [Workflowdienste](../../../../docs/framework/wcf/feature-details/workflow-services.md)
- [Übersicht über das Hosten von Workflowdiensten](../../../../docs/framework/wcf/feature-details/hosting-workflow-services-overview.md)
- [Messagingaktivitäten](../../../../docs/framework/wcf/feature-details/messaging-activities.md)
