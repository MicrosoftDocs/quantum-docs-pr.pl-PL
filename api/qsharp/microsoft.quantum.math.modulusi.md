---
uid: Microsoft.Quantum.Math.ModulusI
title: ModulusI, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModulusI
qsharp.summary: Computes the canonical residue of `value` modulo `modulus`.
ms.openlocfilehash: 3f698a00b2c8d94b7cb3cca4f1721c659918f4a0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723090"
---
# <a name="modulusi-function"></a><span data-ttu-id="cba92-102">ModulusI, funkcja</span><span class="sxs-lookup"><span data-stu-id="cba92-102">ModulusI function</span></span>

<span data-ttu-id="cba92-103">Przestrzeń nazw: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="cba92-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="cba92-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="cba92-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="cba92-105">Oblicza pozostałą postać kanoniczną `value` modulo `modulus` .</span><span class="sxs-lookup"><span data-stu-id="cba92-105">Computes the canonical residue of `value` modulo `modulus`.</span></span>

```qsharp
function ModulusI (value : Int, modulus : Int) : Int
```


## <a name="input"></a><span data-ttu-id="cba92-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="cba92-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="cba92-107">wartość: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="cba92-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="cba92-108">Wartość, dla której jest obliczana pozostała część</span><span class="sxs-lookup"><span data-stu-id="cba92-108">The value of which residue is computed</span></span>


### <a name="modulus--int"></a><span data-ttu-id="cba92-109">Moduł: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="cba92-109">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="cba92-110">Moduł, w którym są pożądane pozostałości, musi być dodatni</span><span class="sxs-lookup"><span data-stu-id="cba92-110">The modulus by which residues are take, must be positive</span></span>



## <a name="output--int"></a><span data-ttu-id="cba92-111">Wynik: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="cba92-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="cba92-112">Liczba całkowita $r $ między 0 i `modulus - 1` taka, która `value - r` jest podzielna przez moduł</span><span class="sxs-lookup"><span data-stu-id="cba92-112">Integer $r$ between 0 and `modulus - 1` such that `value - r` is divisible by modulus</span></span>

## <a name="remarks"></a><span data-ttu-id="cba92-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="cba92-113">Remarks</span></span>

<span data-ttu-id="cba92-114">Ta funkcja zachowuje się inaczej, jak działa operator `%` w C# i Q # AS w wyniku jest zawsze dodatnią liczbą całkowitą z zakresu od 0 do `modulus - 1` , nawet jeśli wartość jest ujemna.</span><span class="sxs-lookup"><span data-stu-id="cba92-114">This function behaves different to how the operator `%` behaves in C# and Q# as in the result is always a positive integer between 0 and `modulus - 1`, even if value is negative.</span></span>