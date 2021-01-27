---
title: Konwersje typów w Q# bibliotekach standardowych
description: Poznaj typowe i zdefiniowane przez użytkownika funkcje konwersji typów w Q# bibliotekach standardowych.
author: cgranade
uid: microsoft.quantum.libraries.convert
ms.author: chgranad
ms.topic: conceptual
no-loc:
- Q#
- $$v
ms.openlocfilehash: 67f47339363a52097f342c8ae4e43a8a93d606a8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858021"
---
# <a name="type-conversions"></a><span data-ttu-id="0c71f-103">Konwersje typu</span><span class="sxs-lookup"><span data-stu-id="0c71f-103">Type Conversions</span></span> #

<span data-ttu-id="0c71f-104">Q# jest językiem o **jednoznacznie określonym typie** .</span><span class="sxs-lookup"><span data-stu-id="0c71f-104">Q# is a **strongly-typed** language.</span></span>
<span data-ttu-id="0c71f-105">W szczególności nie Q# rzutuje niejawnie między różnymi typami.</span><span class="sxs-lookup"><span data-stu-id="0c71f-105">In particular, Q# does not implicitly cast between distinct types.</span></span> <span data-ttu-id="0c71f-106">Na przykład `1 + 2.0` nie jest prawidłowym Q# wyrażeniem.</span><span class="sxs-lookup"><span data-stu-id="0c71f-106">For instance, `1 + 2.0` is not a valid Q# expression.</span></span>
<span data-ttu-id="0c71f-107">Zamiast tego Q# oferuje różne funkcje konwersji typów do konstruowania nowych wartości danego typu.</span><span class="sxs-lookup"><span data-stu-id="0c71f-107">Rather, Q# provides a variety of type conversion functions for constructing new values of a given type.</span></span>

<span data-ttu-id="0c71f-108">Na przykład <xref:Microsoft.Quantum.Core.Length> ma typ danych wyjściowych `Int` , więc jego dane wyjściowe muszą być najpierw konwertowane na, `Double` zanim będzie można go użyć jako części wyrażenia zmiennoprzecinkowego.</span><span class="sxs-lookup"><span data-stu-id="0c71f-108">For example, <xref:Microsoft.Quantum.Core.Length> has an output type of `Int`, so its output must first be converted to a `Double` before it can be used as a part of a floating-point expression.</span></span>
<span data-ttu-id="0c71f-109">Można to zrobić za pomocą <xref:Microsoft.Quantum.Convert.IntAsDouble> funkcji:</span><span class="sxs-lookup"><span data-stu-id="0c71f-109">This can be done using the <xref:Microsoft.Quantum.Convert.IntAsDouble> function:</span></span>

```qsharp
open Microsoft.Quantum.Convert as Convert;

function HalfLength<'T>(arr : 'T[]) : Double {
    return Convert.IntAsDouble(Length(arr)) / 2.0;
}
```

<span data-ttu-id="0c71f-110"><xref:Microsoft.Quantum.Convert>Przestrzeń nazw zawiera typowe funkcje konwersji typów do pracy z podstawowymi wbudowanymi typami, takimi jak `Int` ,,, `Double` `BigInt` `Result` i `Bool` :</span><span class="sxs-lookup"><span data-stu-id="0c71f-110">The <xref:Microsoft.Quantum.Convert> namespace provides common type conversion functions for working with the basic built-in types, such as `Int`, `Double`, `BigInt`, `Result`, and `Bool`:</span></span>

```qsharp
let bool = Convert.ResultAsBool(One);        // true
let big = Convert.IntAsBigInt(271);          // 271L
let indices = Convert.RangeAsIntArray(0..4); // [0, 1, 2, 3, 4]
```

<span data-ttu-id="0c71f-111"><xref:Microsoft.Quantum.Convert>Przestrzeń nazw udostępnia również kilka bardziej egzotycznych konwersji, takich jak `FunctionAsOperation` , które konwertują funkcje `'T -> 'U` na nowe operacje `'T => 'U` .</span><span class="sxs-lookup"><span data-stu-id="0c71f-111">The <xref:Microsoft.Quantum.Convert> namespace also provides some more exotic conversions, such as `FunctionAsOperation`, which converts functions `'T -> 'U` into new operations `'T => 'U`.</span></span>

<span data-ttu-id="0c71f-112">Na koniec Q# Biblioteka standardowa zawiera wiele typów zdefiniowanych przez użytkownika, takich jak <xref:Microsoft.Quantum.Math.Complex> i <xref:Microsoft.Quantum.Arithmetic.LittleEndian> .</span><span class="sxs-lookup"><span data-stu-id="0c71f-112">Finally, the Q# standard library provides a number of user-defined types such as <xref:Microsoft.Quantum.Math.Complex> and <xref:Microsoft.Quantum.Arithmetic.LittleEndian>.</span></span>
<span data-ttu-id="0c71f-113">Wraz z tymi typami Biblioteka standardowa udostępnia funkcje takie jak <xref:Microsoft.Quantum.Arithmetic.BigEndianAsLittleEndian> :</span><span class="sxs-lookup"><span data-stu-id="0c71f-113">Along with these types, the standard library provides functions such as <xref:Microsoft.Quantum.Arithmetic.BigEndianAsLittleEndian>:</span></span>

```qsharp
open Microsoft.Quantum.Arithmetic as Arithmetic;

let register = Arithmetic.BigEndian(qubits);
IncrementByInteger(Arithmetic.BigEndianAsLittleEndian(register));
```
