---
uid: Microsoft.Quantum.Arithmetic.AssertMostSignificantBit
title: AssertMostSignificantBit, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertMostSignificantBit
qsharp.summary: Asserts that the most significant qubit of a qubit register representing an unsigned integer is in a particular state.
ms.openlocfilehash: 41381455d1a96970647f887e038f7dff3a4eb204
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223786"
---
# <a name="assertmostsignificantbit-operation"></a><span data-ttu-id="7c421-102">AssertMostSignificantBit, operacja</span><span class="sxs-lookup"><span data-stu-id="7c421-102">AssertMostSignificantBit operation</span></span>

<span data-ttu-id="7c421-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="7c421-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="7c421-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7c421-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7c421-105">Potwierdza, że najbardziej znaczący qubit rejestru qubit reprezentujący liczbę całkowitą bez znaku jest w określonym stanie.</span><span class="sxs-lookup"><span data-stu-id="7c421-105">Asserts that the most significant qubit of a qubit register representing an unsigned integer is in a particular state.</span></span>

```qsharp
operation AssertMostSignificantBit (value : Result, number : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="7c421-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="7c421-106">Input</span></span>

### <a name="value--__invalidresult__"></a><span data-ttu-id="7c421-107">wartość: __nieprawidłowa <Result>__</span><span class="sxs-lookup"><span data-stu-id="7c421-107">value : __invalid<Result>__</span></span>

<span data-ttu-id="7c421-108">Wartość najwyższego potwierdzeń bitów.</span><span class="sxs-lookup"><span data-stu-id="7c421-108">The value of the highest bit being asserted.</span></span>


### <a name="number--littleendian"></a><span data-ttu-id="7c421-109">Liczba: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="7c421-109">number : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="7c421-110">Liczba całkowita bez znaku, która jest sprawdzana z największą liczbą bitów.</span><span class="sxs-lookup"><span data-stu-id="7c421-110">Unsigned integer of which the highest bit is checked.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7c421-111">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7c421-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="7c421-112">Uwagi</span><span class="sxs-lookup"><span data-stu-id="7c421-112">Remarks</span></span>

<span data-ttu-id="7c421-113">Kontrolowana wersja tej operacji ignoruje kontrolki.</span><span class="sxs-lookup"><span data-stu-id="7c421-113">The controlled version of this operation ignores controls.</span></span>

## <a name="see-also"></a><span data-ttu-id="7c421-114">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="7c421-114">See Also</span></span>

- [<span data-ttu-id="7c421-115">Microsoft. Quantum. wewnętrzna. Assert</span><span class="sxs-lookup"><span data-stu-id="7c421-115">Microsoft.Quantum.Intrinsic.Assert</span></span>](xref:Microsoft.Quantum.Intrinsic.Assert)