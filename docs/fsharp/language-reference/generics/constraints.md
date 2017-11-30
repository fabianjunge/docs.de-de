---
title: "Einschränkungen (F#)"
description: "Informationen Sie zu F#-Einschränkungen, die für generische Typparameter an die Anforderungen für die ein Type-Argument in einem generischen Typ oder einer Funktion gültig."
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 2f232a3a-9486-48fb-9759-f23404ed4b52
ms.openlocfilehash: 91854fd2f692688e0f1c27aba1422eff64156048
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="constraints"></a><span data-ttu-id="9178a-104">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="9178a-104">Constraints</span></span>

<span data-ttu-id="9178a-105">In diesem Thema wird beschrieben, Einschränkungen, die Sie für generische gelten können Typparameter an die Anforderungen für die ein Type-Argument in einer generischen Typ- oder Funktion.</span><span class="sxs-lookup"><span data-stu-id="9178a-105">This topic describes constraints that you can apply to generic type parameters to specify the requirements for a type argument in a generic type or function.</span></span>


## <a name="syntax"></a><span data-ttu-id="9178a-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="9178a-106">Syntax</span></span>

```fsharp
type-parameter-list when constraint1 [ and constraint2]
```

## <a name="remarks"></a><span data-ttu-id="9178a-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9178a-107">Remarks</span></span>
<span data-ttu-id="9178a-108">Es gibt mehrere unterschiedliche Einschränkungen, die Sie anwenden können, um die Typen beschränken, die in einem generischen Typ verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="9178a-108">There are several different constraints you can apply to limit the types that can be used in a generic type.</span></span> <span data-ttu-id="9178a-109">In der folgenden Tabelle aufgelistet und beschrieben von diesen Einschränkungen.</span><span class="sxs-lookup"><span data-stu-id="9178a-109">The following table lists and describes these constraints.</span></span>

