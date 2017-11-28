---
title: XML-Dokumentation (F#)
description: "Erfahren Sie mehr über Unterstützung in F# erläutert werden, zum Generieren von Dokumentation aus Kommentaren."
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: d99ab1b6-e170-4ec2-a543-43ea7ab15bb2
ms.openlocfilehash: 20768a7d4ea17c926318043f658691819a3d7d2f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="xml-documentation"></a><span data-ttu-id="d167d-104">XML-Dokumentation</span><span class="sxs-lookup"><span data-stu-id="d167d-104">XML Documentation</span></span>

<span data-ttu-id="d167d-105">Können Sie Dokumentation vom Triple-Schrägstrich (/ / /) erzeugt code in f#.</span><span class="sxs-lookup"><span data-stu-id="d167d-105">You can produce documentation from triple-slash (///) code comments in F#.</span></span> <span data-ttu-id="d167d-106">XML-Kommentare können Deklarationen in Codedateien (sein) oder Signaturdateien (".FSI") voranstellen.</span><span class="sxs-lookup"><span data-stu-id="d167d-106">XML comments can precede declarations in code files (.fs) or signature (.fsi) files.</span></span>


## <a name="generating-documentation-from-comments"></a><span data-ttu-id="d167d-107">Generieren von Dokumentation aus Kommentaren</span><span class="sxs-lookup"><span data-stu-id="d167d-107">Generating Documentation from Comments</span></span>
<span data-ttu-id="d167d-108">Die Unterstützung in f# zum Generieren von Dokumentation aus Kommentaren ist dieselbe wie in anderen .NET Framework-Sprachen.</span><span class="sxs-lookup"><span data-stu-id="d167d-108">The support in F# for generating documentation from comments is the same as that in other .NET Framework languages.</span></span> <span data-ttu-id="d167d-109">Wie in anderen .NET Framework-Sprachen die [-Doc-Compileroption](https://msdn.microsoft.com/library/434394ae-0d4a-459c-a684-bffede519a04) ermöglicht es Ihnen, eine XML-Datei zu erzeugen, die Informationen enthält, die Sie in der Dokumentation mit einem Tool wie z. B. Sandburg konvertieren können.</span><span class="sxs-lookup"><span data-stu-id="d167d-109">As in other .NET Framework languages, the [-doc compiler option](https://msdn.microsoft.com/library/434394ae-0d4a-459c-a684-bffede519a04) enables you to produce an XML file that contains information that you can convert into documentation by using a tool such as Sandcastle.</span></span> <span data-ttu-id="d167d-110">Die Dokumentation mithilfe der Tools, die entwickelt wurden für die Verwendung mit Assemblys, die in anderen .NET Framework-Sprachen, in der Regel geschrieben sind generiert erzeugen einen Überblick über die APIs, die auf der kompilierten Form von F#-Konstrukten basiert.</span><span class="sxs-lookup"><span data-stu-id="d167d-110">The documentation generated by using tools that are designed for use with assemblies that are written in other .NET Framework languages generally produce a view of the APIs that is based on the compiled form of F# constructs.</span></span> <span data-ttu-id="d167d-111">Sofern nicht ausdrücklich F#-Supporttools, entspricht Dokumentation, die von diesen Tools generierten f#-Ansicht einer API nicht.</span><span class="sxs-lookup"><span data-stu-id="d167d-111">Unless tools specifically support F#, documentation generated by these tools does not match the F# view of an API.</span></span>

<span data-ttu-id="d167d-112">Weitere Informationen zum Generieren von Dokumentation aus XML finden Sie unter [XML-Dokumentationskommentare &#40; C &#35; Programmierhandbuch &#41; ](https://msdn.microsoft.com/library/b2s063f7).</span><span class="sxs-lookup"><span data-stu-id="d167d-112">For more information about how to generate documentation from XML, see [XML Documentation Comments &#40;C&#35; Programming Guide&#41;](https://msdn.microsoft.com/library/b2s063f7).</span></span>


## <a name="recommended-tags"></a><span data-ttu-id="d167d-113">Empfohlene Tags</span><span class="sxs-lookup"><span data-stu-id="d167d-113">Recommended Tags</span></span>
<span data-ttu-id="d167d-114">Es gibt zwei Möglichkeiten zum Schreiben von XML-Dokumentationskommentare.</span><span class="sxs-lookup"><span data-stu-id="d167d-114">There are two ways to write XML documentation comments.</span></span> <span data-ttu-id="d167d-115">Eine besteht darin, nur die Dokumentation direkt in einen Kommentar Triple-Schrägstrich schreiben, ohne Verwendung von XML-Tags.</span><span class="sxs-lookup"><span data-stu-id="d167d-115">One is to just write the documentation directly in a triple-slash comment, without using XML tags.</span></span> <span data-ttu-id="d167d-116">Wenn Sie so vorgehen, wird der gesamte Kommentartext als die Zusammenfassung Dokumentation für das Codekonstrukt aufgefasst, die unmittelbar folgt.</span><span class="sxs-lookup"><span data-stu-id="d167d-116">If you do this, the entire comment text is taken as the summary documentation for the code construct that immediately follows.</span></span> <span data-ttu-id="d167d-117">Verwenden Sie diese Methode, wenn Sie nur eine kurze Zusammenfassung für jedes Konstrukt schreiben möchten.</span><span class="sxs-lookup"><span data-stu-id="d167d-117">Use this method when you want to write only a brief summary for each construct.</span></span> <span data-ttu-id="d167d-118">Die andere Methode ist, mit der XML-Tags mehr strukturierte Dokumentation zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="d167d-118">The other method is to use XML tags to provide more structured documentation.</span></span> <span data-ttu-id="d167d-119">Die zweite Methode können Sie separate Hinweise für eine kurze Zusammenfassung, zusätzliche Hinweise, Dokumentation für jeden Parameter und die Typparameter und die ausgelösten Ausnahmen und eine Beschreibung des Rückgabewerts angeben.</span><span class="sxs-lookup"><span data-stu-id="d167d-119">The second method enables you to specify separate notes for a short summary, additional remarks, documentation for each parameter and type parameter and exceptions thrown, and a description of the return value.</span></span> <span data-ttu-id="d167d-120">Die folgende Tabelle beschreibt die XML-Tags, die in F#-XML-Codekommentaren erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="d167d-120">The following table describes XML tags that are recognized in F# XML code comments.</span></span>



|<span data-ttu-id="d167d-121">Tagsyntax</span><span class="sxs-lookup"><span data-stu-id="d167d-121">Tag syntax</span></span>|<span data-ttu-id="d167d-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d167d-122">Description</span></span>|
|----------|-----------|
|<span data-ttu-id="d167d-123">**&lt;c&gt;***Text* **&lt; /c&gt;**</span><span class="sxs-lookup"><span data-stu-id="d167d-123">**&lt;c&gt;***text***&lt;/c&gt;**</span></span>|<span data-ttu-id="d167d-124">Gibt an, dass *Text* Code ist.</span><span class="sxs-lookup"><span data-stu-id="d167d-124">Specifies that *text* is code.</span></span> <span data-ttu-id="d167d-125">Dieses Tag kann durch Dokumentationsgeneratoren verwendet werden, um Text in einer Schriftart anzuzeigen, die für Code geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="d167d-125">This tag can be used by documentation generators to display text in a font that is appropriate for code.</span></span>|
|<span data-ttu-id="d167d-126">**&lt;Zusammenfassung&gt;***Text* **&lt; /summary&gt;**</span><span class="sxs-lookup"><span data-stu-id="d167d-126">**&lt;summary&gt;***text***&lt;/summary&gt;**</span></span>|<span data-ttu-id="d167d-127">Gibt an, dass *Text* ist eine kurze Beschreibung der das Programmelement.</span><span class="sxs-lookup"><span data-stu-id="d167d-127">Specifies that *text* is a brief description of the program element.</span></span> <span data-ttu-id="d167d-128">Die Beschreibung ist in der Regel ein oder zwei Sätze.</span><span class="sxs-lookup"><span data-stu-id="d167d-128">The description is usually one or two sentences.</span></span>|
|<span data-ttu-id="d167d-129">**&lt;"Hinweise"&gt;***Text* **&lt; /remarks&gt;**</span><span class="sxs-lookup"><span data-stu-id="d167d-129">**&lt;remarks&gt;***text***&lt;/remarks&gt;**</span></span>|<span data-ttu-id="d167d-130">Gibt an, dass *Text* enthält zusätzliche Informationen über das Programmelement.</span><span class="sxs-lookup"><span data-stu-id="d167d-130">Specifies that *text* contains supplementary information about the program element.</span></span>|
|<span data-ttu-id="d167d-131">**&lt;Param Name = "***Namen***"&gt;***Beschreibung***&lt;/param&gt;**</span><span class="sxs-lookup"><span data-stu-id="d167d-131">**&lt;param name="***name***"&gt;***description***&lt;/param&gt;**</span></span>|<span data-ttu-id="d167d-132">Gibt den Namen und eine Beschreibung für eine Funktion oder Methode Parameter.</span><span class="sxs-lookup"><span data-stu-id="d167d-132">Specifies the name and description for a function or method parameter.</span></span>|
|<span data-ttu-id="d167d-133">**&lt;Typeparam Name = "***Namen***"&gt;***Beschreibung***&lt;/typeparam&gt;**</span><span class="sxs-lookup"><span data-stu-id="d167d-133">**&lt;typeparam name="***name***"&gt;***description***&lt;/typeparam&gt;**</span></span>|<span data-ttu-id="d167d-134">Gibt den Namen und eine Beschreibung für einen Typparameter darstellt.</span><span class="sxs-lookup"><span data-stu-id="d167d-134">Specifies the name and description for a type parameter.</span></span>|
|<span data-ttu-id="d167d-135">**&lt;Gibt&gt;***Text* **&lt; /returns&gt;**</span><span class="sxs-lookup"><span data-stu-id="d167d-135">**&lt;returns&gt;***text***&lt;/returns&gt;**</span></span>|<span data-ttu-id="d167d-136">Gibt an, dass *Text* beschreibt den Rückgabewert einer Funktion oder Methode.</span><span class="sxs-lookup"><span data-stu-id="d167d-136">Specifies that *text* describes the return value of a function or method.</span></span>|
|<span data-ttu-id="d167d-137">**&lt;Ausnahme Cref = "***Typ***"&gt;***Beschreibung***&lt;/exception&gt;**</span><span class="sxs-lookup"><span data-stu-id="d167d-137">**&lt;exception cref="***type***"&gt;***description***&lt;/exception&gt;**</span></span>|<span data-ttu-id="d167d-138">Gibt den Typ der Ausnahme, die generiert werden kann und die Umstände, unter denen sie ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="d167d-138">Specifies the type of exception that can be generated and the circumstances under which it is thrown.</span></span>|
|<span data-ttu-id="d167d-139">**&lt;Siehe Cref = "***Verweis***"&gt;***Text* **&lt; /finden Sie unter&gt;**</span><span class="sxs-lookup"><span data-stu-id="d167d-139">**&lt;see cref="***reference***"&gt;***text***&lt;/see&gt;**</span></span>|<span data-ttu-id="d167d-140">Gibt einen Inlinelink auf ein anderes Programmelement.</span><span class="sxs-lookup"><span data-stu-id="d167d-140">Specifies an inline link to another program element.</span></span> <span data-ttu-id="d167d-141">Die *Verweis* ist der Name, wie er in der XML-Dokumentationsdatei angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="d167d-141">The *reference* is the name as it appears in the XML documentation file.</span></span> <span data-ttu-id="d167d-142">Die *Text* ist der Text im Link dargestellt.</span><span class="sxs-lookup"><span data-stu-id="d167d-142">The *text* is the text shown in the link.</span></span>|
|<span data-ttu-id="d167d-143">**&lt;Seealso Cref = "***Verweis***" /&gt;**</span><span class="sxs-lookup"><span data-stu-id="d167d-143">**&lt;seealso cref="***reference***"/&gt;**</span></span>|<span data-ttu-id="d167d-144">Gibt einen Link Siehe auch in der Dokumentation für einen anderen Typ.</span><span class="sxs-lookup"><span data-stu-id="d167d-144">Specifies a See Also link to the documentation for another type.</span></span> <span data-ttu-id="d167d-145">Die *Verweis* ist der Name, wie er in der XML-Dokumentationsdatei angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="d167d-145">The *reference* is the name as it appears in the XML documentation file.</span></span> <span data-ttu-id="d167d-146">Siehe auch Links, die in der Regel am unteren Rand einer Dokumentationsseite angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="d167d-146">See Also links usually appear at the bottom of a documentation page.</span></span>|
|<span data-ttu-id="d167d-147">**&lt;Para&gt;***Text***&lt;/para&gt;**</span><span class="sxs-lookup"><span data-stu-id="d167d-147">**&lt;para&gt;***text***&lt;/para&gt;**</span></span>|<span data-ttu-id="d167d-148">Gibt einen Textabsatz an.</span><span class="sxs-lookup"><span data-stu-id="d167d-148">Specifies a paragraph of text.</span></span> <span data-ttu-id="d167d-149">Dies dient zum Trennen von Text in der **"Hinweise"** Tag.</span><span class="sxs-lookup"><span data-stu-id="d167d-149">This is used to separate text inside the **remarks** tag.</span></span>|

## <a name="example"></a><span data-ttu-id="d167d-150">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d167d-150">Example</span></span>

### <a name="description"></a><span data-ttu-id="d167d-151">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d167d-151">Description</span></span>
<span data-ttu-id="d167d-152">Im folgenden Code wird eine typische XML-Dokumentationskommentar in einer Signaturdatei.</span><span class="sxs-lookup"><span data-stu-id="d167d-152">The following is a typical XML documentation comment in a signature file.</span></span>


### <a name="code"></a><span data-ttu-id="d167d-153">Code</span><span class="sxs-lookup"><span data-stu-id="d167d-153">Code</span></span>
[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet7101.fs)]
    
## <a name="example"></a><span data-ttu-id="d167d-154">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d167d-154">Example</span></span>

### <a name="description"></a><span data-ttu-id="d167d-155">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d167d-155">Description</span></span>
<span data-ttu-id="d167d-156">Das folgende Beispiel zeigt die alternative Methode verwenden, ohne XML-Tags.</span><span class="sxs-lookup"><span data-stu-id="d167d-156">The following example shows the alternative method, without XML tags.</span></span> <span data-ttu-id="d167d-157">In diesem Beispiel wird der gesamte Text im Kommentar eine Zusammenfassung betrachtet.</span><span class="sxs-lookup"><span data-stu-id="d167d-157">In this example, the entire text in the comment is considered a summary.</span></span> <span data-ttu-id="d167d-158">Beachten Sie, dass wenn Sie eine Zusammenfassung Tag nicht explizit angeben, Sie keine anderen Tags wie z. B. angeben sollten **Param** oder **gibt** Tags.</span><span class="sxs-lookup"><span data-stu-id="d167d-158">Note that if you do not specify a summary tag explicitly, you should not specify other tags, such as **param** or **returns** tags.</span></span>


### <a name="code"></a><span data-ttu-id="d167d-159">Code</span><span class="sxs-lookup"><span data-stu-id="d167d-159">Code</span></span>
[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet7102.fs)]
    
## <a name="see-also"></a><span data-ttu-id="d167d-160">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d167d-160">See Also</span></span>
[<span data-ttu-id="d167d-161">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="d167d-161">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="d167d-162">Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="d167d-162">Compiler Options</span></span>](compiler-options.md)