---
title: Dienstidentitätsbeispiel
ms.date: 03/30/2017
ms.assetid: 79fa8c1c-85bb-4b67-bc67-bfaf721303f8
ms.openlocfilehash: 1efa354f62e1b28ad6cec02d9879448205791e4a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54707634"
---
# <a name="service-identity-sample"></a>Dienstidentitätsbeispiel
Dieses Dienstidentitätsbeispiel veranschaulicht das Festlegen der Identität eines Diensts. Während der Entwurfszeit kann ein Client die Identität mithilfe der Metadaten des Diensts abrufen und zur Laufzeit die Identität des Diensts authentifizieren. Das Konzept der Dienstidentität besteht darin, dass ein Client einen Dienst authentifizieren kann, bevor er einen seiner Vorgänge aufruft. Auf diese Weise wird der Client vor nicht authentifizierten Aufrufen geschützt. Bei einer sicheren Verbindung authentifiziert der Dienst auch die Anmeldeinformationen eines Clients, bevor er diesem Zugriff gewährt. Diese Funktion steht jedoch nicht im Mittelpunkt dieses Beispiels. Finden Sie in die Beispielen in [Client](../../../../docs/framework/wcf/samples/client.md) anzugeben, dass die Server-Authentifizierung.

> [!NOTE]
>  Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.

 In diesem Beispiel werden die folgenden Funktionen veranschaulicht:

-   Wie die verschiedenen Identitätstypen auf unterschiedlichen Endpunkten zu einem Dienst festgelegt werden. Jeder Identitätstyp hat andere Funktionen. Der zu verwendende Identitätstyp ist vom Typ der Sicherheitsanmeldeinformationen abhängig, die bei der Bindung des Endpunkts verwendet werden.

-   Die Identität kann entweder deklarativ in der Konfiguration oder imperativ im Code festgelegt werden. In der Regel sollten Sie sowohl für den Client als auch für den Dienst die Konfiguration verwenden, um die Identität festzulegen.

-   Gewusst wie: Festlegen einer benutzerdefinierten Identität für den Client Eine benutzerdefinierte Identität ist normalerweise eine Anpassung eines vorhandenen Identitätstyps, mit dem ein Client andere in den Dienstanmeldeinformationen enthaltene Anspruchsinformationen überprüfen kann. Auf diese Weise können Autorisierungsentscheidungen getroffen werden, bevor der Dienst aufgerufen wird.

    > [!NOTE]
    >  Dieses Beispiel überprüft die Identität eines Zertifikats mit der Bezeichnung "identity.com" und den RSA-Schlüssel in diesem Zertifikat. Wenn Sie die Identitätstypen "Zertifikat" und "RSA" in der Konfiguration des Clients verwenden, können diese Werte problemlos durch das Überprüfen des WSDL für den Dienst abgerufen werden, auf dem diese Werte serialisiert sind.

 Der folgende Beispielcode zeigt, wie Sie mit "WSHttpBinding" die Identität eines Dienstendpunkts mit dem DNS (Domain Name Server) eines Zertifikats konfigurieren.

```csharp
//Create a service endpoint and set its identity to the certificate's DNS
WSHttpBinding wsAnonbinding = new WSHttpBinding (SecurityMode.Message);
// Client are Anonymous to the service
wsAnonbinding.Security.Message.ClientCredentialType = MessageCredentialType.None;
WServiceEndpoint ep = serviceHost.AddServiceEndpoint(typeof(ICalculator),wsAnonbinding, String.Empty);
EndpointAddress epa = new EndpointAddress(dnsrelativeAddress,EndpointIdentity.CreateDnsIdentity("identity.com"));
ep.Address = epa;
```

 Die Identität kann auch in der Konfiguration der Datei "App.config" angegeben werden. Im folgenden Beispiel wird gezeigt, wie die UPN-Identität (User Principal Name) für einen Dienstendpunkt festgelegt wird.

