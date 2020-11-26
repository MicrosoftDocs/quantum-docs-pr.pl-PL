---
uid: Microsoft.Quantum.Arithmetic.IdenticalPointPosFactFxP
title: IdenticalPointPosFactFxP, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IdenticalPointPosFactFxP
qsharp.summary: Assert that all fixed-point numbers in the provided array have identical point positions when counting from the least- significant bit. I.e., number of bits minus point position must be constant for all fixed-point numbers in the array.
ms.openlocfilehash: 907e270e1c3710fb346044ad7757171c6d5f568d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223055"
---
# <a name="identicalpointposfactfxp-function"></a><span data-ttu-id="572d8-102">IdenticalPointPosFactFxP, funkcja</span><span class="sxs-lookup"><span data-stu-id="572d8-102">IdenticalPointPosFactFxP function</span></span>

<span data-ttu-id="572d8-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="572d8-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="572d8-104">Pakiet: [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="572d8-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="572d8-105">Potwierdź, że wszystkie liczby stałych punktów w podanej tablicy mają identyczne położenia punktów podczas zliczania z najmniej znaczącego bitu.</span><span class="sxs-lookup"><span data-stu-id="572d8-105">Assert that all fixed-point numbers in the provided array have identical point positions when counting from the least- significant bit.</span></span> <span data-ttu-id="572d8-106">Oznacza to, że liczba pozycji punktu minusa bity musi być stała dla wszystkich liczb stałych punktów w tablicy.</span><span class="sxs-lookup"><span data-stu-id="572d8-106">I.e., number of bits minus point position must be constant for all fixed-point numbers in the array.</span></span>

```qsharp
function IdenticalPointPosFactFxP (fixedPoints : Microsoft.Quantum.Arithmetic.FixedPoint[]) : Unit
```


## <a name="input"></a><span data-ttu-id="572d8-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="572d8-107">Input</span></span>

### <a name="fixedpoints--fixedpoint"></a><span data-ttu-id="572d8-108">fixedPoints: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)[]</span><span class="sxs-lookup"><span data-stu-id="572d8-108">fixedPoints : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)[]</span></span>

<span data-ttu-id="572d8-109">Tablica liczb stałych zmiennoprzecinkowych, które będą sprawdzane pod kątem zgodności (przy użyciu potwierdzeń).</span><span class="sxs-lookup"><span data-stu-id="572d8-109">Array of quantum fixed-point numbers that will be checked for compatibility (using assertions).</span></span>



## <a name="output--unit"></a><span data-ttu-id="572d8-110">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="572d8-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

