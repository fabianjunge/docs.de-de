---
title: Musterabgleich (F#)
description: Erfahren Sie, wie Muster werden in f# verwendet zum Vergleichen von Daten mit logischen Strukturen, Daten in einzelne Bestandteile zu zerlegen oder Informationen aus Daten zu extrahieren.
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 5562ee98-e2f1-4dcd-8e2f-16ae27baaade
ms.openlocfilehash: 7c7a3110a8f34c0c96c12d4584010a9ac4b485fa
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="pattern-matching"></a><span data-ttu-id="79f92-104">Musterabgleich</span><span class="sxs-lookup"><span data-stu-id="79f92-104">Pattern Matching</span></span>

<span data-ttu-id="79f92-105">Muster sind Regeln zum Transformieren von Eingabedaten.</span><span class="sxs-lookup"><span data-stu-id="79f92-105">Patterns are rules for transforming input data.</span></span> <span data-ttu-id="79f92-106">Sie werden in F# stets verwendet, um Daten mit logischen Strukturen zu vergleichen, Daten in einzelne Bestandteile zu zerlegen oder auf unterschiedliche Weise Informationen aus Daten zu extrahieren.</span><span class="sxs-lookup"><span data-stu-id="79f92-106">They are used throughout the F# language to compare data with a logical structure or structures, decompose data into constituent parts, or extract information from data in various ways.</span></span>


## <a name="remarks"></a><span data-ttu-id="79f92-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="79f92-107">Remarks</span></span>
<span data-ttu-id="79f92-108">Muster werden in vielen Sprachkonstrukten verwendet, z. B. im `match`-Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="79f92-108">Patterns are used in many language constructs, such as the `match` expression.</span></span> <span data-ttu-id="79f92-109">Sie werden verwendet, wenn Argumente für Funktionen in `let`-Bindungen oder Lambda-Ausdrücken verarbeitet werden, sowie in den dem `try...with`-Ausdruck zugeordneten Ausnahmehandlern.</span><span class="sxs-lookup"><span data-stu-id="79f92-109">They are used when you are processing arguments for functions in `let` bindings, lambda expressions, and in the exception handlers associated with the `try...with` expression.</span></span> <span data-ttu-id="79f92-110">Weitere Informationen finden Sie unter [Übereinstimmungsausdrücken](match-expressions.md), [let-Bindungen](functions/let-bindings.md), [Lambda-Ausdrücke: das `fun` Schlüsselwort](functions/lambda-expressions-the-fun-keyword.md), und [Ausnahmen: die `try...with` Ausdruck](exception-handling/the-try-with-expression.md).</span><span class="sxs-lookup"><span data-stu-id="79f92-110">For more information, see [Match Expressions](match-expressions.md), [let Bindings](functions/let-bindings.md), [Lambda Expressions: The `fun` Keyword](functions/lambda-expressions-the-fun-keyword.md), and [Exceptions: The `try...with` Expression](exception-handling/the-try-with-expression.md).</span></span>

<span data-ttu-id="79f92-111">Beispielsweise ist in der `match` Ausdruck, der *Muster* ist, was dem Pipesymbol angegeben.</span><span class="sxs-lookup"><span data-stu-id="79f92-111">For example, in the `match` expression, the *pattern* is what follows the pipe symbol.</span></span>

```fsharp
match expression with
| pattern [ when condition ] -> result-expression
...
```

<span data-ttu-id="79f92-112">Jedes Muster fungiert als Regel zum Transformieren von Eingaben.</span><span class="sxs-lookup"><span data-stu-id="79f92-112">Each pattern acts as a rule for transforming input in some way.</span></span> <span data-ttu-id="79f92-113">Im `match`-Ausdruck wird jedes Muster einzeln untersucht, um zu ermitteln, ob die Eingabedaten mit dem Muster kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="79f92-113">In the `match` expression, each pattern is examined in turn to see if the input data is compatible with the pattern.</span></span> <span data-ttu-id="79f92-114">Wenn eine Übereinstimmung gefunden wird, wird der Ergebnisausdruck ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="79f92-114">If a match is found, the result expression is executed.</span></span> <span data-ttu-id="79f92-115">Wenn keine Übereinstimmung gefunden wird, wird die nächste Musterregel getestet.</span><span class="sxs-lookup"><span data-stu-id="79f92-115">If a match is not found, the next pattern rule is tested.</span></span> <span data-ttu-id="79f92-116">Die optionale When *Bedingung* wird eine Erläuterung der Teile [Übereinstimmungsausdrücken](match-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="79f92-116">The optional when *condition* part is explained in [Match Expressions](match-expressions.md).</span></span>

<span data-ttu-id="79f92-117">In der folgenden Tabelle werden unterstützte Muster aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="79f92-117">Supported patterns are shown in the following table.</span></span> <span data-ttu-id="79f92-118">Zur Laufzeit wird die Eingabe anhand jedes der folgenden Muster in der in der Tabelle aufgeführten Reihenfolge überprüft. Die Muster werden rekursiv vom ersten bis zum letzten Muster im Code und von links nach rechts in den einzelnen Zeilen angewendet.</span><span class="sxs-lookup"><span data-stu-id="79f92-118">At run time, the input is tested against each of the following patterns in the order listed in the table, and patterns are applied recursively, from first to last as they appear in your code, and from left to right for the patterns on each line.</span></span>

|<span data-ttu-id="79f92-119">Name</span><span class="sxs-lookup"><span data-stu-id="79f92-119">Name</span></span>|<span data-ttu-id="79f92-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="79f92-120">Description</span></span>|<span data-ttu-id="79f92-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="79f92-121">Example</span></span>|
|----|-----------|-------|
|<span data-ttu-id="79f92-122">Konstantenmuster</span><span class="sxs-lookup"><span data-stu-id="79f92-122">Constant pattern</span></span>|<span data-ttu-id="79f92-123">Ein beliebiges numerisches Literal, Zeichenliteral oder Zeichenfolgenliteral, eine Enumerationskonstante oder ein definierter Literalbezeichner.</span><span class="sxs-lookup"><span data-stu-id="79f92-123">Any numeric, character, or string literal, an enumeration constant, or a defined literal identifier</span></span>|<span data-ttu-id="79f92-124">`1.0`, `"test"`, `30`, `Color.Red`</span><span class="sxs-lookup"><span data-stu-id="79f92-124">`1.0`, `"test"`, `30`, `Color.Red`</span></span>|
|<span data-ttu-id="79f92-125">Bezeichnermuster</span><span class="sxs-lookup"><span data-stu-id="79f92-125">Identifier pattern</span></span>|<span data-ttu-id="79f92-126">Der Wert eines Falls einer Unterscheidungs-Union, eine Ausnahmebezeichnung oder ein Fall eines aktiven Musters.</span><span class="sxs-lookup"><span data-stu-id="79f92-126">A case value of a discriminated union, an exception label, or an active pattern case</span></span>|`Some(x)`<br /><br />`Failure(msg)`|
|<span data-ttu-id="79f92-127">Variablenmuster</span><span class="sxs-lookup"><span data-stu-id="79f92-127">Variable pattern</span></span>|<span data-ttu-id="79f92-128">*identifier*</span><span class="sxs-lookup"><span data-stu-id="79f92-128">*identifier*</span></span>|`a`|
|<span data-ttu-id="79f92-129">`as`-Muster</span><span class="sxs-lookup"><span data-stu-id="79f92-129">`as` pattern</span></span>|<span data-ttu-id="79f92-130">*Muster* als *Bezeichner*</span><span class="sxs-lookup"><span data-stu-id="79f92-130">*pattern* as *identifier*</span></span>|`(a, b) as tuple1`|
|<span data-ttu-id="79f92-131">OR-Muster</span><span class="sxs-lookup"><span data-stu-id="79f92-131">OR pattern</span></span>|<span data-ttu-id="79f92-132">*pattern1* &#124; *pattern2*</span><span class="sxs-lookup"><span data-stu-id="79f92-132">*pattern1* &#124; *pattern2*</span></span>|<code>([h] &#124; [h; _])</code>|
|<span data-ttu-id="79f92-133">AND-Muster</span><span class="sxs-lookup"><span data-stu-id="79f92-133">AND pattern</span></span>|<span data-ttu-id="79f92-134">*pattern1* &amp; *pattern2*</span><span class="sxs-lookup"><span data-stu-id="79f92-134">*pattern1* &amp; *pattern2*</span></span>|`(a, b) & (_, "test")`|
|<span data-ttu-id="79f92-135">Cons-Muster</span><span class="sxs-lookup"><span data-stu-id="79f92-135">Cons pattern</span></span>|<span data-ttu-id="79f92-136">*Bezeichner* :: *Liste-Bezeichner*</span><span class="sxs-lookup"><span data-stu-id="79f92-136">*identifier* :: *list-identifier*</span></span>|`h :: t`|
|<span data-ttu-id="79f92-137">Listenmuster</span><span class="sxs-lookup"><span data-stu-id="79f92-137">List pattern</span></span>|<span data-ttu-id="79f92-138">[ *Muster_1*;...; *Pattern_n* ]</span><span class="sxs-lookup"><span data-stu-id="79f92-138">[ *pattern_1*; ... ; *pattern_n* ]</span></span>|`[ a; b; c ]`|
|<span data-ttu-id="79f92-139">Arraymuster</span><span class="sxs-lookup"><span data-stu-id="79f92-139">Array pattern</span></span>|<span data-ttu-id="79f92-140">[&#124; *Muster_1*;..; *Pattern_n* &#124;]</span><span class="sxs-lookup"><span data-stu-id="79f92-140">[&#124; *pattern_1*; ..; *pattern_n* &#124;]</span></span>|<code>[&#124; a; b; c &#124;]</code>|
|<span data-ttu-id="79f92-141">Muster in Klammern</span><span class="sxs-lookup"><span data-stu-id="79f92-141">Parenthesized pattern</span></span>|<span data-ttu-id="79f92-142">( *Muster* )</span><span class="sxs-lookup"><span data-stu-id="79f92-142">( *pattern* )</span></span>|`( a )`|
|<span data-ttu-id="79f92-143">Tupelmuster</span><span class="sxs-lookup"><span data-stu-id="79f92-143">Tuple pattern</span></span>|<span data-ttu-id="79f92-144">( *Muster_1*,..., *Pattern_n* )</span><span class="sxs-lookup"><span data-stu-id="79f92-144">( *pattern_1*, ... , *pattern_n* )</span></span>|`( a, b )`|
|<span data-ttu-id="79f92-145">Datensatzmuster</span><span class="sxs-lookup"><span data-stu-id="79f92-145">Record pattern</span></span>|<span data-ttu-id="79f92-146">{ *Bezeichner1* = *Muster_1*;...; *Identifier_n* = *Pattern_n* }</span><span class="sxs-lookup"><span data-stu-id="79f92-146">{ *identifier1* = *pattern_1*; ... ; *identifier_n* = *pattern_n* }</span></span>|`{ Name = name; }`|
|<span data-ttu-id="79f92-147">Platzhaltermuster</span><span class="sxs-lookup"><span data-stu-id="79f92-147">Wildcard pattern</span></span>|<span data-ttu-id="79f92-148">_</span><span class="sxs-lookup"><span data-stu-id="79f92-148">_</span></span>|`_`|
|<span data-ttu-id="79f92-149">Muster zusammen mit Typanmerkung</span><span class="sxs-lookup"><span data-stu-id="79f92-149">Pattern together with type annotation</span></span>|<span data-ttu-id="79f92-150">*Muster* : *Typ*</span><span class="sxs-lookup"><span data-stu-id="79f92-150">*pattern* : *type*</span></span>|`a : int`|
|<span data-ttu-id="79f92-151">Typtestmuster</span><span class="sxs-lookup"><span data-stu-id="79f92-151">Type test pattern</span></span>|<span data-ttu-id="79f92-152">:?</span><span class="sxs-lookup"><span data-stu-id="79f92-152">:?</span></span> <span data-ttu-id="79f92-153">*Typ* [als *Bezeichner* ]</span><span class="sxs-lookup"><span data-stu-id="79f92-153">*type* [ as *identifier* ]</span></span>|`:? System.DateTime as dt`|
|<span data-ttu-id="79f92-154">NULL-Muster</span><span class="sxs-lookup"><span data-stu-id="79f92-154">Null pattern</span></span>|<span data-ttu-id="79f92-155">NULL</span><span class="sxs-lookup"><span data-stu-id="79f92-155">null</span></span>|`null`|

## <a name="constant-patterns"></a><span data-ttu-id="79f92-156">Konstantenmuster</span><span class="sxs-lookup"><span data-stu-id="79f92-156">Constant Patterns</span></span>
<span data-ttu-id="79f92-157">Konstantenmuster sind numerische Literale, Zeichenliterale und Zeichenfolgenliterale, Enumerationskonstanten (einschließlich Enumerationstypnamen).</span><span class="sxs-lookup"><span data-stu-id="79f92-157">Constant patterns are numeric, character, and string literals, enumeration constants (with the enumeration type name included).</span></span> <span data-ttu-id="79f92-158">Ein `match`-Ausdruck, der nur über Konstantenmuster verfügt, ist mit case-Anweisungen in anderen Sprachen vergleichbar.</span><span class="sxs-lookup"><span data-stu-id="79f92-158">A `match` expression that has only constant patterns can be compared to a case statement in other languages.</span></span> <span data-ttu-id="79f92-159">Die Eingabe wird mit dem Literalwert verglichen, und das Muster stimmt überein, wenn die Werte gleich sind.</span><span class="sxs-lookup"><span data-stu-id="79f92-159">The input is compared with the literal value and the pattern matches if the values are equal.</span></span> <span data-ttu-id="79f92-160">Der Typ des Literals muss mit dem Typ der Eingabe kompatibel sein.</span><span class="sxs-lookup"><span data-stu-id="79f92-160">The type of the literal must be compatible with the type of the input.</span></span>

<span data-ttu-id="79f92-161">Im folgenden Beispiel wird die Verwendung von Literalmustern veranschaulicht, und es werden außerdem ein Variablenmuster und ein OR-Muster verwendet.</span><span class="sxs-lookup"><span data-stu-id="79f92-161">The following example demonstrates the use of literal patterns, and also uses a variable pattern and an OR pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4801.fs)]

<span data-ttu-id="79f92-162">Ein weiteres Beispiel für ein Literalmuster ist ein auf Enumerationskonstanten basierendes Muster.</span><span class="sxs-lookup"><span data-stu-id="79f92-162">Another example of a literal pattern is a pattern based on enumeration constants.</span></span> <span data-ttu-id="79f92-163">Wenn Sie Enumerationskonstanten verwenden, müssen Sie den Enumerationstypnamen angeben.</span><span class="sxs-lookup"><span data-stu-id="79f92-163">You must specify the enumeration type name when you use enumeration constants.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4802.fs)]

