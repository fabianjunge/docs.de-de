---
title: Erstellen einer App für eine Spielerrangliste anhand der Auswertung von Spielpartien mit Infer.NET und probabilistischer Programmierung
description: Finden Sie heraus, wie Sie die probabilistische Programmierung mit Infer.NET verwenden können, um eine App für eine Spielerrangliste anhand der Auswertung von Spielpartien zu erstellen, die auf einer vereinfachten Version von TrueSkill basiert.
ms.date: 10/04/2018
ms.topic: how-to
ms.custom: mvc
ms.openlocfilehash: 990fd60d809c893730bf2682946f89dbe59f36a5
ms.sourcegitcommit: 8c28ab17c26bf08abbd004cc37651985c68841b8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2018
ms.locfileid: "49401696"
---
# <a name="create-a-game-match-up-list-app-with-infernet-and-probabilistic-programming"></a><span data-ttu-id="02029-103">Erstellen einer App für eine Spielerrangliste anhand der Auswertung von Spielpartien mit Infer.NET und probabilistischer Programmierung</span><span class="sxs-lookup"><span data-stu-id="02029-103">Create a game match up list app with Infer.NET and probabilistic programming</span></span>

<span data-ttu-id="02029-104">In dieser Schrittanleitung erfahren Sie mehr zur probabilistischen Programmierung mithilfe von Infer.NET.</span><span class="sxs-lookup"><span data-stu-id="02029-104">This how-to guide teaches you about probabilistic programming using Infer.NET.</span></span> <span data-ttu-id="02029-105">Die probabilistische Programmierung ist ein Ansatz des maschinellen Lernens, bei dem benutzerdefinierte Modelle als Computerprogramme ausgedrückt werden.</span><span class="sxs-lookup"><span data-stu-id="02029-105">Probabilistic programming is a machine learning approach where custom models are expressed as computer programs.</span></span> <span data-ttu-id="02029-106">Dieser Ansatz ermöglicht es, Wissen auf einem bestimmten Fachgebiet in die Modelle zu integrieren, und sorgt dafür, dass sich das System für maschinelles Lernen besser interpretieren lässt.</span><span class="sxs-lookup"><span data-stu-id="02029-106">It allows for incorporating domain knowledge in the models and makes the machine learning system more interpretable.</span></span> <span data-ttu-id="02029-107">Der Ansatz unterstützt auch direkte Rückschlüsse – also den Prozess des Lernens beim Eintreffen neuer Daten.</span><span class="sxs-lookup"><span data-stu-id="02029-107">It also supports online inference – the process of learning as new data arrives.</span></span> <span data-ttu-id="02029-108">Infer.NET wird in verschiedenen Microsoft-Produkten in Azure, Xbox und Bing eingesetzt.</span><span class="sxs-lookup"><span data-stu-id="02029-108">Infer.NET is used in various products at Microsoft in Azure, Xbox, and Bing.</span></span>

## <a name="what-is-probabilistic-programming"></a><span data-ttu-id="02029-109">Was ist die probabilistische Programmierung?</span><span class="sxs-lookup"><span data-stu-id="02029-109">What is probabilistic programming?</span></span> 

<span data-ttu-id="02029-110">Mit der probabilistischen Programmierung können wir statistische Modelle aus Prozessen der realen Welt erstellen.</span><span class="sxs-lookup"><span data-stu-id="02029-110">Probabilistic programming allows us to create statistical models of real-world processes.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="02029-111">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="02029-111">Prerequisites</span></span>

