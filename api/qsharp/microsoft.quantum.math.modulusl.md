---
uid: Microsoft.Quantum.Math.ModulusL
title: Funkcja modułu
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModulusL
qsharp.summary: Computes the canonical residue of `value` modulo `modulus`.
ms.openlocfilehash: 6be2edb052cf55f8e8465c76b5dcadeb61ff11ea
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842742"
---
# <a name="modulusl-function"></a><span data-ttu-id="c60ff-102">Funkcja modułu</span><span class="sxs-lookup"><span data-stu-id="c60ff-102">ModulusL function</span></span>

<span data-ttu-id="c60ff-103">Przestrzeń nazw: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="c60ff-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="c60ff-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c60ff-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c60ff-105">Oblicza pozostałą postać kanoniczną `value` modulo `modulus` .</span><span class="sxs-lookup"><span data-stu-id="c60ff-105">Computes the canonical residue of `value` modulo `modulus`.</span></span>

```qsharp
function ModulusL (value : BigInt, modulus : BigInt) : BigInt
```


## <a name="input"></a><span data-ttu-id="c60ff-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="c60ff-106">Input</span></span>

### <a name="value--bigint"></a><span data-ttu-id="c60ff-107">wartość: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="c60ff-107">value : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="c60ff-108">Wartość, dla której jest obliczana pozostała część</span><span class="sxs-lookup"><span data-stu-id="c60ff-108">The value of which residue is computed</span></span>


### <a name="modulus--bigint"></a><span data-ttu-id="c60ff-109">Moduł: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="c60ff-109">modulus : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="c60ff-110">Moduł, w którym są pożądane pozostałości, musi być dodatni</span><span class="sxs-lookup"><span data-stu-id="c60ff-110">The modulus by which residues are take, must be positive</span></span>



## <a name="output--bigint"></a><span data-ttu-id="c60ff-111">Dane wyjściowe: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="c60ff-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="c60ff-112">Liczba całkowita $r $ między 0 i `modulus - 1` taka, która `value - r` jest podzielna przez moduł</span><span class="sxs-lookup"><span data-stu-id="c60ff-112">Integer $r$ between 0 and `modulus - 1` such that `value - r` is divisible by modulus</span></span>

## <a name="remarks"></a><span data-ttu-id="c60ff-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="c60ff-113">Remarks</span></span>

<span data-ttu-id="c60ff-114">Ta funkcja zachowuje się inaczej, jak działa operator `%` w C# i Q # AS w wyniku jest zawsze nieujemną liczbą całkowitą z zakresu od 0 do `modulus - 1` , nawet jeśli wartość jest ujemna.</span><span class="sxs-lookup"><span data-stu-id="c60ff-114">This function behaves different to how the operator `%` behaves in C# and Q# as in the result is always a non-negative integer between 0 and `modulus - 1`, even if value is negative.</span></span>