## <a name="identifier-patterns"></a><span data-ttu-id="79f92-164">Bezeichnermuster</span><span class="sxs-lookup"><span data-stu-id="79f92-164">Identifier Patterns</span></span>
<span data-ttu-id="79f92-165">Wenn das Muster eine Zeichenfolge ist, die einen gültigen Bezeichner bildet, bestimmt die Form des Bezeichners, wie das Muster verglichen wird.</span><span class="sxs-lookup"><span data-stu-id="79f92-165">If the pattern is a string of characters that forms a valid identifier, the form of the identifier determines how the pattern is matched.</span></span> <span data-ttu-id="79f92-166">Wenn der Bezeichner länger als ein einzelnes Zeichen ist und mit einem Großbuchstaben beginnt, versucht der Compiler, eine Übereinstimmung mit dem Bezeichnermuster zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="79f92-166">If the identifier is longer than a single character and starts with an uppercase character, the compiler tries to make a match to the identifier pattern.</span></span> <span data-ttu-id="79f92-167">Der Bezeichner für dieses Muster kann ein Wert sein, der mit dem Literal-Attribut, einem Unterscheidungs-Union-Fall, einem Ausnahmebezeichner oder einem Fall eines aktiven Musters markiert wurde.</span><span class="sxs-lookup"><span data-stu-id="79f92-167">The identifier for this pattern could be a value marked with the Literal attribute, a discriminated union case, an exception identifier, or an active pattern case.</span></span> <span data-ttu-id="79f92-168">Wenn kein übereinstimmender Bezeichner gefunden wird, schlägt der Vergleich fehl, und die nächste Musterregel, das Variablenmuster, wird mit der Eingabe verglichen.</span><span class="sxs-lookup"><span data-stu-id="79f92-168">If no matching identifier is found, the match fails and the next pattern rule, the variable pattern, is compared to the input.</span></span>

