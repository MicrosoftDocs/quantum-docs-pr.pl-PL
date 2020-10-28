---
uid: Microsoft.Quantum.Arithmetic.IdenticalPointPosFactFxP
title: IdenticalPointPosFactFxP, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IdenticalPointPosFactFxP
qsharp.summary: Assert that all fixed-point numbers in the provided array have identical point positions when counting from the least- significant bit. I.e., number of bits minus point position must be constant for all fixed-point numbers in the array.
ms.openlocfilehash: 0b285ce980ca1abbc3eb20838389a6f49835e742
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721116"
---
# <a name="identicalpointposfactfxp-function"></a><span data-ttu-id="3e450-102">IdenticalPointPosFactFxP, funkcja</span><span class="sxs-lookup"><span data-stu-id="3e450-102">IdenticalPointPosFactFxP function</span></span>

<span data-ttu-id="3e450-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="3e450-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="3e450-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3e450-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3e450-105">Potwierdź, że wszystkie liczby stałych punktów w podanej tablicy mają identyczne położenia punktów podczas zliczania z najmniej znaczącego bitu.</span><span class="sxs-lookup"><span data-stu-id="3e450-105">Assert that all fixed-point numbers in the provided array have identical point positions when counting from the least- significant bit.</span></span> <span data-ttu-id="3e450-106">Oznacza to, że liczba pozycji punktu minusa bity musi być stała dla wszystkich liczb stałych punktów w tablicy.</span><span class="sxs-lookup"><span data-stu-id="3e450-106">I.e., number of bits minus point position must be constant for all fixed-point numbers in the array.</span></span>

```qsharp
function IdenticalPointPosFactFxP (fixedPoints : Microsoft.Quantum.Arithmetic.FixedPoint[]) : Unit
```


## <a name="input"></a><span data-ttu-id="3e450-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="3e450-107">Input</span></span>

### <a name="fixedpoints--fixedpoint"></a><span data-ttu-id="3e450-108">fixedPoints: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)[]</span><span class="sxs-lookup"><span data-stu-id="3e450-108">fixedPoints : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)[]</span></span>

<span data-ttu-id="3e450-109">Tablica liczb stałych zmiennoprzecinkowych, które będą sprawdzane pod kątem zgodności (przy użyciu potwierdzeń).</span><span class="sxs-lookup"><span data-stu-id="3e450-109">Array of quantum fixed-point numbers that will be checked for compatibility (using assertions).</span></span>



## <a name="output--unit"></a><span data-ttu-id="3e450-110">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3e450-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

