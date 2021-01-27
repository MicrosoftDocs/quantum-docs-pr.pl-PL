---
uid: Microsoft.Quantum.Math.ModulusI
title: ModulusI, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModulusI
qsharp.summary: Computes the canonical residue of `value` modulo `modulus`.
ms.openlocfilehash: 7bad044db9e2229c85cb3909dc4802bceaee6382
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847289"
---
# <a name="modulusi-function"></a><span data-ttu-id="0206d-102">ModulusI, funkcja</span><span class="sxs-lookup"><span data-stu-id="0206d-102">ModulusI function</span></span>

<span data-ttu-id="0206d-103">Przestrzeń nazw: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="0206d-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="0206d-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0206d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0206d-105">Oblicza pozostałą postać kanoniczną `value` modulo `modulus` .</span><span class="sxs-lookup"><span data-stu-id="0206d-105">Computes the canonical residue of `value` modulo `modulus`.</span></span>

```qsharp
function ModulusI (value : Int, modulus : Int) : Int
```


## <a name="input"></a><span data-ttu-id="0206d-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="0206d-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="0206d-107">wartość: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0206d-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0206d-108">Wartość, dla której jest obliczana pozostała część</span><span class="sxs-lookup"><span data-stu-id="0206d-108">The value of which residue is computed</span></span>


### <a name="modulus--int"></a><span data-ttu-id="0206d-109">Moduł: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0206d-109">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0206d-110">Moduł, w którym są pożądane pozostałości, musi być dodatni</span><span class="sxs-lookup"><span data-stu-id="0206d-110">The modulus by which residues are take, must be positive</span></span>



## <a name="output--int"></a><span data-ttu-id="0206d-111">Wynik: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0206d-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0206d-112">Liczba całkowita $r $ między 0 i `modulus - 1` taka, która `value - r` jest podzielna przez moduł</span><span class="sxs-lookup"><span data-stu-id="0206d-112">Integer $r$ between 0 and `modulus - 1` such that `value - r` is divisible by modulus</span></span>

## <a name="remarks"></a><span data-ttu-id="0206d-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="0206d-113">Remarks</span></span>

<span data-ttu-id="0206d-114">Ta funkcja zachowuje się inaczej, jak działa operator `%` w C# i Q # AS w wyniku jest zawsze nieujemną liczbą całkowitą z zakresu od 0 do `modulus - 1` , nawet jeśli wartość jest ujemna.</span><span class="sxs-lookup"><span data-stu-id="0206d-114">This function behaves different to how the operator `%` behaves in C# and Q# as in the result is always a non-negative integer between 0 and `modulus - 1`, even if value is negative.</span></span>