<span data-ttu-id="79f92-169">Unterscheidungs-Union-Muster können einfache benannte Fälle sein oder über einen Wert bzw. über ein mehrere Werte enthaltendes Tupel verfügen.</span><span class="sxs-lookup"><span data-stu-id="79f92-169">Discriminated union patterns can be simple named cases or they can have a value, or a tuple containing multiple values.</span></span> <span data-ttu-id="79f92-170">Wenn ein Wert vorhanden ist, müssen Sie einen Bezeichner für den Wert angeben.</span><span class="sxs-lookup"><span data-stu-id="79f92-170">If there is a value, you must specify an identifier for the value.</span></span> <span data-ttu-id="79f92-171">Im Fall eines Tupels müssen Sie ein Tupelmuster mit einem Bezeichner für jedes Element des Tupels oder einen Bezeichner mit einem Feldnamen für eine oder mehrere benannte Union-Felder angeben.</span><span class="sxs-lookup"><span data-stu-id="79f92-171">In the case of a tuple, you must supply a tuple pattern with an identifier for each element of the tuple or an identifier with a field name for one or more named union fields.</span></span> <span data-ttu-id="79f92-172">Entsprechende Beispiele finden Sie in den Codebeispielen dieses Abschnitts.</span><span class="sxs-lookup"><span data-stu-id="79f92-172">See the code examples in this section for examples.</span></span>

