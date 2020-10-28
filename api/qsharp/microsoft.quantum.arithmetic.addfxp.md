---
uid: Microsoft.Quantum.Arithmetic.AddFxP
title: AddFxP, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AddFxP
qsharp.summary: Adds two fixed-point numbers stored in quantum registers.
ms.openlocfilehash: cf1f1379b7e1c32aefb0fccb55f4d13c95c78d8f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721701"
---
# <a name="addfxp-operation"></a><span data-ttu-id="b4347-102">AddFxP, operacja</span><span class="sxs-lookup"><span data-stu-id="b4347-102">AddFxP operation</span></span>

<span data-ttu-id="b4347-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="b4347-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="b4347-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b4347-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b4347-105">Dodaje dwie stałe numery przechowywane w rejestrach Quantum.</span><span class="sxs-lookup"><span data-stu-id="b4347-105">Adds two fixed-point numbers stored in quantum registers.</span></span>

```qsharp
operation AddFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit
```


## <a name="description"></a><span data-ttu-id="b4347-106">Opis</span><span class="sxs-lookup"><span data-stu-id="b4347-106">Description</span></span>

<span data-ttu-id="b4347-107">W przypadku dwóch rejestrów ustalonych odpowiednio w Stanach $ \ket{f_1} $ i $ \ket{f_2} $ program wykona operację $ \ket{f_1} \ket{f_2} \mapsto \ket{f_1} \ket{f_1 f_2} $.</span><span class="sxs-lookup"><span data-stu-id="b4347-107">Given two fixed-point registers respectively in states $\ket{f_1}$ and $\ket{f_2}$, performs the operation $\ket{f_1} \ket{f_2} \mapsto \ket{f_1} \ket{f_1 + f_2}$.</span></span>

## <a name="input"></a><span data-ttu-id="b4347-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="b4347-108">Input</span></span>

### <a name="fp1--fixedpoint"></a><span data-ttu-id="b4347-109">FP1: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="b4347-109">fp1 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="b4347-110">Numer pierwszej stałej punktu</span><span class="sxs-lookup"><span data-stu-id="b4347-110">First fixed-point number</span></span>


### <a name="fp2--fixedpoint"></a><span data-ttu-id="b4347-111">FP2: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="b4347-111">fp2 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="b4347-112">Druga liczba stałych punktów, zostanie zaktualizowana tak, aby zawierała sumę dwóch danych wejściowych.</span><span class="sxs-lookup"><span data-stu-id="b4347-112">Second fixed-point number, will be updated to contain the sum of the two inputs.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b4347-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b4347-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="b4347-114">Uwagi</span><span class="sxs-lookup"><span data-stu-id="b4347-114">Remarks</span></span>

<span data-ttu-id="b4347-115">Bieżąca implementacja wymaga, aby dwie stałe punkty miały tę samą pozycję punktu zliczania z najmniej znaczącego bitu, tj., $n _i $ i $p _i $ muszą być równe.</span><span class="sxs-lookup"><span data-stu-id="b4347-115">The current implementation requires the two fixed-point numbers to have the same point position counting from the least-significant bit, i.e., $n_i$ and $p_i$ must be equal.</span></span>