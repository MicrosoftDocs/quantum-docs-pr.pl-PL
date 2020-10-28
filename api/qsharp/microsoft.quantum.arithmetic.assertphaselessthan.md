---
uid: Microsoft.Quantum.Arithmetic.AssertPhaseLessThan
title: AssertPhaseLessThan, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertPhaseLessThan
qsharp.summary: Asserts that the `number` encoded in PhaseLittleEndian is less than `value`.
ms.openlocfilehash: d003d83a84356ce52c5601135000813c7f119e4d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721377"
---
# <a name="assertphaselessthan-operation"></a><span data-ttu-id="3b9fe-102">AssertPhaseLessThan, operacja</span><span class="sxs-lookup"><span data-stu-id="3b9fe-102">AssertPhaseLessThan operation</span></span>

<span data-ttu-id="3b9fe-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="3b9fe-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="3b9fe-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3b9fe-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3b9fe-105">Potwierdza, że `number` zakodowany w PhaseLittleEndian jest mniejszy niż `value` .</span><span class="sxs-lookup"><span data-stu-id="3b9fe-105">Asserts that the `number` encoded in PhaseLittleEndian is less than `value`.</span></span>

```qsharp
operation AssertPhaseLessThan (value : Int, number : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="3b9fe-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="3b9fe-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="3b9fe-107">wartość: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3b9fe-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3b9fe-108">`number` musi być mniejszy niż ten.</span><span class="sxs-lookup"><span data-stu-id="3b9fe-108">`number` must be less than this.</span></span>


### <a name="number--phaselittleendian"></a><span data-ttu-id="3b9fe-109">Liczba: [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="3b9fe-109">number : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="3b9fe-110">Liczba całkowita bez znaku, która jest porównywana z `value` .</span><span class="sxs-lookup"><span data-stu-id="3b9fe-110">Unsigned integer which is compared to `value`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3b9fe-111">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3b9fe-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="3b9fe-112">Uwagi</span><span class="sxs-lookup"><span data-stu-id="3b9fe-112">Remarks</span></span>

<span data-ttu-id="3b9fe-113">Kontrolowana wersja tej operacji ignoruje kontrolki.</span><span class="sxs-lookup"><span data-stu-id="3b9fe-113">The controlled version of this operation ignores controls.</span></span>