<span data-ttu-id="79f92-173">Der `option`-Typ ist eine Unterscheidungs-Union mit den beiden Fällen `Some` und `None`.</span><span class="sxs-lookup"><span data-stu-id="79f92-173">The `option` type is a discriminated union that has two cases, `Some` and `None`.</span></span> <span data-ttu-id="79f92-174">Ein Fall (`Some`) verfügt über einen Wert, der andere Fall (`None`) ist jedoch lediglich ein benannter Fall.</span><span class="sxs-lookup"><span data-stu-id="79f92-174">One case (`Some`) has a value, but the other (`None`) is just a named case.</span></span> <span data-ttu-id="79f92-175">Daher muss `Some` über eine Variable für den dem Fall `Some` zugeordneten Wert verfügen, `None` muss jedoch als None angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="79f92-175">Therefore, `Some` needs to have a variable for the value associated with the `Some` case, but `None` must appear by itself.</span></span> <span data-ttu-id="79f92-176">Im folgenden Code wird der Variablen `var1` der Wert zugewiesen, der durch den Vergleich mit dem Fall `Some` ermittelt wurde.</span><span class="sxs-lookup"><span data-stu-id="79f92-176">In the following code, the variable `var1` is given the value that is obtained by matching to the `Some` case.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4803.fs)]

