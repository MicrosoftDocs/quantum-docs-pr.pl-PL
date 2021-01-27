---
uid: Microsoft.Quantum.Arithmetic.SquareFxP
title: SquareFxP, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: SquareFxP
qsharp.summary: Squares a fixed-point number.
ms.openlocfilehash: ba0364d7c649c2a949fc52f89409a5280f71a82f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842920"
---
# <a name="squarefxp-operation"></a><span data-ttu-id="9135a-102">SquareFxP, operacja</span><span class="sxs-lookup"><span data-stu-id="9135a-102">SquareFxP operation</span></span>

<span data-ttu-id="9135a-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="9135a-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="9135a-104">Pakiet: [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="9135a-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="9135a-105">Kwadraty o stałej liczbie punktów.</span><span class="sxs-lookup"><span data-stu-id="9135a-105">Squares a fixed-point number.</span></span>

```qsharp
operation SquareFxP (fp : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="9135a-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="9135a-106">Input</span></span>

### <a name="fp--fixedpoint"></a><span data-ttu-id="9135a-107">FP: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="9135a-107">fp : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="9135a-108">Liczba stałych punktów.</span><span class="sxs-lookup"><span data-stu-id="9135a-108">Fixed-point number.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="9135a-109">wynik: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="9135a-109">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="9135a-110">Liczba stałych punktów wyników musi być w stanie $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="9135a-110">Result fixed-point number, must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9135a-111">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9135a-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

