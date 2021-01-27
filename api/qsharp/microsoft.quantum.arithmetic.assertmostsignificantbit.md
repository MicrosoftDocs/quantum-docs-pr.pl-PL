---
uid: Microsoft.Quantum.Arithmetic.AssertMostSignificantBit
title: AssertMostSignificantBit, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertMostSignificantBit
qsharp.summary: Asserts that the most significant qubit of a qubit register representing an unsigned integer is in a particular state.
ms.openlocfilehash: b0b52a4ba7492d68896669aeb0b6b550d2f27f64
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843426"
---
# <a name="assertmostsignificantbit-operation"></a><span data-ttu-id="735f6-102">AssertMostSignificantBit, operacja</span><span class="sxs-lookup"><span data-stu-id="735f6-102">AssertMostSignificantBit operation</span></span>

<span data-ttu-id="735f6-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="735f6-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="735f6-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="735f6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="735f6-105">Potwierdza, że najbardziej znaczący qubit rejestru qubit reprezentujący liczbę całkowitą bez znaku jest w określonym stanie.</span><span class="sxs-lookup"><span data-stu-id="735f6-105">Asserts that the most significant qubit of a qubit register representing an unsigned integer is in a particular state.</span></span>

```qsharp
operation AssertMostSignificantBit (value : Result, number : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="735f6-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="735f6-106">Input</span></span>

### <a name="value--__invalidresult__"></a><span data-ttu-id="735f6-107">wartość: __nieprawidłowa <Result>__</span><span class="sxs-lookup"><span data-stu-id="735f6-107">value : __invalid<Result>__</span></span>

<span data-ttu-id="735f6-108">Wartość najwyższego potwierdzeń bitów.</span><span class="sxs-lookup"><span data-stu-id="735f6-108">The value of the highest bit being asserted.</span></span>


### <a name="number--littleendian"></a><span data-ttu-id="735f6-109">Liczba: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="735f6-109">number : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="735f6-110">Liczba całkowita bez znaku, która jest sprawdzana z największą liczbą bitów.</span><span class="sxs-lookup"><span data-stu-id="735f6-110">Unsigned integer of which the highest bit is checked.</span></span>



## <a name="output--unit"></a><span data-ttu-id="735f6-111">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="735f6-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="735f6-112">Uwagi</span><span class="sxs-lookup"><span data-stu-id="735f6-112">Remarks</span></span>

<span data-ttu-id="735f6-113">Kontrolowana wersja tej operacji ignoruje kontrolki.</span><span class="sxs-lookup"><span data-stu-id="735f6-113">The controlled version of this operation ignores controls.</span></span>

## <a name="see-also"></a><span data-ttu-id="735f6-114">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="735f6-114">See Also</span></span>

- [<span data-ttu-id="735f6-115">Microsoft. Quantum. wewnętrzna. Assert</span><span class="sxs-lookup"><span data-stu-id="735f6-115">Microsoft.Quantum.Intrinsic.Assert</span></span>](xref:Microsoft.Quantum.Intrinsic.Assert)