<span data-ttu-id="79f92-177">Im folgenden Beispiel enthält die Unterscheidungs-Union `PersonName` eine Kombination von Zeichenfolgen und Zeichen, die mögliche Formen von Namen darstellen.</span><span class="sxs-lookup"><span data-stu-id="79f92-177">In the following example, the `PersonName` discriminated union contains a mixture of strings and characters that represent possible forms of names.</span></span> <span data-ttu-id="79f92-178">Die Fälle der Unterscheidungs-Union lauten `FirstOnly`, `LastOnly` und `FirstLast`.</span><span class="sxs-lookup"><span data-stu-id="79f92-178">The cases of the discriminated union are `FirstOnly`, `LastOnly`, and `FirstLast`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4804.fs)]

<span data-ttu-id="79f92-179">Für Unterscheidungs-Unions, die über benannte Felder verfügen, verwenden Sie das Gleichheitszeichen (=), um den Wert eines benannten Felds zu extrahieren.</span><span class="sxs-lookup"><span data-stu-id="79f92-179">For discriminated unions that have named fields, you use the equals sign (=) to extract the value of a named field.</span></span> <span data-ttu-id="79f92-180">Betrachten Sie zum Beispiel eine Unterscheidungs-Union mit einer Deklaration wie der folgenden.</span><span class="sxs-lookup"><span data-stu-id="79f92-180">For example, consider a discriminated union with a declaration like the following.</span></span>

```fsharp
type Shape =
    | Rectangle of height : float * width : float
    | Circle of radius : float
```

<span data-ttu-id="79f92-181">Sie können die benannten Felder in einem Mustervergleichsausdruck wie folgt verwenden.</span><span class="sxs-lookup"><span data-stu-id="79f92-181">You can use the named fields in a pattern matching expression as follows.</span></span>

```fsharp
let matchShape shape =
    match shape with
    | Rectangle(height = h) -> printfn "Rectangle with length %f" h
    | Circle(r) -> printfn "Circle with radius %f" r
```

<span data-ttu-id="79f92-182">Die Verwendung des benannten Felds ist optional. Im vorherigen Beispiel haben `Circle(r)` und `Circle(radius = r)` die gleiche Auswirkung.</span><span class="sxs-lookup"><span data-stu-id="79f92-182">The use of the named field is optional, so in the previous example, both `Circle(r)` and `Circle(radius = r)` have the same effect.</span></span>

<span data-ttu-id="79f92-183">Wenn Sie mehrere Felder angeben, verwenden Sie das Semikolon (;) als Trennzeichen.</span><span class="sxs-lookup"><span data-stu-id="79f92-183">When you specify multiple fields, use the semicolon (;) as a separator.</span></span>

```
match shape with
| Rectangle(height = h; width = w) -> printfn "Rectangle with height %f and width %f" h w
| _ -> ()
```

<span data-ttu-id="79f92-184">Mit aktiven Mustern können Sie komplexere benutzerdefinierte Musterabgleiche definieren.</span><span class="sxs-lookup"><span data-stu-id="79f92-184">Active patterns enable you to define more complex custom pattern matching.</span></span> <span data-ttu-id="79f92-185">Weitere Informationen über aktive Muster finden Sie unter [mit aktiven Mustern](active-patterns.md).</span><span class="sxs-lookup"><span data-stu-id="79f92-185">For more information about active patterns, see [Active Patterns](active-patterns.md).</span></span>

<span data-ttu-id="79f92-186">Der Fall, in dem der Bezeichner eine Ausnahme ist, wird beim Musterabgleich im Kontext von Ausnahmehandlern verwendet.</span><span class="sxs-lookup"><span data-stu-id="79f92-186">The case in which the identifier is an exception is used in pattern matching in the context of exception handlers.</span></span> <span data-ttu-id="79f92-187">Informationen über Mustervergleich bei der Behandlung von Ausnahmen finden Sie unter [Ausnahmen: die `try...with` Ausdruck](exception-handling/the-try-with-expression.md).</span><span class="sxs-lookup"><span data-stu-id="79f92-187">For information about pattern matching in exception handling, see [Exceptions: The `try...with` Expression](exception-handling/the-try-with-expression.md).</span></span>


## <a name="variable-patterns"></a><span data-ttu-id="79f92-188">Variablenmuster</span><span class="sxs-lookup"><span data-stu-id="79f92-188">Variable Patterns</span></span>
<span data-ttu-id="79f92-189">Im Variablenmuster wird dem zu vergleichenden Wert ein Variablenname zugewiesen, der dann im Ausführungsausdruck auf der rechten Seite des Symbols `->` verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="79f92-189">The variable pattern assigns the value being matched to a variable name, which is then available for use in the execution expression to the right of the `->` symbol.</span></span> <span data-ttu-id="79f92-190">Ein Variablenmuster an sich stimmt mit jeder Eingabe überein, jedoch sind Variablenmuster häufig in anderen Mustern enthalten und ermöglichen somit komplexere Strukturen, z. B. Tupel und Arrays, die in Variablen zerlegt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="79f92-190">A variable pattern alone matches any input, but variable patterns often appear within other patterns, therefore enabling more complex structures such as tuples and arrays to be decomposed into variables.</span></span>

