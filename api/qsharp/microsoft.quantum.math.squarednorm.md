---
uid: Microsoft.Quantum.Math.SquaredNorm
title: SquaredNorm, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: SquaredNorm
qsharp.summary: Returns the squared 2-norm of a vector.
ms.openlocfilehash: 4165a761753f336cb7b94ad36b11ac324ad4e5c6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725022"
---
# <a name="squarednorm-function"></a><span data-ttu-id="e0b4c-102">SquaredNorm, funkcja</span><span class="sxs-lookup"><span data-stu-id="e0b4c-102">SquaredNorm function</span></span>

<span data-ttu-id="e0b4c-103">Przestrzeń nazw: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="e0b4c-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="e0b4c-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e0b4c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e0b4c-105">Zwraca kwadratową 2-normatywną wartość wektora.</span><span class="sxs-lookup"><span data-stu-id="e0b4c-105">Returns the squared 2-norm of a vector.</span></span>

```qsharp
function SquaredNorm (array : Double[]) : Double
```


## <a name="description"></a><span data-ttu-id="e0b4c-106">Opis</span><span class="sxs-lookup"><span data-stu-id="e0b4c-106">Description</span></span>

<span data-ttu-id="e0b4c-107">Zwraca kwadratową 2-normę wektora; oznacza to, że dane wejściowe $ \vec{x} $ zwracają wartość $ \ sum_i x_i ^ 2 $.</span><span class="sxs-lookup"><span data-stu-id="e0b4c-107">Returns the squared 2-norm of a vector; that is, given an input $\vec{x}$, returns $\sum_i x_i^2$.</span></span>

## <a name="input"></a><span data-ttu-id="e0b4c-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="e0b4c-108">Input</span></span>

### <a name="array--double"></a><span data-ttu-id="e0b4c-109">Array: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="e0b4c-109">array : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="e0b4c-110">Wektor, którego wartość jest równa 2, która ma zostać zwrócona.</span><span class="sxs-lookup"><span data-stu-id="e0b4c-110">The vector whose squared 2-norm is to be returned.</span></span>



## <a name="output--double"></a><span data-ttu-id="e0b4c-111">Dane wyjściowe: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e0b4c-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e0b4c-112">Kwadratowa 2-norma `array` .</span><span class="sxs-lookup"><span data-stu-id="e0b4c-112">The squared 2-norm of `array`.</span></span>