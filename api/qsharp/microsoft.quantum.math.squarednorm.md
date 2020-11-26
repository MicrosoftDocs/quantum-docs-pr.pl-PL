---
uid: Microsoft.Quantum.Math.SquaredNorm
title: SquaredNorm, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: SquaredNorm
qsharp.summary: Returns the squared 2-norm of a vector.
ms.openlocfilehash: ecbc66a8851f23187e0c0ea53ce121442323733b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96227305"
---
# <a name="squarednorm-function"></a><span data-ttu-id="11218-102">SquaredNorm, funkcja</span><span class="sxs-lookup"><span data-stu-id="11218-102">SquaredNorm function</span></span>

<span data-ttu-id="11218-103">Przestrzeń nazw: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="11218-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="11218-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="11218-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="11218-105">Zwraca kwadratową 2-normatywną wartość wektora.</span><span class="sxs-lookup"><span data-stu-id="11218-105">Returns the squared 2-norm of a vector.</span></span>

```qsharp
function SquaredNorm (array : Double[]) : Double
```


## <a name="description"></a><span data-ttu-id="11218-106">Opis</span><span class="sxs-lookup"><span data-stu-id="11218-106">Description</span></span>

<span data-ttu-id="11218-107">Zwraca kwadratową 2-normę wektora; oznacza to, że dane wejściowe $ \vec{x} $ zwracają wartość $ \ sum_i x_i ^ 2 $.</span><span class="sxs-lookup"><span data-stu-id="11218-107">Returns the squared 2-norm of a vector; that is, given an input $\vec{x}$, returns $\sum_i x_i^2$.</span></span>

## <a name="input"></a><span data-ttu-id="11218-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="11218-108">Input</span></span>

### <a name="array--double"></a><span data-ttu-id="11218-109">Array: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="11218-109">array : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="11218-110">Wektor, którego wartość jest równa 2, która ma zostać zwrócona.</span><span class="sxs-lookup"><span data-stu-id="11218-110">The vector whose squared 2-norm is to be returned.</span></span>



## <a name="output--double"></a><span data-ttu-id="11218-111">Dane wyjściowe: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="11218-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="11218-112">Kwadratowa 2-norma `array` .</span><span class="sxs-lookup"><span data-stu-id="11218-112">The squared 2-norm of `array`.</span></span>