<span data-ttu-id="79f92-191">Im folgenden Beispiel wird ein Variablenmuster in einem Tupelmuster veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="79f92-191">The following example demonstrates a variable pattern within a tuple pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4805.fs)]

## <a name="as-pattern"></a><span data-ttu-id="79f92-192">as-Muster</span><span class="sxs-lookup"><span data-stu-id="79f92-192">as Pattern</span></span>
<span data-ttu-id="79f92-193">Das `as`-Muster ist ein Muster, an das eine `as`-Klausel angefügt ist.</span><span class="sxs-lookup"><span data-stu-id="79f92-193">The `as` pattern is a pattern that has an `as` clause appended to it.</span></span> <span data-ttu-id="79f92-194">Die `as`-Klausel bindet den übereinstimmenden Wert an einen Namen, der im Ausführungsausdruck eines `match`-Ausdrucks verwendet werden kann. Falls das Muster in einer `let`-Bindung verwendet wird, wird stattdessen der Name dem lokalen Bereich als Bindung hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="79f92-194">The `as` clause binds the matched value to a name that can be used in the execution expression of a `match` expression, or, in the case where this pattern is used in a `let` binding, the name is added as a binding to the local scope.</span></span>

<span data-ttu-id="79f92-195">Im folgenden Beispiel wird ein `as`-Muster verwendet.</span><span class="sxs-lookup"><span data-stu-id="79f92-195">The following example uses an `as` pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4806.fs)]

## <a name="or-pattern"></a><span data-ttu-id="79f92-196">OR-Muster</span><span class="sxs-lookup"><span data-stu-id="79f92-196">OR Pattern</span></span>
<span data-ttu-id="79f92-197">Das OR-Muster wird verwendet, wenn Eingabedaten mit mehreren Mustern übereinstimmen können und als Ergebnis der gleiche Code ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="79f92-197">The OR pattern is used when input data can match multiple patterns, and you want to execute the same code as a result.</span></span> <span data-ttu-id="79f92-198">Die Typen beider Seiten des OR-Musters müssen kompatibel sein.</span><span class="sxs-lookup"><span data-stu-id="79f92-198">The types of both sides of the OR pattern must be compatible.</span></span>

<span data-ttu-id="79f92-199">Das OR-Muster wird im folgenden Beispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="79f92-199">The following example demonstrates the OR pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4807.fs)]

## <a name="and-pattern"></a><span data-ttu-id="79f92-200">AND-Muster</span><span class="sxs-lookup"><span data-stu-id="79f92-200">AND Pattern</span></span>
<span data-ttu-id="79f92-201">Das AND-Muster erfordert, dass die Eingabe mit zwei Mustern übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="79f92-201">The AND pattern requires that the input match two patterns.</span></span> <span data-ttu-id="79f92-202">Die Typen beider Seiten des AND-Musters müssen kompatibel sein.</span><span class="sxs-lookup"><span data-stu-id="79f92-202">The types of both sides of the AND pattern must be compatible.</span></span>

<span data-ttu-id="79f92-203">Im folgende Beispiel wird z. B. `detectZeroTuple` angezeigt, der [Tupelmuster](https://msdn.microsoft.com/library/#tuple) Abschnitt weiter unten in diesem Thema, jedoch werden hier `var1` und `var2` unter Verwendung des AND-Musters als Werte abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="79f92-203">The following example is like `detectZeroTuple` shown in the [Tuple Pattern](https://msdn.microsoft.com/library/#tuple) section later in this topic, but here both `var1` and `var2` are obtained as values by using the AND pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4808.fs)]

## <a name="cons-pattern"></a><span data-ttu-id="79f92-204">Cons-Muster</span><span class="sxs-lookup"><span data-stu-id="79f92-204">Cons Pattern</span></span>
<span data-ttu-id="79f92-205">Cons-Muster wird verwendet, um eine Liste in das erste Element zu zerlegen der *Head*, und eine Liste mit den restlichen Elementen der *Tail*.</span><span class="sxs-lookup"><span data-stu-id="79f92-205">The cons pattern is used to decompose a list into the first element, the *head*, and a list that contains the remaining elements, the *tail*.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4809.fs)]

## <a name="list-pattern"></a><span data-ttu-id="79f92-206">Listenmuster</span><span class="sxs-lookup"><span data-stu-id="79f92-206">List Pattern</span></span>
<span data-ttu-id="79f92-207">Mit dem Listenmuster können Listen in eine Reihe von Elementen zerlegt werden.</span><span class="sxs-lookup"><span data-stu-id="79f92-207">The list pattern enables lists to be decomposed into a number of elements.</span></span> <span data-ttu-id="79f92-208">Das Listenmuster selbst darf nur mit Listen einer bestimmten Anzahl von Elementen übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="79f92-208">The list pattern itself can match only lists of a specific number of elements.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4810.fs)]