```xml
<endpoint address="upnidentity"
        behaviorConfiguration=""
        binding="wsHttpBinding"
        bindingConfiguration="WSHttpBinding_Windows"
        name="WSHttpBinding_ICalculator_Windows"
        contract="Microsoft.ServiceModel.Samples.ICalculator">
  <!-- Set the UPN identity for this endpoint -->
  <identity>
      <userPrincipalName value="host\myservice.com" />
  </identity >
</endpoint>
```

 Eine benutzerdefinierte Identität kann durch Ableiten von den <xref:System.ServiceModel.EndpointIdentity>- und <xref:System.ServiceModel.Security.IdentityVerifier>-Klassen auf dem Client eingerichtet werden. Im Prinzip kann die <xref:System.ServiceModel.Security.IdentityVerifier>-Klasse als Cliententsprechung der `AuthorizationManager`-Klasse des Diensts betrachtet werden. Im folgenden Codebeispiel wird eine Implementierung von `OrgEndpointIdentity` veranschaulicht. Hier wird der Name einer Organisation gespeichert, der mit dem Antragstellernamen des Serverzertifikats verglichen wird. Die Autorisierungsprüfung des Organisationsnamens findet in der `CheckAccess`-Methode der `CustomIdentityVerifier`-Klasse statt.

```csharp
// This custom EndpointIdentity stores an organization name
public class OrgEndpointIdentity : EndpointIdentity
{
    private string orgClaim;
    public OrgEndpointIdentity(string orgName)
    {
        orgClaim = orgName;
    }
    public string OrganizationClaim
    {
        get { return orgClaim; }
        set { orgClaim = value; }
    }
}

//This custom IdentityVerifier uses the supplied OrgEndpointIdentity to
//check that X.509 certificate's distinguished name claim contains
//the organization name e.g. the string value "O=Contoso"
class CustomIdentityVerifier : IdentityVerifier
{
    public override bool CheckAccess(EndpointIdentity identity, AuthorizationContext authContext)
    {
        bool returnvalue = false;
        foreach (ClaimSet claimset in authContext.ClaimSets)
        {
            foreach (Claim claim in claimset)
            {
                if (claim.ClaimType == "http://schemas.microsoft.com/ws/2005/05/identity/claims/x500distinguishedname")
                {
                    X500DistinguishedName name = (X500DistinguishedName)claim.Resource;
                    if (name.Name.Contains(((OrgEndpointIdentity)identity).OrganizationClaim))
                    {
                        Console.WriteLine("Claim Type: {0}",claim.ClaimType);
                        Console.WriteLine("Right: {0}", claim.Right);
                        Console.WriteLine("Resource: {0}",claim.Resource);
                        Console.WriteLine();
                        returnvalue = true;
                    }
                }
            }
        }
        return returnvalue;
    }
}
```

 In diesem Beispiel wird ein Zertifikat namens "identity.com" verwendet, das sich im sprachspezifischen Identitätsprojektmappenordner befindet.

### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen

1.  Stellen Sie sicher, dass Sie ausgeführt haben die [Schritte der Einrichtung einmaligen Setupverfahren für Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).

2.  Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.

3.  Folgen Sie den Anweisungen, um das Beispiel in einer Konfiguration für die einzelnen-Computer oder computerübergreifend auszuführen, [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).

### <a name="to-run-the-sample-on-the-same-computer"></a>So führen Sie das Beispiel auf demselben Computer aus

1.  Importieren Sie unter [!INCLUDE[wxp](../../../../includes/wxp-md.md)] oder [!INCLUDE[wv](../../../../includes/wv-md.md)] die Zertifikatdatei Identity.pfx im Identitätsprojektmappenordner mithilfe des MMC-Snap-In-Tools in den Zertifikatspeicher LocalMachine/Mein (persönlicher) Zertifikatspeicher. Diese Datei ist durch ein Kennwort geschützt. Während des Imports werden Sie um ein Kennwort gebeten. Typ `xyz` in das Kennwortfeld. Weitere Informationen finden Sie unter [How to: Anzeigen von Zertifikaten mit dem MMC-Snap-in](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md) Thema. Sobald dies geschehen ist, führen Sie "Setup.bat" im Developer-Eingabeaufforderung für Visual Studio mit Administratorrechten aus, die dieses Zertifikat in den Speicher CurrentUser/vertrauenswürdige Personen, für die Verwendung auf dem Client kopiert.

2.  Auf [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)], führen Sie Setup.bat aus dem beispielinstallationsordner innerhalb einer Visual Studio 2012-Eingabeaufforderung mit Administratorrechten aus. Hiermit werden alle Zertifikate installiert, die zum Ausführen des Beispiels erforderlich sind.

    > [!NOTE]
    >  Die Batchdatei "Setup.bat" wird aus einer Visual Studio 2012-Eingabeaufforderung ausgeführt werden soll. Die PATH-Umgebungsvariable festgelegt in der Visual Studio 2012-Eingabeaufforderung verweist auf das Verzeichnis mit ausführbaren Dateien, die durch das Skript Setup.bat erforderlich sind. Wenn Sie mit dem Beispiel fertig sind, müssen Sie die Datei Cleanup.bat ausführen, um die Zertifikate zu entfernen. In anderen Sicherheitsbeispielen werden die gleichen Zertifikate verwendet.  
  