- <span data-ttu-id="02029-112">Einrichten der lokalen Entwicklungsumgebung</span><span class="sxs-lookup"><span data-stu-id="02029-112">Local development environment setup</span></span>

  <span data-ttu-id="02029-113">Für diese Schrittanleitung wird vorausgesetzt, dass Sie über einen Computer verfügen, den Sie für die Entwicklung nutzen können.</span><span class="sxs-lookup"><span data-stu-id="02029-113">This how-to guide expects you to have a machine you can use for development.</span></span> <span data-ttu-id="02029-114">Das [.NET-Tutorial](https://www.microsoft.com/net/core) für den Einstieg in 10 Minuten bietet Anleitungen zum Einrichten Ihrer lokalen Entwicklungsumgebung auf einem Mac-, Windows- oder Linux-Computer.</span><span class="sxs-lookup"><span data-stu-id="02029-114">The .NET [Get Started in 10 minutes](https://www.microsoft.com/net/core) tutorial has instructions for setting up your local development environment on Mac, PC, or Linux.</span></span>

## <a name="create-your-app"></a><span data-ttu-id="02029-115">Erstellen der App</span><span class="sxs-lookup"><span data-stu-id="02029-115">Create your app</span></span>

1. <span data-ttu-id="02029-116">Öffnen Sie eine neue Eingabeaufforderung, und führen Sie die folgenden Befehle aus:</span><span class="sxs-lookup"><span data-stu-id="02029-116">Open a new command prompt and run the following commands:</span></span>

```console
dotnet new console -o myApp
cd myApp
```

<span data-ttu-id="02029-117">Der `dotnet`-Befehl erstellt eine `new`-Anwendung des Typs `console`.</span><span class="sxs-lookup"><span data-stu-id="02029-117">The `dotnet` command creates a `new` application of type `console`.</span></span> <span data-ttu-id="02029-118">Der `-o`-Parameter erstellt ein Verzeichnis namens `myApp`, in dem Ihre App gespeichert wird, und füllt es mit den erforderlichen Dateien auf.</span><span class="sxs-lookup"><span data-stu-id="02029-118">The `-o` parameter creates a directory named `myApp` where your app is stored and populates it with the required files.</span></span> <span data-ttu-id="02029-119">Mit dem `cd myApp`-Befehl wechseln Sie in das neu erstellte App-Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="02029-119">The `cd myApp` command puts you into the newly created app directory.</span></span>

## <a name="install-infernet-package"></a><span data-ttu-id="02029-120">Installieren des Infer.NET-Pakets</span><span class="sxs-lookup"><span data-stu-id="02029-120">Install Infer.NET package</span></span>

<span data-ttu-id="02029-121">Um Infer.NET verwenden zu können, müssen Sie das `Microsoft.ML.Probabilistic.Compiler`-Paket installieren.</span><span class="sxs-lookup"><span data-stu-id="02029-121">To use Infer.NET, you need to install the `Microsoft.ML.Probabilistic.Compiler` package.</span></span> <span data-ttu-id="02029-122">Führen Sie an der Eingabeaufforderung folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="02029-122">In your command prompt, run the following command:</span></span>

```console
dotnet add package Microsoft.ML.Probabilistic.Compiler
```

## <a name="design-your-model"></a><span data-ttu-id="02029-123">Entwerfen des Modells</span><span class="sxs-lookup"><span data-stu-id="02029-123">Design your model</span></span>

<span data-ttu-id="02029-124">Das Beispiel verwendet Tischtennis- oder Fußballspiele, die im Büro ausgetragen wurden.</span><span class="sxs-lookup"><span data-stu-id="02029-124">The example sample uses table tennis or foosball matches played in the office.</span></span> <span data-ttu-id="02029-125">Wir kennen die Teilnehmer und das Ergebnis jedes Spiels.</span><span class="sxs-lookup"><span data-stu-id="02029-125">We have the participants and outcome of each match.</span></span>  <span data-ttu-id="02029-126">Aus diesen Daten möchten wir die Fähigkeiten jedes Spielers ableiten.</span><span class="sxs-lookup"><span data-stu-id="02029-126">We want to infer the player's skills from this data.</span></span> <span data-ttu-id="02029-127">Wir nehmen an, dass die latenten Fähigkeiten jedes Spielers normal verteilt sind und dass die Leistung in einem bestimmten Spiel eine abweichende Version dieser Fähigkeiten darstellt.</span><span class="sxs-lookup"><span data-stu-id="02029-127">We’ll assume that each player has a normally distributed latent skill and their performance in a given match is a noisy version of this skill.</span></span> <span data-ttu-id="02029-128">Die Daten legen nahe, dass die Leistung des Gewinners besser ist als die Leistung des Verlierers.</span><span class="sxs-lookup"><span data-stu-id="02029-128">The data constrains the winner’s performance to be greater than the loser’s performance.</span></span> <span data-ttu-id="02029-129">Dies ist eine vereinfachte Version des beliebten [TrueSkill](https://www.microsoft.com/en-us/research/project/trueskill-ranking-system/)-Modells, das auch Teams, Unentschieden und andere Erweiterungen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="02029-129">This is a simplified version of the popular [TrueSkill](https://www.microsoft.com/en-us/research/project/trueskill-ranking-system/) model, which also supports teams, draws, and other extensions.</span></span> <span data-ttu-id="02029-130">Eine [erweiterte Version](https://www.microsoft.com/en-us/research/publication/trueskill-2-improved-bayesian-skill-rating-system/) dieses Modells wird für die Spielergebnisse in den sehr erfolgreichen Spielen „Halo“ und „Gears of War“ verwendet.</span><span class="sxs-lookup"><span data-stu-id="02029-130">An [advanced version](https://www.microsoft.com/en-us/research/publication/trueskill-2-improved-bayesian-skill-rating-system/) of this model is used for matchmaking in the best-selling game titles Halo and Gears of War.</span></span>

<span data-ttu-id="02029-131">Wir müssen die abgeleiteten Fähigkeiten jedes Spielers sowie die Varianz auflisten – das Maß für Ungewissheit in Bezug auf die Fähigkeiten.</span><span class="sxs-lookup"><span data-stu-id="02029-131">We need to list the inferred player skills, alongside with their variance – the measure of uncertainty around the skills.</span></span>

<span data-ttu-id="02029-132">*Beispieldaten für Spielergebnisse*</span><span class="sxs-lookup"><span data-stu-id="02029-132">*Game result sample data*</span></span>

<span data-ttu-id="02029-133">Spiel</span><span class="sxs-lookup"><span data-stu-id="02029-133">Game</span></span> |<span data-ttu-id="02029-134">Gewinner</span><span class="sxs-lookup"><span data-stu-id="02029-134">Winner</span></span> | <span data-ttu-id="02029-135">Verlierer</span><span class="sxs-lookup"><span data-stu-id="02029-135">Loser</span></span>
---------|----------|---------
 <span data-ttu-id="02029-136">1</span><span class="sxs-lookup"><span data-stu-id="02029-136">1</span></span> | <span data-ttu-id="02029-137">Spieler 0</span><span class="sxs-lookup"><span data-stu-id="02029-137">Player 0</span></span> | <span data-ttu-id="02029-138">Spieler 1</span><span class="sxs-lookup"><span data-stu-id="02029-138">Player 1</span></span>
 <span data-ttu-id="02029-139">2</span><span class="sxs-lookup"><span data-stu-id="02029-139">2</span></span> | <span data-ttu-id="02029-140">Spieler 0</span><span class="sxs-lookup"><span data-stu-id="02029-140">Player 0</span></span> | <span data-ttu-id="02029-141">Spieler 3</span><span class="sxs-lookup"><span data-stu-id="02029-141">Player 3</span></span>
 <span data-ttu-id="02029-142">3</span><span class="sxs-lookup"><span data-stu-id="02029-142">3</span></span> | <span data-ttu-id="02029-143">Spieler 0</span><span class="sxs-lookup"><span data-stu-id="02029-143">Player 0</span></span> | <span data-ttu-id="02029-144">Spieler 4</span><span class="sxs-lookup"><span data-stu-id="02029-144">Player 4</span></span>
 <span data-ttu-id="02029-145">4</span><span class="sxs-lookup"><span data-stu-id="02029-145">4</span></span> | <span data-ttu-id="02029-146">Spieler 1</span><span class="sxs-lookup"><span data-stu-id="02029-146">Player 1</span></span> | <span data-ttu-id="02029-147">Spieler 2</span><span class="sxs-lookup"><span data-stu-id="02029-147">Player 2</span></span>
 <span data-ttu-id="02029-148">5</span><span class="sxs-lookup"><span data-stu-id="02029-148">5</span></span> | <span data-ttu-id="02029-149">Spieler 3</span><span class="sxs-lookup"><span data-stu-id="02029-149">Player 3</span></span> | <span data-ttu-id="02029-150">Spieler 1</span><span class="sxs-lookup"><span data-stu-id="02029-150">Player 1</span></span>
 <span data-ttu-id="02029-151">6</span><span class="sxs-lookup"><span data-stu-id="02029-151">6</span></span> | <span data-ttu-id="02029-152">Spieler 4</span><span class="sxs-lookup"><span data-stu-id="02029-152">Player 4</span></span> | <span data-ttu-id="02029-153">Spieler 2</span><span class="sxs-lookup"><span data-stu-id="02029-153">Player 2</span></span>

<span data-ttu-id="02029-154">Wenn Sie sich die Beispieldaten genau ansehen, werden Sie feststellen, dass die Spieler 3 und 4 jeweils einen Sieg und eine Niederlage zu verzeichnen haben.</span><span class="sxs-lookup"><span data-stu-id="02029-154">With a closer look at the sample data, you’ll notice that players 3 and 4 both have one win and one loss.</span></span> <span data-ttu-id="02029-155">Sehen wir uns jetzt mithilfe der probabilistischen Programmierung an, wie die Rangfolgen aussehen.</span><span class="sxs-lookup"><span data-stu-id="02029-155">Let's see what the rankings look like using probabilistic programming.</span></span> <span data-ttu-id="02029-156">Beachten Sie, dass es auch einen Spieler 0 (null) gibt, weil sogar Ranglisten für Bürospiele für uns Entwickler nullbasiert sind.</span><span class="sxs-lookup"><span data-stu-id="02029-156">Notice also there is a player zero because even office match up lists are zero based to us developers.</span></span>

## <a name="write-some-code"></a><span data-ttu-id="02029-157">Schreiben von Code</span><span class="sxs-lookup"><span data-stu-id="02029-157">Write some code</span></span>

<span data-ttu-id="02029-158">Nachdem wir das Modell konzipiert haben, ist es jetzt an der Zeit, es mithilfe der Modellierungs-API von Infer.NET als probabilistisches Programm auszudrücken.</span><span class="sxs-lookup"><span data-stu-id="02029-158">Having designed the model, it’s time to express it as a probabilistic program using the Infer.NET modeling API.</span></span> <span data-ttu-id="02029-159">Öffnen Sie `Program.cs` in Ihrem bevorzugten Text-Editor, und ersetzen Sie den gesamten Inhalt durch folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="02029-159">Open `Program.cs` in your favorite text editor and replace all of its contents with the following code:</span></span>

```csharp
namespace myApp

{
    using System;
    using System.Linq;
    using Microsoft.ML.Probabilistic;
    using Microsoft.ML.Probabilistic.Distributions;
    using Microsoft.ML.Probabilistic.Models;

    class Program
    {

        static void Main(string[] args)
        {
            // The winner and loser in each of 6 samples games
            var winnerData = new[] { 0, 0, 0, 1, 3, 4 };
            var loserData = new[] { 1, 3, 4, 2, 1, 2 };

            // Define the statistical model as a probabilistic program 
            var game = new Range(winnerData.Length);
            var player = new Range(winnerData.Concat(loserData).Max() + 1);
            var playerSkills = Variable.Array<double>(player);
            playerSkills[player] = Variable.GaussianFromMeanAndVariance(6, 9).ForEach(player);

            var winners = Variable.Array<int>(game);
            var losers = Variable.Array<int>(game);

            using (Variable.ForEach(game))
            {
                // The player performance is a noisy version of their skill
                var winnerPerformance = Variable.GaussianFromMeanAndVariance(playerSkills[winners[game]], 1.0);
                var loserPerformance = Variable.GaussianFromMeanAndVariance(playerSkills[losers[game]], 1.0);

                // The winner performed better in this game
                Variable.ConstrainTrue(winnerPerformance > loserPerformance);
            }

            // Attach the data to the model
            winners.ObservedValue = winnerData;
            losers.ObservedValue = loserData;

            // Run inference
            var inferenceEngine = new InferenceEngine();
            var inferredSkills = inferenceEngine.Infer<Gaussian[]>(playerSkills);

            // The inferred skills are uncertain, which is captured in their variance
            var orderedPlayerSkills = inferredSkills
               .Select((s, i) => new { Player = i, Skill = s })
               .OrderByDescending(ps => ps.Skill.GetMean());

            foreach (var playerSkill in orderedPlayerSkills)
            {
                Console.WriteLine($"Player {playerSkill.Player} skill: {playerSkill.Skill}");
            }
        }
    }
}
```

## <a name="run-your-app"></a><span data-ttu-id="02029-160">Ausführen der App</span><span class="sxs-lookup"><span data-stu-id="02029-160">Run your app</span></span>

<span data-ttu-id="02029-161">Führen Sie an der Eingabeaufforderung folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="02029-161">In your command prompt, run the following command:</span></span>

```console
dotnet run
```

## <a name="results"></a><span data-ttu-id="02029-162">Ergebnisse</span><span class="sxs-lookup"><span data-stu-id="02029-162">Results</span></span>

<span data-ttu-id="02029-163">Die Ergebnisse sollten den hier dargestellten ähneln:</span><span class="sxs-lookup"><span data-stu-id="02029-163">Your results should be similar to the following:</span></span>

```
Compiling model...done.
Iterating:
.........|.........|.........|.........|.........| 50
Player 0 skill: Gaussian(9.517, 3.926)
Player 3 skill: Gaussian(6.834, 3.892)
Player 4 skill: Gaussian(6.054, 4.731)
Player 1 skill: Gaussian(4.955, 3.503)
Player 2 skill: Gaussian(2.639, 4.288)
```

<span data-ttu-id="02029-164">Beachten Sie bei den Ergebnissen, dass Spieler 3 gemäß unserem Modell etwas höher rangiert als Spieler 4.</span><span class="sxs-lookup"><span data-stu-id="02029-164">In the results, notice that player 3 ranks slightly higher than player 4 according to our model.</span></span> <span data-ttu-id="02029-165">Das liegt daran, dass der Sieg von Spieler 3 über Spieler 1 signifikanter ist als der Sieg von Spieler 4 über Spieler 2 – beachten Sie, dass Spieler 1 gegen Spieler 2 gewonnen hat.</span><span class="sxs-lookup"><span data-stu-id="02029-165">That’s because the victory of player 3 over player 1 is more significant than the victory of player 4 over player 2 – note that player 1 beats player 2.</span></span> <span data-ttu-id="02029-166">Spieler 0 ist der Gesamtsieger!</span><span class="sxs-lookup"><span data-stu-id="02029-166">Player 0 is the overall champ!</span></span>  

## <a name="keep-learning"></a><span data-ttu-id="02029-167">Weiterlernen</span><span class="sxs-lookup"><span data-stu-id="02029-167">Keep learning</span></span>

<span data-ttu-id="02029-168">Das Konzipieren von statistischen Modellen ist eine Kunst für sich.</span><span class="sxs-lookup"><span data-stu-id="02029-168">Designing statistical models is a skill on its own.</span></span> <span data-ttu-id="02029-169">Das Microsoft Research Cambridge-Team hat ein [kostenloses Onlinebuch](http://mbmlbook.com/) herausgebracht, das eine behutsame Einführung zum Thema bietet.</span><span class="sxs-lookup"><span data-stu-id="02029-169">The Microsoft Research Cambridge team has written a [free online book](http://mbmlbook.com/), which gives a gentle introduction to the article.</span></span> <span data-ttu-id="02029-170">In Kapitel 3 wird das TrueSkill-Modell ausführlicher behandelt.</span><span class="sxs-lookup"><span data-stu-id="02029-170">Chapter 3 of this book covers the TrueSkill model in more detail.</span></span> <span data-ttu-id="02029-171">Wenn Sie ein Modell entwickelt haben, können Sie es mithilfe der [umfangreichen Dokumentation](https://dotnet.github.io/infer/) auf der Website von Infer.NET in Code transformieren.</span><span class="sxs-lookup"><span data-stu-id="02029-171">Once you have a model in mind, you can transform it into code using the [extensive documentation](https://dotnet.github.io/infer/) on the Infer.NET website.</span></span>

## <a name="next-steps"></a><span data-ttu-id="02029-172">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="02029-172">Next steps</span></span>

<span data-ttu-id="02029-173">Im GitHub-Repository zu Infer.NET können Sie mit dem Lernen fortfahren und weitere Beispiele finden.</span><span class="sxs-lookup"><span data-stu-id="02029-173">Check out the Infer.NET GitHub repository to continue learning and find more samples.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="02029-174">GitHub-Repository zu dotnet/infer</span><span class="sxs-lookup"><span data-stu-id="02029-174">dotnet/infer GitHub repository</span></span>](https://github.com/dotnet/infer)