## <a name="array-pattern"></a><span data-ttu-id="79f92-209">Arraymuster</span><span class="sxs-lookup"><span data-stu-id="79f92-209">Array Pattern</span></span>
<span data-ttu-id="79f92-210">Das Arraymuster ähnelt dem Listenmuster, und es kann zum Zerlegen von Arrays einer bestimmten Länge verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="79f92-210">The array pattern resembles the list pattern and can be used to decompose arrays of a specific length.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4811.fs)]

## <a name="parenthesized-pattern"></a><span data-ttu-id="79f92-211">Muster in Klammern</span><span class="sxs-lookup"><span data-stu-id="79f92-211">Parenthesized Pattern</span></span>
<span data-ttu-id="79f92-212">Muster können in Klammern eingeschlossen werden, um die gewünschte Assoziativität zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="79f92-212">Parentheses can be grouped around patterns to achieve the desired associativity.</span></span> <span data-ttu-id="79f92-213">Im folgenden Beispiel werden Klammern verwendet, um die Assoziativität zwischen einem AND-Muster und einem Cons-Muster zu steuern.</span><span class="sxs-lookup"><span data-stu-id="79f92-213">In the following example, parentheses are used to control associativity between an AND pattern and a cons pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4812.fs)]

## <a name="tuple-pattern"></a><span data-ttu-id="79f92-214">Tupelmuster</span><span class="sxs-lookup"><span data-stu-id="79f92-214">Tuple Pattern</span></span>
<span data-ttu-id="79f92-215">Mithilfe des Tupelmusters werden Eingabe in Tupelform verglichen. Es ermöglicht das Zerlegen des Tupels in seine Bestandteile mithilfe von Mustervergleichsvariablen für die einzelnen Positionen im Tupel.</span><span class="sxs-lookup"><span data-stu-id="79f92-215">The tuple pattern matches input in tuple form and enables the tuple to be decomposed into its constituent elements by using pattern matching variables for each position in the tuple.</span></span>

<span data-ttu-id="79f92-216">Im folgenden Beispiel wird die Verwendung des Tupelmusters veranschaulicht, und es werden außerdem Literalmuster, Variablenmuster und das Platzhaltermuster verwendet.</span><span class="sxs-lookup"><span data-stu-id="79f92-216">The following example demonstrates the tuple pattern and also uses literal patterns, variable patterns, and the wildcard pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4813.fs)]

## <a name="record-pattern"></a><span data-ttu-id="79f92-217">Datensatzmuster</span><span class="sxs-lookup"><span data-stu-id="79f92-217">Record Pattern</span></span>
<span data-ttu-id="79f92-218">Mit dem Datensatzmuster werden Datensätze zerlegt, um die Werte von Feldern zu extrahieren.</span><span class="sxs-lookup"><span data-stu-id="79f92-218">The record pattern is used to decompose records to extract the values of fields.</span></span> <span data-ttu-id="79f92-219">Das Muster muss nicht auf alle Felder des Datensatzes verweisen. Weggelassene Felder werden nicht verglichen und nicht extrahiert.</span><span class="sxs-lookup"><span data-stu-id="79f92-219">The pattern does not have to reference all fields of the record; any omitted fields just do not participate in matching and are not extracted.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4814.fs)]

## <a name="wildcard-pattern"></a><span data-ttu-id="79f92-220">Platzhaltermuster</span><span class="sxs-lookup"><span data-stu-id="79f92-220">Wildcard Pattern</span></span>
<span data-ttu-id="79f92-221">Das Platzhaltermuster wird durch den Unterstrich (`_`) dargestellt und stimmt wie das Variablenmuster mit jeder Eingabe überein, außer dass die Eingabe verworfen wird, anstatt einer Variablen zugewiesen zu werden.</span><span class="sxs-lookup"><span data-stu-id="79f92-221">The wildcard pattern is represented by the underscore (`_`) character and matches any input, just like the variable pattern, except that the input is discarded instead of assigned to a variable.</span></span> <span data-ttu-id="79f92-222">Das Platzhaltermuster wird oft innerhalb anderer Muster als Platzhalter für Werte verwendet, die im Ausdruck auf der rechten Seite des Symbols `->` nicht benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="79f92-222">The wildcard pattern is often used within other patterns as a placeholder for values that are not needed in the expression to the right of the `->` symbol.</span></span> <span data-ttu-id="79f92-223">Das Platzhaltermuster wird außerdem häufig am Ende einer Liste von Mustern als Übereinstimmung für jede nicht übereinstimmende Eingabe verwendet.</span><span class="sxs-lookup"><span data-stu-id="79f92-223">The wildcard pattern is also frequently used at the end of a list of patterns to match any unmatched input.</span></span> <span data-ttu-id="79f92-224">Das Platzhaltermuster wird in vielen Codebeispielen dieses Themas veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="79f92-224">The wildcard pattern is demonstrated in many code examples in this topic.</span></span> <span data-ttu-id="79f92-225">Ein Beispiel finden Sie im vorangehenden Code.</span><span class="sxs-lookup"><span data-stu-id="79f92-225">See the preceding code for one example.</span></span>


