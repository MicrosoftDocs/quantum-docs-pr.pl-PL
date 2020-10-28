---
uid: Microsoft.Quantum.Arithmetic.AssertMostSignificantBit
title: AssertMostSignificantBit, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertMostSignificantBit
qsharp.summary: Asserts that the most significant qubit of a qubit register representing an unsigned integer is in a particular state.
ms.openlocfilehash: 408e50ed9f2e6c8ba35db20855608d2bd1f24eea
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721380"
---
# <a name="assertmostsignificantbit-operation"></a><span data-ttu-id="ecc22-102">AssertMostSignificantBit, operacja</span><span class="sxs-lookup"><span data-stu-id="ecc22-102">AssertMostSignificantBit operation</span></span>

<span data-ttu-id="ecc22-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="ecc22-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="ecc22-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ecc22-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ecc22-105">Potwierdza, że najbardziej znaczący qubit rejestru qubit reprezentujący liczbę całkowitą bez znaku jest w określonym stanie.</span><span class="sxs-lookup"><span data-stu-id="ecc22-105">Asserts that the most significant qubit of a qubit register representing an unsigned integer is in a particular state.</span></span>

```qsharp
operation AssertMostSignificantBit (value : Result, number : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="ecc22-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="ecc22-106">Input</span></span>

### <a name="value--__invalidresult__"></a><span data-ttu-id="ecc22-107">wartość: __nieprawidłowa <Result>__</span><span class="sxs-lookup"><span data-stu-id="ecc22-107">value : __invalid<Result>__</span></span>

<span data-ttu-id="ecc22-108">Wartość najwyższego potwierdzeń bitów.</span><span class="sxs-lookup"><span data-stu-id="ecc22-108">The value of the highest bit being asserted.</span></span>


### <a name="number--littleendian"></a><span data-ttu-id="ecc22-109">Liczba: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="ecc22-109">number : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="ecc22-110">Liczba całkowita bez znaku, która jest sprawdzana z największą liczbą bitów.</span><span class="sxs-lookup"><span data-stu-id="ecc22-110">Unsigned integer of which the highest bit is checked.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ecc22-111">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ecc22-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="ecc22-112">Uwagi</span><span class="sxs-lookup"><span data-stu-id="ecc22-112">Remarks</span></span>

<span data-ttu-id="ecc22-113">Kontrolowana wersja tej operacji ignoruje kontrolki.</span><span class="sxs-lookup"><span data-stu-id="ecc22-113">The controlled version of this operation ignores controls.</span></span>

## <a name="see-also"></a><span data-ttu-id="ecc22-114">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="ecc22-114">See Also</span></span>

- [<span data-ttu-id="ecc22-115">Microsoft. Quantum. wewnętrzna. Assert</span><span class="sxs-lookup"><span data-stu-id="ecc22-115">Microsoft.Quantum.Intrinsic.Assert</span></span>](xref:Microsoft.Quantum.Intrinsic.Assert)