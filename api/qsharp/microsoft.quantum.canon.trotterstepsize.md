---
uid: Microsoft.Quantum.Canon.TrotterStepSize
title: TrotterStepSize, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TrotterStepSize
qsharp.summary: Computes Trotter step size in recursive implementation of Trotter simulation algorithm.
ms.openlocfilehash: aa5b63e058e1ea726b0d4c6eca73078831daaf3b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204695"
---
# <a name="trotterstepsize-function"></a><span data-ttu-id="b5413-102">TrotterStepSize, funkcja</span><span class="sxs-lookup"><span data-stu-id="b5413-102">TrotterStepSize function</span></span>

<span data-ttu-id="b5413-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b5413-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b5413-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b5413-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b5413-105">Oblicza rozmiar kroku Trotter w cyklicznej implementacji algorytmu symulacji Trotter.</span><span class="sxs-lookup"><span data-stu-id="b5413-105">Computes Trotter step size in recursive implementation of Trotter simulation algorithm.</span></span>

```qsharp
function TrotterStepSize (order : Int) : Double
```


## <a name="input"></a><span data-ttu-id="b5413-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="b5413-106">Input</span></span>

### <a name="order--int"></a><span data-ttu-id="b5413-107">kolejność: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b5413-107">order : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--double"></a><span data-ttu-id="b5413-108">Dane wyjściowe: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b5413-108">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="remarks"></a><span data-ttu-id="b5413-109">Uwagi</span><span class="sxs-lookup"><span data-stu-id="b5413-109">Remarks</span></span>

<span data-ttu-id="b5413-110">Ta operacja używa innej konwencji indeksowania niż wartość [Quant-pH/0508139](https://arxiv.org/abs/quant-ph/0508139).</span><span class="sxs-lookup"><span data-stu-id="b5413-110">This operation uses a different indexing convention than that of [quant-ph/0508139](https://arxiv.org/abs/quant-ph/0508139).</span></span> <span data-ttu-id="b5413-111">W szczególności `DecomposedIntoTimeStepsCA(_, 4)` odpowiada skalarnemu $p _2 (\lambda) $ w Quant-pH/0508139.</span><span class="sxs-lookup"><span data-stu-id="b5413-111">In particular, `DecomposedIntoTimeStepsCA(_, 4)` corresponds to the scalar $p_2(\lambda)$ in quant-ph/0508139.</span></span>