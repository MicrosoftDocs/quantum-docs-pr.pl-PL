---
title: 'Biblioteki Q # standardowe — konwersje typów | Microsoft Docs'
description: 'Biblioteki Q # standardowe — konwersje typów'
author: cgranade
uid: microsoft.quantum.libraries.convert
ms.author: chgranad@microsoft.com
ms.topic: article
ms.openlocfilehash: 4716f0d9562229f08ef6f0f5f80961f793de4c5c
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2019
ms.locfileid: "73184478"
---
# <a name="type-conversions"></a><span data-ttu-id="3e036-103">Konwersje typów</span><span class="sxs-lookup"><span data-stu-id="3e036-103">Type Conversions</span></span> #

<span data-ttu-id="3e036-104">Q # to język o **jednoznacznie określonym typie** .</span><span class="sxs-lookup"><span data-stu-id="3e036-104">Q# is a **strongly-typed** language.</span></span>
<span data-ttu-id="3e036-105">W szczególności polecenie Q # nie niejawnie rzutuje między różnymi typami.</span><span class="sxs-lookup"><span data-stu-id="3e036-105">In particular, Q# does not implicitly cast between distinct types.</span></span> <span data-ttu-id="3e036-106">Na przykład `1 + 2.0` nie jest prawidłowym wyrażeniem Q #.</span><span class="sxs-lookup"><span data-stu-id="3e036-106">For instance, `1 + 2.0` is not a valid Q# expression.</span></span>
<span data-ttu-id="3e036-107">Zamiast tego funkcja Q # zapewnia różnorodne funkcje konwersji typów do konstruowania nowych wartości danego typu.</span><span class="sxs-lookup"><span data-stu-id="3e036-107">Rather, Q# provides a variety of type conversion functions for constructing new values of a given type.</span></span>

<span data-ttu-id="3e036-108">Na przykład <xref:microsoft.quantum.core.length> ma typ danych wyjściowych `Int`, dlatego dane wyjściowe muszą zostać najpierw skonwertowane na `Double`, zanim będzie można go użyć jako części wyrażenia zmiennoprzecinkowego.</span><span class="sxs-lookup"><span data-stu-id="3e036-108">For example, <xref:microsoft.quantum.core.length> has an output type of `Int`, so its output must first be converted to a `Double` before it can be used as a part of a floating-point expression.</span></span>
<span data-ttu-id="3e036-109">Można to zrobić za pomocą funkcji <xref:microsoft.quantum.convert.intasdouble>:</span><span class="sxs-lookup"><span data-stu-id="3e036-109">This can be done using the <xref:microsoft.quantum.convert.intasdouble> function:</span></span>

```qsharp
open Microsoft.Quantum.Convert as Convert;

function HalfLength<'T>(arr : 'T[]) : Double {
    return Convert.IntAsDouble(Length(arr)) / 2.0;
}
```

<span data-ttu-id="3e036-110">Przestrzeń nazw <xref:microsoft.quantum.convert> zawiera wspólne funkcje konwersji typów do pracy z podstawowymi wbudowanymi typami, takimi jak `Int`, `Double`, `BigInt`, `Result`i `Bool`:</span><span class="sxs-lookup"><span data-stu-id="3e036-110">The <xref:microsoft.quantum.convert> namespace provides common type conversion functions for working with the basic built-in types, such as `Int`, `Double`, `BigInt`, `Result`, and `Bool`:</span></span>

```qsharp
let bool = Convert.ResultAsBool(One);        // true
let big = Convert.IntAsBigInt(271);          // 271L
let indices = Convert.RangeAsIntArray(0..4); // [0, 1, 2, 3, 4]
```

<span data-ttu-id="3e036-111">Przestrzeń nazw <xref:microsoft.quantum.convert> udostępnia również kilka bardziej egzotycznych konwersji, takich jak `FunctionAsOperation`, które konwertują funkcje `'T -> 'U` na nowe operacje `'T => 'U`.</span><span class="sxs-lookup"><span data-stu-id="3e036-111">The <xref:microsoft.quantum.convert> namespace also provides some more exotic conversions, such as `FunctionAsOperation`, which converts functions `'T -> 'U` into new operations `'T => 'U`.</span></span>

<span data-ttu-id="3e036-112">Na koniec standardowa biblioteka Q # zawiera wiele typów zdefiniowanych przez użytkownika, takich jak <xref:microsoft.quantum.math.complex> i <xref:microsoft.quantum.arithmetic.littleendian>.</span><span class="sxs-lookup"><span data-stu-id="3e036-112">Finally, the Q# standard library provides a number of user-defined types such as <xref:microsoft.quantum.math.complex> and <xref:microsoft.quantum.arithmetic.littleendian>.</span></span>
<span data-ttu-id="3e036-113">Wraz z tymi typami Biblioteka standardowa zawiera funkcje, takie jak <xref:microsoft.quantum.arithmetic.bigendianaslittleendian>:</span><span class="sxs-lookup"><span data-stu-id="3e036-113">Along with these types, the standard library provides functions such as <xref:microsoft.quantum.arithmetic.bigendianaslittleendian>:</span></span>

```Q#
open Microsoft.Quantum.Arithmetic as Arithmetic;

let register = Arithmetic.BigEndian(qubits);
IncrementByInteger(Arithmetic.BigEndianAsLittleEndian(register));
```
