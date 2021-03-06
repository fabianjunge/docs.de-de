---
title: Offizielle .NET-Docker-Images
description: .NET-Microservicesarchitektur für .NET-Containeranwendungen | Offizielle .NET-Docker-Images
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/11/2018
ms.openlocfilehash: c1948693edbc197b8527ce8ce82c196206a16876
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53131377"
---
# <a name="official-net-docker-images"></a>Offizielle .NET-Docker-Images

Die offiziellen .NET-Docker-Images sind Docker-Images, die von Microsoft erstellt und optimiert werden. Sie sind öffentlich in den Microsoft-Repositorys im [Docker-Hub](https://hub.docker.com/u/microsoft/) verfügbar. Jedes Repository kann je nach .NET-Version und der Version des Betriebssystems mehrere Images enthalten (Linux Debian, Alpine Linux, Windows Nano Server, Windows Server Core usw.).

Seit .NET Core 2.1 stehen alle .NET Core-Images – auch für ASP.NET Core – auf Docker Hub im .NET Core-Image-Repository zur Verfügung: https://hub.docker.com/r/microsoft/dotnet/

Die meisten Image-Repositorys stellen umfangreiche Taggingfunktionen bereit, die Sie nicht nur bei der Auswahl einer bestimmten Frameworkversion unterstützen, sondern auch bei der des Betriebssystems (Linux-Distribution oder Windows-Version).

## <a name="net-core-and-docker-image-optimizations-for-development-versus-production"></a>.NET Core- und Docker-Imageoptimierungen für die Entwicklung und die Produktion

Beim Erstellen von Docker-Images für Entwickler standen für Microsoft die folgenden wichtigen Szenarios im Mittelpunkt:

-   Images zum *Entwickeln* und Erstellen von .NET Core-Apps

-   Images zum *Ausführen* von .NET Core-Apps

Warum mehrere Images? Beim Entwickeln, Erstellen und Ausführen von Containeranwendungen gibt es üblicherweise unterschiedliche Prioritäten. Durch das Bereitstellen verschiedener Images leistet Microsoft einen Beitrag zur Optimierung der separaten Prozesse des Entwickelns, Erstellens und Bereitstellens von Apps.

### <a name="during-development-and-build"></a>Während der Entwicklung und Erstellung

In der Entwicklungsphase zählt, wie schnell Sie Änderungen durchlaufen und Änderungen debuggen können. Die Größe des Images ist nicht so entscheidend wie die Fähigkeit, Änderungen am Code vorzunehmen und schnell anzuzeigen. Einige Tools und „Build-Agent-Container“ verwenden das .NET Core-Entwicklungsimage (*microsoft/dotnet:2.1-sdk*) während der Entwicklung und des Buildprozesses. Wenn Sie innerhalb eines Docker-Containers programmieren, sind die Elemente, die zum Kompilieren der App benötigt werden, das Wichtigste. Das schließt den Compiler und alle anderen .NET-Abhängigkeiten ein.

Warum ist diese Art von Buildimage wichtig? Dieses Image wird nie in einer Produktionsumgebung bereitgestellt. Damit wird ausschließlich der Inhalt erstellt, den Sie in einem Produktionsimage platzieren. Dieses Image wird dann bei Verwendung mehrstufiger Docker-Builds in der Continuous Integration- oder Buildumgebung verwendet.

### <a name="in-production"></a>In einer Produktionsumgebung

In der Produktion ist wichtig, wie schnell Sie bereitstellen und die Container basierend auf einem Produktions-.NET Core-Image starten können. Das Image, das auf *microsoft/dotnet:2.1-aspnetcore-runtime* basiert und nur die Runtime enthält, ist aus diesem Grund klein: damit es von der Docker-Registrierung schnell über das Netzwerk an die Docker-Hosts übertragen werden kann. Die Inhalte sind bereit zur Ausführung und ermöglichen eine minimale Zeitspanne zwischen dem Start des Containers und dem Verarbeiten der Ergebnisse. Anders als bei „dotnet build“ oder „dotnet publish“ beim Verwenden des Buildcontainers besteht im Docker-Modell keine Notwendigkeit, C\#-Code zu kompilieren.

In diesem optimierten Image werden nur die Binärdateien und andere Inhalte platziert, die zum Ausführen der Anwendung erforderlich sind. Der von „dotnet publish“ erstellte Inhalt enthält z.B. nur die kompilierten .NET-Binärdateien, Images sowie JS- und CSS-Dateien. Im Lauf der Zeit werden Sie Images bemerken, die vorab JIT-kompiliert wurden (die Kompilierung von IL zu nativ, die zur Laufzeit erfolgt).

Obwohl mehrere Versionen der .NET Core- und ASP.NET Core-Images verfügbar sind, haben sie alle mindestens eine Ebene gemeinsam, einschließlich der Grundebene. Aus diesem Grund ist wenig Speicherplatz erforderlich, um ein Image zu speichern, denn es besteht nur aus dem Delta zwischen dem benutzerdefinierten Image und dem Basisimage. So können Sie das Image schnell aus der Registrierung abrufen.

Wenn Sie sich die .NET-Image-Repositorys im Docker-Hub ansehen, werden Sie mehrere Imageversionen finden, die klassifiziert oder mit Tags versehen sind. Diese Tags helfen dabei, je nach benötigter Version zu entscheiden, welches Image verwendet werden sollte, so wie in der folgenden Tabelle:

| Bild                                       | Kommentare                                                                                          |
| ------------------------------------------- | ------------------------------------------------------------------------------------------------- |
| microsoft/dotnet:**2.1-aspnetcore-runtime** | ASP.NET Core mit Optimierungen nur für die Runtime und ASP.NET Core unter Linux und Windows (Mehrfacharchitektur) |
| microsoft/dotnet:**2.1-sdk**                | .NET Core mit enthaltenen SDKs unter Linux und Windows (Mehrfacharchitektur)                                  |

>[!div class="step-by-step"]
>[Zurück](net-container-os-targets.md)
>[Weiter](../architect-microservice-container-applications/index.md)