|<span data-ttu-id="9178a-110">Constraint</span><span class="sxs-lookup"><span data-stu-id="9178a-110">Constraint</span></span>|<span data-ttu-id="9178a-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="9178a-111">Syntax</span></span>|<span data-ttu-id="9178a-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9178a-112">Description</span></span>|
|----------|------|-----------|
|<span data-ttu-id="9178a-113">Typeinschränkung</span><span class="sxs-lookup"><span data-stu-id="9178a-113">Type Constraint</span></span>|<span data-ttu-id="9178a-114">*Typparameter* :&gt; *Typ*</span><span class="sxs-lookup"><span data-stu-id="9178a-114">*type-parameter* :&gt; *type*</span></span>|<span data-ttu-id="9178a-115">Der bereitgestellte Typ muss gleich oder abgeleiteten aus dem angegebenen Typ oder, wenn der Typ eine Schnittstelle ist, muss der angegebene Typ der Schnittstelle implementieren.</span><span class="sxs-lookup"><span data-stu-id="9178a-115">The provided type must be equal to or derived from the type specified, or, if the type is an interface, the provided type must implement the interface.</span></span>|
|<span data-ttu-id="9178a-116">NULL-Einschränkung</span><span class="sxs-lookup"><span data-stu-id="9178a-116">Null Constraint</span></span>|<span data-ttu-id="9178a-117">*Typparameter* : null</span><span class="sxs-lookup"><span data-stu-id="9178a-117">*type-parameter* : null</span></span>|<span data-ttu-id="9178a-118">Der angegebene Typ muss das null-Literal unterstützen.</span><span class="sxs-lookup"><span data-stu-id="9178a-118">The provided type must support the null literal.</span></span> <span data-ttu-id="9178a-119">Dies schließt alle Objekttypen .NET jedoch nicht F#-Liste, Tupel, Funktion, Klasse, Datensatz oder union-Typen.</span><span class="sxs-lookup"><span data-stu-id="9178a-119">This includes all .NET object types but not F# list, tuple, function, class, record, or union types.</span></span>|
|<span data-ttu-id="9178a-120">Explizites Mitglied-Einschränkung</span><span class="sxs-lookup"><span data-stu-id="9178a-120">Explicit Member Constraint</span></span>|<span data-ttu-id="9178a-121">[()]*Typparameter* [oder... oder *Typparameter*)]: (* Membersignatur *)</span><span class="sxs-lookup"><span data-stu-id="9178a-121">[(]*type-parameter* [or ... or *type-parameter*)] : (*member-signature *)</span></span>|<span data-ttu-id="9178a-122">Mindestens eines der bereitgestellten Typargumente benötigen ein Element, das die angegebene Signatur verfügt; nicht für die allgemeine Verwendung vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="9178a-122">At least one of the type arguments provided must have a member that has the specified signature; not intended for common use.</span></span> <span data-ttu-id="9178a-123">Mitglieder müssen entweder explizit auf den Typ oder die Teil einer Erweiterung impliziter Typ werden als gültige Ziele für eine explizite Schnittstellenmember-Einschränkung definiert werden.</span><span class="sxs-lookup"><span data-stu-id="9178a-123">Members must be either explicitly defined on the type or part of an implicit type extension to be valid targets for an Explicit Member Constraint.</span></span>|
|<span data-ttu-id="9178a-124">Konstruktoreinschränkung</span><span class="sxs-lookup"><span data-stu-id="9178a-124">Constructor Constraint</span></span>|<span data-ttu-id="9178a-125">*Typparameter* : (new: Einheit -&gt; "ein)</span><span class="sxs-lookup"><span data-stu-id="9178a-125">*type-parameter* : ( new : unit -&gt; 'a )</span></span>|<span data-ttu-id="9178a-126">Der bereitgestellte Typ muss einen Standardkonstruktor verfügen.</span><span class="sxs-lookup"><span data-stu-id="9178a-126">The provided type must have a default constructor.</span></span>|
|<span data-ttu-id="9178a-127">Werttypeinschränkung</span><span class="sxs-lookup"><span data-stu-id="9178a-127">Value Type Constraint</span></span>|<span data-ttu-id="9178a-128">: Struktur</span><span class="sxs-lookup"><span data-stu-id="9178a-128">: struct</span></span>|<span data-ttu-id="9178a-129">Der angegebene Typ muss ein Werttyp .NET.</span><span class="sxs-lookup"><span data-stu-id="9178a-129">The provided type must be a .NET value type.</span></span>|
|<span data-ttu-id="9178a-130">Reference-Typ-Einschränkung</span><span class="sxs-lookup"><span data-stu-id="9178a-130">Reference Type Constraint</span></span>|<span data-ttu-id="9178a-131">: nicht-Struktur</span><span class="sxs-lookup"><span data-stu-id="9178a-131">: not struct</span></span>|<span data-ttu-id="9178a-132">Der angegebene Typ muss ein Verweistyp .NET.</span><span class="sxs-lookup"><span data-stu-id="9178a-132">The provided type must be a .NET reference type.</span></span>|
|<span data-ttu-id="9178a-133">Enumeration Typeinschränkung</span><span class="sxs-lookup"><span data-stu-id="9178a-133">Enumeration Type Constraint</span></span>|<span data-ttu-id="9178a-134">: Enum&lt;*zugrunde liegenden Typ*&gt;</span><span class="sxs-lookup"><span data-stu-id="9178a-134">: enum&lt;*underlying-type*&gt;</span></span>|<span data-ttu-id="9178a-135">Der bereitgestellte Typ muss ein enumerierter Typ, mit dem angegebenen zugrunde liegenden Datentyp; nicht für die allgemeine Verwendung vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="9178a-135">The provided type must be an enumerated type that has the specified underlying type; not intended for common use.</span></span>|
|<span data-ttu-id="9178a-136">Delegieren der Einschränkung</span><span class="sxs-lookup"><span data-stu-id="9178a-136">Delegate Constraint</span></span>|<span data-ttu-id="9178a-137">: Delegieren&lt;*Tupel Parametertyp*, *Return-Type*&gt;</span><span class="sxs-lookup"><span data-stu-id="9178a-137">: delegate&lt;*tuple-parameter-type*, *return-type*&gt;</span></span>|<span data-ttu-id="9178a-138">Der bereitgestellte Typ muss werden einem Delegattyp als Typ, der die angegebenen Argumenten verfügt und Rückgabewert; nicht für die allgemeine Verwendung vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="9178a-138">The provided type must be a delegate type that has the specified arguments and return value; not intended for common use.</span></span>|
|<span data-ttu-id="9178a-139">Vergleich-Einschränkung</span><span class="sxs-lookup"><span data-stu-id="9178a-139">Comparison Constraint</span></span>|<span data-ttu-id="9178a-140">: Vergleich</span><span class="sxs-lookup"><span data-stu-id="9178a-140">: comparison</span></span>|<span data-ttu-id="9178a-141">Der angegebene Typ muss Vergleich unterstützen.</span><span class="sxs-lookup"><span data-stu-id="9178a-141">The provided type must support comparison.</span></span>|
|<span data-ttu-id="9178a-142">Equality-Einschränkung</span><span class="sxs-lookup"><span data-stu-id="9178a-142">Equality Constraint</span></span>|<span data-ttu-id="9178a-143">: auf Gleichheit</span><span class="sxs-lookup"><span data-stu-id="9178a-143">: equality</span></span>|<span data-ttu-id="9178a-144">Der angegebene Typ muss Gleichheit unterstützen.</span><span class="sxs-lookup"><span data-stu-id="9178a-144">The provided type must support equality.</span></span>|
|<span data-ttu-id="9178a-145">Nicht verwaltete Einschränkung</span><span class="sxs-lookup"><span data-stu-id="9178a-145">Unmanaged Constraint</span></span>|<span data-ttu-id="9178a-146">: nicht verwaltete</span><span class="sxs-lookup"><span data-stu-id="9178a-146">: unmanaged</span></span>|<span data-ttu-id="9178a-147">Der angegebene Typ muss einen nicht verwalteten Typ.</span><span class="sxs-lookup"><span data-stu-id="9178a-147">The provided type must be an unmanaged type.</span></span> <span data-ttu-id="9178a-148">Nicht verwaltete Typen sind entweder bestimmte primitiven Typen (`sbyte`, `byte`, `char`, `nativeint`, `unativeint`, `float32`, `float`, `int16`, `uint16`, `int32`, `uint32`, `int64`, `uint64`, oder `decimal`), Enumerationstypen, `nativeptr&lt;_&gt;`, oder eine nicht generische Struktur, deren Felder alle nicht verwalteten Typen.</span><span class="sxs-lookup"><span data-stu-id="9178a-148">Unmanaged types are either certain primitive types (`sbyte`, `byte`, `char`, `nativeint`, `unativeint`, `float32`, `float`, `int16`, `uint16`, `int32`, `uint32`, `int64`, `uint64`, or `decimal`), enumeration types, `nativeptr&lt;_&gt;`, or a non-generic structure whose fields are all unmanaged types.</span></span>|
<span data-ttu-id="9178a-149">Sie müssen eine Einschränkung hinzufügen, wenn der Code hat eine Funktion verwenden, die in der Regel auf den Einschränkungstyp jedoch nicht für Typen verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="9178a-149">You have to add a constraint when your code has to use a feature that is available on the constraint type but not on types in general.</span></span> <span data-ttu-id="9178a-150">Wenn Sie die Einschränkung des Typs verwenden, um einen Klassentyp anzugeben, können Sie eine der Methoden dieser Klasse in der generischen Funktion oder einen Typ verwenden.</span><span class="sxs-lookup"><span data-stu-id="9178a-150">For example, if you use the type constraint to specify a class type, you can use any one of the methods of that class in the generic function or type.</span></span>

<span data-ttu-id="9178a-151">Angeben von Einschränkungen ist manchmal erforderlich, wenn Typparameter explizit zu schreiben, da ohne Einschränkung, hat der Compiler keine Möglichkeit zu überprüfen, dass die Funktionen, mit dem Sie, auf einen beliebigen Typ zur Verfügung stehen, der zur Laufzeit für den Typ angegeben werden kann Parameter.</span><span class="sxs-lookup"><span data-stu-id="9178a-151">Specifying constraints is sometimes required when writing type parameters explicitly, because without a constraint, the compiler has no way of verifying that the features that you are using will be available on any type that might be supplied at run time for the type parameter.</span></span>

<span data-ttu-id="9178a-152">Die am häufigsten verwendeten Einschränkungen, die in f#-Code verwendet werden, typeinschränkungen, die Basisklassen oder Schnittstellen angeben.</span><span class="sxs-lookup"><span data-stu-id="9178a-152">The most common constraints you use in F# code are type constraints that specify base classes or interfaces.</span></span> <span data-ttu-id="9178a-153">Die anderen Einschränkungen werden entweder von der f#-Bibliothek verwendet, um bestimmte Funktionen, z. B. die Einschränkung explizites Mitglied zu implementieren, wird verwendet, um den Operator für arithmetische Operatoren überladen implementieren oder dienen hauptsächlich da f# das vollständige unterstützt ein Satz von Einschränkungen, die von der common Language Runtime unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="9178a-153">The other constraints are either used by the F# library to implement certain functionality, such as the explicit member constraint, which is used to implement operator overloading for arithmetic operators, or are provided mainly because F# supports the complete set of constraints that is supported by the common language runtime.</span></span>

<span data-ttu-id="9178a-154">Beim Rückschlussprozess Typ sind einige Einschränkungen automatisch vom Compiler abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="9178a-154">During the type inference process, some constraints are inferred automatically by the compiler.</span></span> <span data-ttu-id="9178a-155">Angenommen, Sie verwenden die `+` -Operator in einer Funktion, leitet der Compiler eine explizite Schnittstellenmember-Einschränkung für Variablentypen, die im Ausdruck verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9178a-155">For example, if you use the `+` operator in a function, the compiler infers an explicit member constraint on variable types that are used in the expression.</span></span>

<span data-ttu-id="9178a-156">Der folgende Code zeigt einige Einschränkung Deklarationen.</span><span class="sxs-lookup"><span data-stu-id="9178a-156">The following code illustrates some constraint declarations.</span></span>

```fsharp
// Base Type Constraint
type Class1<'T when 'T :> System.Exception> =
class end

// Interface Type Constraint
type Class2<'T when 'T :> System.IComparable> = 
class end

// Null constraint
type Class3<'T when 'T : null> =
class end

// Member constraint with static member
type Class4<'T when 'T : (static member staticMethod1 : unit -> 'T) > =
class end

// Member constraint with instance member
type Class5<'T when 'T : (member Method1 : 'T -> int)> =
class end

// Member constraint with property
type Class6<'T when 'T : (member Property1 : int)> =
class end

// Constructor constraint
type Class7<'T when 'T : (new : unit -> 'T)>() =
member val Field = new 'T()

// Reference type constraint
type Class8<'T when 'T : not struct> =
class end

// Enumeration constraint with underlying value specified
type Class9<'T when 'T : enum<uint32>> =
class end

// 'T must implement IComparable, or be an array type with comparable
// elements, or be System.IntPtr or System.UIntPtr. Also, 'T must not have
// the NoComparison attribute.
type Class10<'T when 'T : comparison> =
class end

// 'T must support equality. This is true for any type that does not
// have the NoEquality attribute.
type Class11<'T when 'T : equality> =
class end

type Class12<'T when 'T : delegate<obj * System.EventArgs, unit>> =
class end

type Class13<'T when 'T : unmanaged> =
class end

// Member constraints with two type parameters
// Most often used with static type parameters in inline functions
let inline add(value1 : ^T when ^T : (static member (+) : ^T * ^T -> ^T), value2: ^T) =
value1 + value2

// ^T and ^U must support operator +
let inline heterogenousAdd(value1 : ^T when (^T or ^U) : (static member (+) : ^T * ^U -> ^T), value2 : ^U) =
value1 + value2

// If there are multiple constraints, use the and keyword to separate them.
type Class14<'T,'U when 'T : equality and 'U : equality> =
class end
```

## <a name="see-also"></a><span data-ttu-id="9178a-157">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9178a-157">See Also</span></span>
[<span data-ttu-id="9178a-158">Generika</span><span class="sxs-lookup"><span data-stu-id="9178a-158">Generics</span></span>](index.md)

[<span data-ttu-id="9178a-159">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="9178a-159">Constraints</span></span>](constraints.md)