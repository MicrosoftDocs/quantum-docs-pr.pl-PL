---
uid: Microsoft.Quantum.Arithmetic.ComputeReciprocalI
title: ComputeReciprocalI, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ComputeReciprocalI
qsharp.summary: Computes the reciprocal 1/x for an unsigned integer x using integer division. The result, interpreted as an integer, will be `floor(2^(2*n-1) / x)`.
ms.openlocfilehash: b99e816ed69af6e6d1758442d6f95c5ab0e5c07a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721224"
---
# <a name="computereciprocali-operation"></a><span data-ttu-id="ef724-102">ComputeReciprocalI, operacja</span><span class="sxs-lookup"><span data-stu-id="ef724-102">ComputeReciprocalI operation</span></span>

<span data-ttu-id="ef724-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="ef724-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="ef724-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ef724-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ef724-105">Oblicza odwrotność 1/x dla nieoznaczonej liczby całkowitej x przy użyciu dzielenia liczb całkowitych.</span><span class="sxs-lookup"><span data-stu-id="ef724-105">Computes the reciprocal 1/x for an unsigned integer x using integer division.</span></span> <span data-ttu-id="ef724-106">Wynikiem jest interpretowana jako liczba całkowita `floor(2^(2*n-1) / x)` .</span><span class="sxs-lookup"><span data-stu-id="ef724-106">The result, interpreted as an integer, will be `floor(2^(2*n-1) / x)`.</span></span>

```qsharp
operation ComputeReciprocalI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="ef724-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="ef724-107">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="ef724-108">XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="ef724-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="ef724-109">n-bitowa liczba całkowita bez znaku</span><span class="sxs-lookup"><span data-stu-id="ef724-109">n-bit unsigned integer</span></span>


### <a name="result--littleendian"></a><span data-ttu-id="ef724-110">wynik: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="ef724-110">result : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="ef724-111">2n-bitowe dane wyjściowe muszą znajdować się w $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="ef724-111">2n-bit output, must be in $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ef724-112">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ef724-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="ef724-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="ef724-113">Remarks</span></span>

<span data-ttu-id="ef724-114">Dla danych wejściowych x = 0, dane wyjściowe będą wszystkie.</span><span class="sxs-lookup"><span data-stu-id="ef724-114">For the input x=0, the output will be all-ones.</span></span>