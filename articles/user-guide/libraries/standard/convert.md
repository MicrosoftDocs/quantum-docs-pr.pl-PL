---
title: Konwersje typów w Q# bibliotekach standardowych
description: Poznaj typowe i zdefiniowane przez użytkownika funkcje konwersji typów w Q# bibliotekach standardowych.
author: cgranade
uid: microsoft.quantum.libraries.convert
ms.author: chgranad
ms.topic: article
no-loc:
- Q#
- $$v
ms.openlocfilehash: aa8a1ad624067906998d2735c7a95174a163ce97
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835608"
---
# <a name="type-conversions"></a><span data-ttu-id="01d44-103">Konwersje typu</span><span class="sxs-lookup"><span data-stu-id="01d44-103">Type Conversions</span></span> #

<span data-ttu-id="01d44-104">Q# jest językiem o **jednoznacznie określonym typie** .</span><span class="sxs-lookup"><span data-stu-id="01d44-104">Q# is a **strongly-typed** language.</span></span>
<span data-ttu-id="01d44-105">W szczególności nie Q# rzutuje niejawnie między różnymi typami.</span><span class="sxs-lookup"><span data-stu-id="01d44-105">In particular, Q# does not implicitly cast between distinct types.</span></span> <span data-ttu-id="01d44-106">Na przykład `1 + 2.0` nie jest prawidłowym Q# wyrażeniem.</span><span class="sxs-lookup"><span data-stu-id="01d44-106">For instance, `1 + 2.0` is not a valid Q# expression.</span></span>
<span data-ttu-id="01d44-107">Zamiast tego Q# oferuje różne funkcje konwersji typów do konstruowania nowych wartości danego typu.</span><span class="sxs-lookup"><span data-stu-id="01d44-107">Rather, Q# provides a variety of type conversion functions for constructing new values of a given type.</span></span>

<span data-ttu-id="01d44-108">Na przykład <xref:microsoft.quantum.core.length> ma typ danych wyjściowych `Int` , więc jego dane wyjściowe muszą być najpierw konwertowane na, `Double` zanim będzie można go użyć jako części wyrażenia zmiennoprzecinkowego.</span><span class="sxs-lookup"><span data-stu-id="01d44-108">For example, <xref:microsoft.quantum.core.length> has an output type of `Int`, so its output must first be converted to a `Double` before it can be used as a part of a floating-point expression.</span></span>
<span data-ttu-id="01d44-109">Można to zrobić za pomocą <xref:microsoft.quantum.convert.intasdouble> funkcji:</span><span class="sxs-lookup"><span data-stu-id="01d44-109">This can be done using the <xref:microsoft.quantum.convert.intasdouble> function:</span></span>

```qsharp
open Microsoft.Quantum.Convert as Convert;

function HalfLength<'T>(arr : 'T[]) : Double {
    return Convert.IntAsDouble(Length(arr)) / 2.0;
}
```

<span data-ttu-id="01d44-110"><xref:microsoft.quantum.convert>Przestrzeń nazw zawiera typowe funkcje konwersji typów do pracy z podstawowymi wbudowanymi typami, takimi jak `Int` ,,, `Double` `BigInt` `Result` i `Bool` :</span><span class="sxs-lookup"><span data-stu-id="01d44-110">The <xref:microsoft.quantum.convert> namespace provides common type conversion functions for working with the basic built-in types, such as `Int`, `Double`, `BigInt`, `Result`, and `Bool`:</span></span>

```qsharp
let bool = Convert.ResultAsBool(One);        // true
let big = Convert.IntAsBigInt(271);          // 271L
let indices = Convert.RangeAsIntArray(0..4); // [0, 1, 2, 3, 4]
```

<span data-ttu-id="01d44-111"><xref:microsoft.quantum.convert>Przestrzeń nazw udostępnia również kilka bardziej egzotycznych konwersji, takich jak `FunctionAsOperation` , które konwertują funkcje `'T -> 'U` na nowe operacje `'T => 'U` .</span><span class="sxs-lookup"><span data-stu-id="01d44-111">The <xref:microsoft.quantum.convert> namespace also provides some more exotic conversions, such as `FunctionAsOperation`, which converts functions `'T -> 'U` into new operations `'T => 'U`.</span></span>

<span data-ttu-id="01d44-112">Na koniec Q# Biblioteka standardowa zawiera wiele typów zdefiniowanych przez użytkownika, takich jak <xref:microsoft.quantum.math.complex> i <xref:microsoft.quantum.arithmetic.littleendian> .</span><span class="sxs-lookup"><span data-stu-id="01d44-112">Finally, the Q# standard library provides a number of user-defined types such as <xref:microsoft.quantum.math.complex> and <xref:microsoft.quantum.arithmetic.littleendian>.</span></span>
<span data-ttu-id="01d44-113">Wraz z tymi typami Biblioteka standardowa udostępnia funkcje takie jak <xref:microsoft.quantum.arithmetic.bigendianaslittleendian> :</span><span class="sxs-lookup"><span data-stu-id="01d44-113">Along with these types, the standard library provides functions such as <xref:microsoft.quantum.arithmetic.bigendianaslittleendian>:</span></span>

```Q#
open Microsoft.Quantum.Arithmetic as Arithmetic;

let register = Arithmetic.BigEndian(qubits);
IncrementByInteger(Arithmetic.BigEndianAsLittleEndian(register));
```