## <a name="patterns-that-have-type-annotations"></a><span data-ttu-id="79f92-226">Muster mit Typanmerkungen</span><span class="sxs-lookup"><span data-stu-id="79f92-226">Patterns That Have Type Annotations</span></span>
<span data-ttu-id="79f92-227">Muster können Typanmerkungen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="79f92-227">Patterns can have type annotations.</span></span> <span data-ttu-id="79f92-228">Diese verhalten sich wie andere Typanmerkungen und steuern Typrückschluss wie diese.</span><span class="sxs-lookup"><span data-stu-id="79f92-228">These behave like other type annotations and guide inference like other type annotations.</span></span> <span data-ttu-id="79f92-229">Typanmerkungen in Mustern müssen in Klammern eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="79f92-229">Parentheses are required around type annotations in patterns.</span></span> <span data-ttu-id="79f92-230">Im folgenden Code wird ein Muster veranschaulicht, das eine Typanmerkung aufweist.</span><span class="sxs-lookup"><span data-stu-id="79f92-230">The following code shows a pattern that has a type annotation.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4815.fs)]

## <a name="type-test-pattern"></a><span data-ttu-id="79f92-231">Typtestmuster</span><span class="sxs-lookup"><span data-stu-id="79f92-231">Type Test Pattern</span></span>
<span data-ttu-id="79f92-232">Das Typtestmuster wird verwendet, um die Eingabe anhand eines Typs zu vergleichen.</span><span class="sxs-lookup"><span data-stu-id="79f92-232">The type test pattern is used to match the input against a type.</span></span> <span data-ttu-id="79f92-233">Wenn der Eingabetyp mit dem im Muster angegebenen Typ oder einem von diesem abgeleiteten Typ übereinstimmt, ist der Vergleich erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="79f92-233">If the input type is a match to (or a derived type of) the type specified in the pattern, the match succeeds.</span></span>

<span data-ttu-id="79f92-234">Das Typtestmuster wird im folgenden Beispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="79f92-234">The following example demonstrates the type test pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4816.fs)]

## <a name="null-pattern"></a><span data-ttu-id="79f92-235">NULL-Muster</span><span class="sxs-lookup"><span data-stu-id="79f92-235">Null Pattern</span></span>
<span data-ttu-id="79f92-236">Das NULL-Muster wird mit dem NULL-Wert verglichen, der beim Arbeiten mit Typen, die NULL-Werte zulassen, vorhanden sein kann.</span><span class="sxs-lookup"><span data-stu-id="79f92-236">The null pattern matches the null value that can appear when you are working with types that allow a null value.</span></span> <span data-ttu-id="79f92-237">NULL-Muster werden häufig verwendet, bei der Interaktion mit .NET Framework-Code.</span><span class="sxs-lookup"><span data-stu-id="79f92-237">Null patterns are frequently used when interoperating with .NET Framework code.</span></span> <span data-ttu-id="79f92-238">Beispielsweise kann der Rückgabewert einer .NET-API die Eingabe für einen `match`-Ausdruck sein.</span><span class="sxs-lookup"><span data-stu-id="79f92-238">For example, the return value of a .NET API might be the input to a `match` expression.</span></span> <span data-ttu-id="79f92-239">Die Steuerung des Programmablaufs kann von Eigenschaften des Rückgabewerts abhängig gemacht werden, beispielsweise davon, ob der Rückgabewert NULL ist.</span><span class="sxs-lookup"><span data-stu-id="79f92-239">You can control program flow based on whether the return value is null, and also on other characteristics of the returned value.</span></span> <span data-ttu-id="79f92-240">Mithilfe des NULL-Musters können Sie verhindern, dass NULL-Werte an den Rest des Programms weitergegeben werden.</span><span class="sxs-lookup"><span data-stu-id="79f92-240">You can use the null pattern to prevent null values from propagating to the rest of your program.</span></span>

<span data-ttu-id="79f92-241">Im folgenden Beispiel werden das NULL-Muster und das Variablenmuster verwendet.</span><span class="sxs-lookup"><span data-stu-id="79f92-241">The following example uses the null pattern and the variable pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4817.fs)]

## <a name="see-also"></a><span data-ttu-id="79f92-242">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="79f92-242">See Also</span></span>
[<span data-ttu-id="79f92-243">Vergleichsausdrücke</span><span class="sxs-lookup"><span data-stu-id="79f92-243">Match Expressions</span></span>](match-expressions.md)

[<span data-ttu-id="79f92-244">Aktive Muster</span><span class="sxs-lookup"><span data-stu-id="79f92-244">Active Patterns</span></span>](active-patterns.md)

[<span data-ttu-id="79f92-245">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="79f92-245">F# Language Reference</span></span>](index.md)