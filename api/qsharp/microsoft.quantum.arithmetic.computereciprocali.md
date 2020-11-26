---
uid: Microsoft.Quantum.Arithmetic.ComputeReciprocalI
title: ComputeReciprocalI, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ComputeReciprocalI
qsharp.summary: Computes the reciprocal 1/x for an unsigned integer x using integer division. The result, interpreted as an integer, will be `floor(2^(2*n-1) / x)`.
ms.openlocfilehash: 9024da4a457265c65a41ef681cfbb99ebd4989a5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223361"
---
# <a name="computereciprocali-operation"></a><span data-ttu-id="4d1bc-102">ComputeReciprocalI, operacja</span><span class="sxs-lookup"><span data-stu-id="4d1bc-102">ComputeReciprocalI operation</span></span>

<span data-ttu-id="4d1bc-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="4d1bc-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="4d1bc-104">Pakiet: [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="4d1bc-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="4d1bc-105">Oblicza odwrotność 1/x dla nieoznaczonej liczby całkowitej x przy użyciu dzielenia liczb całkowitych.</span><span class="sxs-lookup"><span data-stu-id="4d1bc-105">Computes the reciprocal 1/x for an unsigned integer x using integer division.</span></span> <span data-ttu-id="4d1bc-106">Wynikiem jest interpretowana jako liczba całkowita `floor(2^(2*n-1) / x)` .</span><span class="sxs-lookup"><span data-stu-id="4d1bc-106">The result, interpreted as an integer, will be `floor(2^(2*n-1) / x)`.</span></span>

```qsharp
operation ComputeReciprocalI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="4d1bc-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="4d1bc-107">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="4d1bc-108">XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="4d1bc-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="4d1bc-109">n-bitowa liczba całkowita bez znaku</span><span class="sxs-lookup"><span data-stu-id="4d1bc-109">n-bit unsigned integer</span></span>


### <a name="result--littleendian"></a><span data-ttu-id="4d1bc-110">wynik: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="4d1bc-110">result : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="4d1bc-111">2n-bitowe dane wyjściowe muszą znajdować się w $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="4d1bc-111">2n-bit output, must be in $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4d1bc-112">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4d1bc-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="4d1bc-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="4d1bc-113">Remarks</span></span>

<span data-ttu-id="4d1bc-114">Dla danych wejściowych x = 0, dane wyjściowe będą wszystkie.</span><span class="sxs-lookup"><span data-stu-id="4d1bc-114">For the input x=0, the output will be all-ones.</span></span>