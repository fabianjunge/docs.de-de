---
title: do-Bindungen in Klassen (F#)
description: "Informationen Sie zum Verwenden einer \"do Bindung in einer Klassendefinition, Aktionen ausgeführt, wenn das Objekt erstellt wird oder wenn der Typ zuerst verwendet wird\" f#."
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 78987cb8-bdba-46e2-b5b2-994c83fe42c4
ms.openlocfilehash: f9582338306d87c3dd799425083037cc95b31b1e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="do-bindings-in-classes"></a><span data-ttu-id="145f1-104">do-Bindungen in Klassen</span><span class="sxs-lookup"><span data-stu-id="145f1-104">do Bindings in Classes</span></span>

<span data-ttu-id="145f1-105">Ein `do` Bindung in einer Klassendefinition führt Aktionen aus, wenn das Objekt erstellt wurde, oder für einen statischen `do` binden, wenn der Typ zuerst verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="145f1-105">A `do` binding in a class definition performs actions when the object is constructed or, for a static `do` binding, when the type is first used.</span></span>


## <a name="syntax"></a><span data-ttu-id="145f1-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="145f1-106">Syntax</span></span>

```fsharp
[static] do expression
```

## <a name="remarks"></a><span data-ttu-id="145f1-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="145f1-107">Remarks</span></span>
<span data-ttu-id="145f1-108">Ein `do` Bindung angezeigt wird, zusammen mit oder nach `let` Bindungen, aber vor der Definitionen der Elemente in einer Klassendefinition.</span><span class="sxs-lookup"><span data-stu-id="145f1-108">A `do` binding appears together with or after `let` bindings but before member definitions in a class definition.</span></span> <span data-ttu-id="145f1-109">Obwohl die `do` Schlüsselwort ist optional für `do` Bindungen auf Modulebene, es ist nicht optional für `do` Bindungen in einer Klassendefinition.</span><span class="sxs-lookup"><span data-stu-id="145f1-109">Although the `do` keyword is optional for `do` bindings at the module level, it is not optional for `do` bindings in a class definition.</span></span>

<span data-ttu-id="145f1-110">Für die Erstellung eines jeden Objekts, eines beliebigen angegebenen Typ, der nicht statischen `do` Bindungen und nicht statische `let` Bindungen werden in der Reihenfolge, in der sie in der Klassendefinition erscheinen, ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="145f1-110">For the construction of every object of any given type, non-static `do` bindings and non-static `let` bindings are executed in the order in which they appear in the class definition.</span></span> <span data-ttu-id="145f1-111">Mehrere `do` Bindungen in einem auftreten können.</span><span class="sxs-lookup"><span data-stu-id="145f1-111">Multiple `do` bindings can occur in one type.</span></span> <span data-ttu-id="145f1-112">Die statische `let` Bindungen und die statische `do` Bindungen Nachrichtentext der primären Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="145f1-112">The non-static `let` bindings and the non-static `do` bindings become the body of the primary constructor.</span></span> <span data-ttu-id="145f1-113">Der Code in der statischen `do` im Abschnitt über Bindungen kann die primären Konstruktorparameter und alle Werte oder in definierten Funktionen verweisen die `let` im Abschnitt über Bindungen.</span><span class="sxs-lookup"><span data-stu-id="145f1-113">The code in the non-static `do` bindings section can reference the primary constructor parameters and any values or functions that are defined in the `let` bindings section.</span></span>

<span data-ttu-id="145f1-114">Nicht statische `do` Bindungen können Member der Klasse zugreifen, solange die Klasse verfügt über einen Selbstbezeichner, die von definiert ist ein `as` Schlüsselwort in der Klasse Überschrift bzw. solange alle Vorkommen dieser Elemente mit der Selbstbezeichner für die Klasse qualifiziert sind.</span><span class="sxs-lookup"><span data-stu-id="145f1-114">Non-static `do` bindings can access members of the class as long as the class has a self identifier that is defined by an `as` keyword in the class heading, and as long as all uses of those members are qualified with the self identifier for the class.</span></span>

<span data-ttu-id="145f1-115">Da `let` Bindungen initialisieren die privaten Felder einer Klasse, die häufig notwendig ist, um sicherzustellen, dass Mitglieder Verhalten sich wie erwartet, `do` Bindungen werden in der Regel nach platziert `let` Bindungen, so dass der code in der `do` Bindung kann Führen Sie ein vollständig initialisiertes Objekt.</span><span class="sxs-lookup"><span data-stu-id="145f1-115">Because `let` bindings initialize the private fields of a class, which is often necessary to guarantee that members behave as expected, `do` bindings are usually put after `let` bindings so that code in the `do` binding can execute with a fully initialized object.</span></span> <span data-ttu-id="145f1-116">Wenn Ihr Code versucht, ein Element zu verwenden, bevor die Initialisierung abgeschlossen ist, wird eine InvalidOperationException ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="145f1-116">If your code attempts to use a member before the initialization is complete, an InvalidOperationException is raised.</span></span>

<span data-ttu-id="145f1-117">Statische `do` Bindungen können statische Member verweisen oder Felder des einschließenden Klasse aber nicht auf die Instanz Member oder Felder.</span><span class="sxs-lookup"><span data-stu-id="145f1-117">Static `do` bindings can reference static members or fields of the enclosing class but not instance members or fields.</span></span> <span data-ttu-id="145f1-118">Statische `do` Bindungen werden Teil der statische Initialisierer für die Klasse, die unbedingt ausführen, bevor die Klasse zuerst verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="145f1-118">Static `do` bindings become part of the static initializer for the class, which is guaranteed to execute before the class is first used.</span></span>

<span data-ttu-id="145f1-119">Attribute werden ignoriert, für `do` Bindungen in Typen.</span><span class="sxs-lookup"><span data-stu-id="145f1-119">Attributes are ignored for `do` bindings in types.</span></span> <span data-ttu-id="145f1-120">Wenn ein Attribut für Code erforderlich, die ist in führt ein `do` binden, muss angewendet werden an den primären Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="145f1-120">If an attribute is required for code that executes in a `do` binding, it must be applied to the primary constructor.</span></span>

<span data-ttu-id="145f1-121">Im folgenden Code wird eine Klasse verfügt über einen statischen `do` Bindung und eine nicht statische `do` Bindung.</span><span class="sxs-lookup"><span data-stu-id="145f1-121">In the following code, a class has a static `do` binding and a non-static `do` binding.</span></span> <span data-ttu-id="145f1-122">Das Objekt verfügt über einen Konstruktor, der zwei Parameter verfügt `a` und `b`, und zwei private Felder definiert sind, der `let` Bindungen für die Klasse.</span><span class="sxs-lookup"><span data-stu-id="145f1-122">The object has a constructor that has two parameters, `a` and `b`, and two private fields are defined in the `let` bindings for the class.</span></span> <span data-ttu-id="145f1-123">Zwei Eigenschaften sind auch definiert.</span><span class="sxs-lookup"><span data-stu-id="145f1-123">Two properties are also defined.</span></span> <span data-ttu-id="145f1-124">Alle diese werden im Bereich der statischen `do` im Abschnitt über Bindungen, wie durch die Linie dargestellt wird, die alle diese Werte ausgibt.</span><span class="sxs-lookup"><span data-stu-id="145f1-124">All of these are in scope in the non-static `do` bindings section, as is illustrated by the line that prints all those values.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3101.fs)]

<span data-ttu-id="145f1-125">Die Ausgabe lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="145f1-125">The output is as follows.</span></span>

```console
Initializing MyType.
Initializing object 1 2 2 4 8 16
```

## <a name="see-also"></a><span data-ttu-id="145f1-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="145f1-126">See Also</span></span>
[<span data-ttu-id="145f1-127">Mitglieder</span><span class="sxs-lookup"><span data-stu-id="145f1-127">Members</span></span>](index.md)

[<span data-ttu-id="145f1-128">Klassen</span><span class="sxs-lookup"><span data-stu-id="145f1-128">Classes</span></span>](../classes.md)

[<span data-ttu-id="145f1-129">Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="145f1-129">Constructors</span></span>](constructors.md)

[<span data-ttu-id="145f1-130">`let`-Bindungen in Klassen</span><span class="sxs-lookup"><span data-stu-id="145f1-130">`let` Bindings in Classes</span></span>](let-bindings-in-classes.md)

[<span data-ttu-id="145f1-131">`do`Bindungen</span><span class="sxs-lookup"><span data-stu-id="145f1-131">`do` Bindings</span></span>](../functions/do-Bindings.md)