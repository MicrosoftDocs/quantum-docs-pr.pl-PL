---
uid: Microsoft.Quantum.Math.ModulusL
title: Funkcja modułu
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModulusL
qsharp.summary: Computes the canonical residue of `value` modulo `modulus`.
ms.openlocfilehash: e7e692059051fde295634c37892ec54e2cf1b095
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725101"
---
# <a name="modulusl-function"></a><span data-ttu-id="4bf6a-102">Funkcja modułu</span><span class="sxs-lookup"><span data-stu-id="4bf6a-102">ModulusL function</span></span>

<span data-ttu-id="4bf6a-103">Przestrzeń nazw: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="4bf6a-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="4bf6a-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4bf6a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4bf6a-105">Oblicza pozostałą postać kanoniczną `value` modulo `modulus` .</span><span class="sxs-lookup"><span data-stu-id="4bf6a-105">Computes the canonical residue of `value` modulo `modulus`.</span></span>

```qsharp
function ModulusL (value : BigInt, modulus : BigInt) : BigInt
```


## <a name="input"></a><span data-ttu-id="4bf6a-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="4bf6a-106">Input</span></span>

### <a name="value--bigint"></a><span data-ttu-id="4bf6a-107">wartość: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="4bf6a-107">value : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="4bf6a-108">Wartość, dla której jest obliczana pozostała część</span><span class="sxs-lookup"><span data-stu-id="4bf6a-108">The value of which residue is computed</span></span>


### <a name="modulus--bigint"></a><span data-ttu-id="4bf6a-109">Moduł: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="4bf6a-109">modulus : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="4bf6a-110">Moduł, w którym są pożądane pozostałości, musi być dodatni</span><span class="sxs-lookup"><span data-stu-id="4bf6a-110">The modulus by which residues are take, must be positive</span></span>



## <a name="output--bigint"></a><span data-ttu-id="4bf6a-111">Dane wyjściowe: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="4bf6a-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="4bf6a-112">Liczba całkowita $r $ między 0 i `modulus - 1` taka, która `value - r` jest podzielna przez moduł</span><span class="sxs-lookup"><span data-stu-id="4bf6a-112">Integer $r$ between 0 and `modulus - 1` such that `value - r` is divisible by modulus</span></span>

## <a name="remarks"></a><span data-ttu-id="4bf6a-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="4bf6a-113">Remarks</span></span>

<span data-ttu-id="4bf6a-114">Ta funkcja zachowuje się inaczej, jak działa operator `%` w C# i Q # AS w wyniku jest zawsze dodatnią liczbą całkowitą z zakresu od 0 do `modulus - 1` , nawet jeśli wartość jest ujemna.</span><span class="sxs-lookup"><span data-stu-id="4bf6a-114">This function behaves different to how the operator `%` behaves in C# and Q# as in the result is always a positive integer between 0 and `modulus - 1`, even if value is negative.</span></span>