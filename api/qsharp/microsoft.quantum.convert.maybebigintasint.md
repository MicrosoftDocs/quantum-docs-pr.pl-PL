---
uid: Microsoft.Quantum.Convert.MaybeBigIntAsInt
title: MaybeBigIntAsInt, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: MaybeBigIntAsInt
qsharp.summary: Converts a given big integer to an equivalent integer, if possible. The function returns a pair of the resulting integer and a Boolean flag which is true, if and only if the conversion was possible.
ms.openlocfilehash: d0a598497e8a8f019bbd8da7db1c6cc4d7bde017
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224279"
---
# <a name="maybebigintasint-function"></a><span data-ttu-id="c5140-102">MaybeBigIntAsInt, funkcja</span><span class="sxs-lookup"><span data-stu-id="c5140-102">MaybeBigIntAsInt function</span></span>

<span data-ttu-id="c5140-103">Przestrzeń nazw: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="c5140-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="c5140-104">Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="c5140-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="c5140-105">Konwertuje daną dużą liczbę całkowitą na równoważną liczbę całkowitą, jeśli jest to możliwe.</span><span class="sxs-lookup"><span data-stu-id="c5140-105">Converts a given big integer to an equivalent integer, if possible.</span></span>
<span data-ttu-id="c5140-106">Funkcja zwraca parę wynikowej liczby całkowitej i flagi logicznej, która ma wartość true, jeśli i tylko wtedy, gdy konwersja była możliwa.</span><span class="sxs-lookup"><span data-stu-id="c5140-106">The function returns a pair of the resulting integer and a Boolean flag which is true, if and only if the conversion was possible.</span></span>

```qsharp
function MaybeBigIntAsInt (a : BigInt) : (Int, Bool)
```


## <a name="input"></a><span data-ttu-id="c5140-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="c5140-107">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="c5140-108">Odp.: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="c5140-108">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>





## <a name="output--intbool"></a><span data-ttu-id="c5140-109">Wynik: ([int](xref:microsoft.quantum.lang-ref.int),[bool](xref:microsoft.quantum.lang-ref.bool))</span><span class="sxs-lookup"><span data-stu-id="c5140-109">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Bool](xref:microsoft.quantum.lang-ref.bool))</span></span>



## <a name="remarks"></a><span data-ttu-id="c5140-110">Uwagi</span><span class="sxs-lookup"><span data-stu-id="c5140-110">Remarks</span></span>

<span data-ttu-id="c5140-111">Aby uzyskać więcej informacji, zobacz [Konstruktor BigInteger języka C#](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.-ctor?view=netframework-4.7.2#System_Numerics_BigInteger__ctor_System_Int64_) .</span><span class="sxs-lookup"><span data-stu-id="c5140-111">See [C# BigInteger constructor](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.-ctor?view=netframework-4.7.2#System_Numerics_BigInteger__ctor_System_Int64_) for more details.</span></span>