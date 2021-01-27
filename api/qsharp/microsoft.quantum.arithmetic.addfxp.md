---
uid: Microsoft.Quantum.Arithmetic.AddFxP
title: AddFxP, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AddFxP
qsharp.summary: Adds two fixed-point numbers stored in quantum registers.
ms.openlocfilehash: 60b7cad3d0bd8800e67830ca921f8e2d705b8f39
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843870"
---
# <a name="addfxp-operation"></a><span data-ttu-id="29975-102">AddFxP, operacja</span><span class="sxs-lookup"><span data-stu-id="29975-102">AddFxP operation</span></span>

<span data-ttu-id="29975-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="29975-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="29975-104">Pakiet: [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="29975-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="29975-105">Dodaje dwie stałe numery przechowywane w rejestrach Quantum.</span><span class="sxs-lookup"><span data-stu-id="29975-105">Adds two fixed-point numbers stored in quantum registers.</span></span>

```qsharp
operation AddFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="29975-106">Opis</span><span class="sxs-lookup"><span data-stu-id="29975-106">Description</span></span>

<span data-ttu-id="29975-107">W przypadku dwóch rejestrów ustalonych odpowiednio w Stanach $ \ket{f_1} $ i $ \ket{f_2} $ program wykona operację $ \ket{f_1} \ket{f_2} \mapsto \ket{f_1} \ket{f_1 f_2} $.</span><span class="sxs-lookup"><span data-stu-id="29975-107">Given two fixed-point registers respectively in states $\ket{f_1}$ and $\ket{f_2}$, performs the operation $\ket{f_1} \ket{f_2} \mapsto \ket{f_1} \ket{f_1 + f_2}$.</span></span>

## <a name="input"></a><span data-ttu-id="29975-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="29975-108">Input</span></span>

### <a name="fp1--fixedpoint"></a><span data-ttu-id="29975-109">FP1: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="29975-109">fp1 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="29975-110">Numer pierwszej stałej punktu</span><span class="sxs-lookup"><span data-stu-id="29975-110">First fixed-point number</span></span>


### <a name="fp2--fixedpoint"></a><span data-ttu-id="29975-111">FP2: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="29975-111">fp2 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="29975-112">Druga liczba stałych punktów, zostanie zaktualizowana tak, aby zawierała sumę dwóch danych wejściowych.</span><span class="sxs-lookup"><span data-stu-id="29975-112">Second fixed-point number, will be updated to contain the sum of the two inputs.</span></span>



## <a name="output--unit"></a><span data-ttu-id="29975-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="29975-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="29975-114">Uwagi</span><span class="sxs-lookup"><span data-stu-id="29975-114">Remarks</span></span>

<span data-ttu-id="29975-115">Bieżąca implementacja wymaga, aby dwie stałe punkty miały tę samą pozycję punktu zliczania z najmniej znaczącego bitu, tj., $n _i $ i $p _i $ muszą być równe.</span><span class="sxs-lookup"><span data-stu-id="29975-115">The current implementation requires the two fixed-point numbers to have the same point position counting from the least-significant bit, i.e., $n_i$ and $p_i$ must be equal.</span></span>