3.  Starten Sie "Service.exe" aus dem Verzeichnis "\service\bin". Stellen Sie sicher, dass der Dienst ist bereit und zeigt eine Eingabeaufforderung drücken \<Eingabetaste > um den Dienst zu beenden.  
  
4.  Starten Sie "Client.exe" aus dem Verzeichnis "\client\bin" oder durch das Drücken der Taste F5 in Visual Studio zum Erstellen und Ausführen. In der Clientkonsolenanwendung wird Clientaktivität angezeigt.  
  
5.  Wenn der Client und der Dienst nicht kommunizieren können, finden Sie weitere Informationen unter [Troubleshooting Tips](https://msdn.microsoft.com/library/8787c877-5e96-42da-8214-fa737a38f10b).  
  
### <a name="to-run-the-sample-across-computers"></a>So führen Sie das Beispiel computerübergreifend aus  
  
1.  Bevor Sie die Clientseite des Beispiels erstellen, müssen Sie den Wert der Dienstendpunktadresse in der Datei Client.cs in der `CallServiceCustomClientIdentity`-Methode ändern. Erstellen Sie anschließend das Beispiel.  
  
2.  Erstellen Sie auf dem Dienstcomputer ein Verzeichnis.  
  
3.  Kopieren Sie die Dienstprogrammdateien aus service\bin in das Verzeichnis auf dem Dienstcomputer. Kopieren Sie außerdem die Dateien Setup.bat und Cleanup.bat auf den Dienstcomputer.  
  
4.  Erstellen Sie auf dem Clientcomputer ein Verzeichnis für die Clientbinärdateien.  
  
5.  Kopieren Sie die Clientprogrammdateien in das Clientverzeichnis auf dem Clientcomputer. Kopieren Sie die Dateien "Setup.bat", "Cleanup.bat" und "ImportServiceCert.bat" ebenfalls auf den Client.  
  
6.  Führen Sie auf den Dienst `setup.bat service` in einer Developer-Eingabeaufforderung für Visual Studio mit Administratorrechten geöffnet. Ausführung `setup.bat` mit der `service` Argument wird ein Dienstzertifikat mit dem vollqualifizierten Domänennamen des Computers erstellt und das Dienstzertifikat in die Datei Service.cer exportiert.  
  
7.  Kopieren Sie die Datei Service.cer aus dem Dienstverzeichnis in das Clientverzeichnis auf dem Clientcomputer.  
  
8.  Ändern Sie in der Datei Client.exe.config auf dem Clientcomputer den Wert für die Adresse des Endpunkts, sodass er mit der neuen Adresse Ihres Diensts übereinstimmt. Es gibt mehrere Instanzen, die geändert werden müssen.  
  
9. Führen Sie auf dem Client importservicecert.bat aus in einer Developer-Eingabeaufforderung für Visual Studio mit Administratorrechten geöffnet. Dadurch wird das Dienstzertifikat aus der Datei Service.cer in den Speicher CurrentUser – TrustedPeople importiert.  
  
10. Starten Sie auf dem Dienstcomputer Service.exe an einer Eingabeaufforderung.  
  
11. Starten Sie auf dem Clientcomputer Client.exe an einer Eingabeaufforderung. Wenn der Client und der Dienst nicht kommunizieren können, finden Sie weitere Informationen unter [Troubleshooting Tips](https://msdn.microsoft.com/library/8787c877-5e96-42da-8214-fa737a38f10b).  
  
### <a name="to-clean-up-after-the-sample"></a>So stellen Sie den Zustand vor Ausführung des Beispiels wieder her  
  
-   Führen Sie Cleanup.bat im Beispielordner aus, nachdem Sie das Beispiel fertig ausgeführt haben.  
  
    > [!NOTE]
    >  Wenn dieses Beispiel computerübergreifend ausgeführt wird, entfernt dieses Skript keine Dienstzertifikate auf einem Client. Wenn Sie Windows Communication Foundation (WCF)-Beispiele, die Zertifikate computerübergreifend verwenden ausgeführt haben, achten Sie darauf, dass Sie die Dienstzertifikate entfernen, die in den Speicher CurrentUser – trustedpeople installiert wurden. Zu diesem Zweck verwenden Sie den folgenden Befehl aus: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` Zum Beispiel: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.

## <a name="see-also"></a>Siehe auch
