---
uid: Microsoft.Quantum.Arithmetic.IncrementByInteger
title: IncrementByInteger, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementByInteger
qsharp.summary: Increments an unsigned quantum register by a classical integer, using phase rotations.
ms.openlocfilehash: 363d48d697e3b2dad4d4896e6b1e701864649d9b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721113"
---
# <a name="incrementbyinteger-operation"></a><span data-ttu-id="24e43-102">IncrementByInteger, operacja</span><span class="sxs-lookup"><span data-stu-id="24e43-102">IncrementByInteger operation</span></span>

<span data-ttu-id="24e43-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="24e43-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="24e43-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="24e43-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="24e43-105">Zwiększa niepodpisany rejestr Quantum przez klasyczną liczbę całkowitą, używając rotacji faz.</span><span class="sxs-lookup"><span data-stu-id="24e43-105">Increments an unsigned quantum register by a classical integer, using phase rotations.</span></span>

```qsharp
operation IncrementByInteger (increment : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="24e43-106">Opis</span><span class="sxs-lookup"><span data-stu-id="24e43-106">Description</span></span>

<span data-ttu-id="24e43-107">Załóżmy, że `target` koduje liczbę całkowitą bez znaku $x $ w kodowaniu little-endian i która `increment` jest równa $a $.</span><span class="sxs-lookup"><span data-stu-id="24e43-107">Suppose that `target` encodes an unsigned integer $x$ in a little-endian encoding and that `increment` is equal to $a$.</span></span>
<span data-ttu-id="24e43-108">Następnie ta operacja implementuje moduł $ \ket{x} \mapsto \ket{x + a} $, w którym jest wykonywane dzielenie modulo $2 ^ n $, gdzie $n = \texttt{Length (target!)} $.</span><span class="sxs-lookup"><span data-stu-id="24e43-108">Then, this operation implements the unitary $\ket{x} \mapsto \ket{x + a}$, where the addition is performed modulo $2^n$, where $n = \texttt{Length(target!)}$.</span></span>

## <a name="input"></a><span data-ttu-id="24e43-109">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="24e43-109">Input</span></span>

### <a name="increment--int"></a><span data-ttu-id="24e43-110">Zwiększ: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="24e43-110">increment : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="24e43-111">Liczba całkowita, przez którą `target` jest zwiększana wartość.</span><span class="sxs-lookup"><span data-stu-id="24e43-111">The integer by which the `target` is incremented by.</span></span>


### <a name="target--littleendian"></a><span data-ttu-id="24e43-112">obiekt docelowy: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="24e43-112">target : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="24e43-113">Rejestr Quantum zakodowania liczbę całkowitą bez znaku przy użyciu kodowania little-endian.</span><span class="sxs-lookup"><span data-stu-id="24e43-113">A quantum register encoding an unsigned integer using little-endian encoding.</span></span>



## <a name="output--unit"></a><span data-ttu-id="24e43-114">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="24e43-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

