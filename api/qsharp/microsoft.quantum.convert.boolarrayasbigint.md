---
uid: Microsoft.Quantum.Convert.BoolArrayAsBigInt
title: BoolArrayAsBigInt, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolArrayAsBigInt
qsharp.summary: Converts a given array of Booleans to an equivalent big integer. The 0 element of the array is the least significant bit of the big integer.
ms.openlocfilehash: 5a85fd9f81cec0f2de7e7807622aab9604a4db7c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214317"
---
# <a name="boolarrayasbigint-function"></a><span data-ttu-id="09783-102">BoolArrayAsBigInt, funkcja</span><span class="sxs-lookup"><span data-stu-id="09783-102">BoolArrayAsBigInt function</span></span>

<span data-ttu-id="09783-103">Przestrzeń nazw: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="09783-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="09783-104">Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="09783-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="09783-105">Konwertuje daną tablicę wartości logicznych na równoważną dużą liczbę całkowitą.</span><span class="sxs-lookup"><span data-stu-id="09783-105">Converts a given array of Booleans to an equivalent big integer.</span></span>
<span data-ttu-id="09783-106">Element 0 tablicy jest najmniej znaczącym bitem dużej liczby całkowitej.</span><span class="sxs-lookup"><span data-stu-id="09783-106">The 0 element of the array is the least significant bit of the big integer.</span></span>

```qsharp
function BoolArrayAsBigInt (a : Bool[]) : BigInt
```


## <a name="input"></a><span data-ttu-id="09783-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="09783-107">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="09783-108">Odp.: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="09783-108">a : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>





## <a name="output--bigint"></a><span data-ttu-id="09783-109">Dane wyjściowe: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="09783-109">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>



## <a name="remarks"></a><span data-ttu-id="09783-110">Uwagi</span><span class="sxs-lookup"><span data-stu-id="09783-110">Remarks</span></span>

<span data-ttu-id="09783-111">Aby uzyskać więcej informacji, zobacz [Konstruktor BigInteger języka C#](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.-ctor?view=netframework-4.7.2#System_Numerics_BigInteger__ctor_System_Int64_) .</span><span class="sxs-lookup"><span data-stu-id="09783-111">See [C# BigInteger constructor](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.-ctor?view=netframework-4.7.2#System_Numerics_BigInteger__ctor_System_Int64_) for more details.</span></span>