---
uid: Microsoft.Quantum.Arithmetic.AssertPhaseLessThan
title: AssertPhaseLessThan, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertPhaseLessThan
qsharp.summary: Asserts that the `number` encoded in PhaseLittleEndian is less than `value`.
ms.openlocfilehash: 8a943ff937593801bd308ab4224c7051ff8a10cb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223752"
---
# <a name="assertphaselessthan-operation"></a><span data-ttu-id="8f39a-102">AssertPhaseLessThan, operacja</span><span class="sxs-lookup"><span data-stu-id="8f39a-102">AssertPhaseLessThan operation</span></span>

<span data-ttu-id="8f39a-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="8f39a-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="8f39a-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8f39a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8f39a-105">Potwierdza, że `number` zakodowany w PhaseLittleEndian jest mniejszy niż `value` .</span><span class="sxs-lookup"><span data-stu-id="8f39a-105">Asserts that the `number` encoded in PhaseLittleEndian is less than `value`.</span></span>

```qsharp
operation AssertPhaseLessThan (value : Int, number : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="8f39a-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="8f39a-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="8f39a-107">wartość: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8f39a-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="8f39a-108">`number` musi być mniejszy niż ten.</span><span class="sxs-lookup"><span data-stu-id="8f39a-108">`number` must be less than this.</span></span>


### <a name="number--phaselittleendian"></a><span data-ttu-id="8f39a-109">Liczba: [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="8f39a-109">number : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="8f39a-110">Liczba całkowita bez znaku, która jest porównywana z `value` .</span><span class="sxs-lookup"><span data-stu-id="8f39a-110">Unsigned integer which is compared to `value`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8f39a-111">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8f39a-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="8f39a-112">Uwagi</span><span class="sxs-lookup"><span data-stu-id="8f39a-112">Remarks</span></span>

<span data-ttu-id="8f39a-113">Kontrolowana wersja tej operacji ignoruje kontrolki.</span><span class="sxs-lookup"><span data-stu-id="8f39a-113">The controlled version of this operation ignores controls.</span></span>