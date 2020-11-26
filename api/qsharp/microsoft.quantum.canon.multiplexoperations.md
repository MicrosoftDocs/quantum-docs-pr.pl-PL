---
uid: Microsoft.Quantum.Canon.MultiplexOperations
title: MultiplexOperations, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexOperations
qsharp.summary: >-
  Applies an array of operations controlled by an array of number states.

  That is, applies Multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by $n$-qubit number state $\ket{j}$.

  $U = \sum^{2^n-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.
ms.openlocfilehash: ad66b39fcfacbe5231ec3b9ba96989d6d5d449c1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206106"
---
# <a name="multiplexoperations-operation"></a><span data-ttu-id="a2577-102">MultiplexOperations, operacja</span><span class="sxs-lookup"><span data-stu-id="a2577-102">MultiplexOperations operation</span></span>

<span data-ttu-id="a2577-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a2577-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a2577-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a2577-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a2577-105">Stosuje tablicę operacji sterowaną przez tablicę liczb Stanów.</span><span class="sxs-lookup"><span data-stu-id="a2577-105">Applies an array of operations controlled by an array of number states.</span></span>

<span data-ttu-id="a2577-106">Oznacza to, że jest stosowana operacja jednostkowa o pomnożenia $U $, która stosuje $V jednostkowe _j $, gdy jest to kontrolowane przez $n $-qubit Number State $ \ket{j} $.</span><span class="sxs-lookup"><span data-stu-id="a2577-106">That is, applies Multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by $n$-qubit number state $\ket{j}$.</span></span>

<span data-ttu-id="a2577-107">$U = \sum ^ {2 ^ n-1} _ {j = 0} \ket{j}\bra{j}\otimes V_j $.</span><span class="sxs-lookup"><span data-stu-id="a2577-107">$U = \sum^{2^n-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.</span></span>

```qsharp
operation MultiplexOperations<'T> (unitaries : ('T => Unit is Adj + Ctl)[], index : Microsoft.Quantum.Arithmetic.LittleEndian, target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="a2577-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="a2577-108">Input</span></span>

### <a name="unitaries--t--unit--is-adj--ctl"></a><span data-ttu-id="a2577-109">unitaries: t = [jednostka](xref:microsoft.quantum.lang-ref.unit) > to przymiotnik + CTL []</span><span class="sxs-lookup"><span data-stu-id="a2577-109">unitaries : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl[]</span></span>

<span data-ttu-id="a2577-110">Tablica operacji jednostkowych do $2 ^ n $.</span><span class="sxs-lookup"><span data-stu-id="a2577-110">Array of up to $2^n$ unitary operations.</span></span> <span data-ttu-id="a2577-111">Operacja $j $ th jest indeksowana przez stan liczbowy $ \ket{j} $ zakodowany w formacie little-endian.</span><span class="sxs-lookup"><span data-stu-id="a2577-111">The $j$th operation is indexed by the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="index--littleendian"></a><span data-ttu-id="a2577-112">indeks: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="a2577-112">index : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="a2577-113">$n $-qubit kontroli rejestru, który koduje liczbę Stany $ \ket{j} $ w formacie little-endian.</span><span class="sxs-lookup"><span data-stu-id="a2577-113">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>


### <a name="target--t"></a><span data-ttu-id="a2577-114">element docelowy: 'T</span><span class="sxs-lookup"><span data-stu-id="a2577-114">target : 'T</span></span>

<span data-ttu-id="a2577-115">Ogólny rejestr qubit, który $V _j $ działa.</span><span class="sxs-lookup"><span data-stu-id="a2577-115">Generic qubit register that $V_j$ acts on.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a2577-116">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a2577-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="a2577-117">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="a2577-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a2577-118">'C</span><span class="sxs-lookup"><span data-stu-id="a2577-118">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="a2577-119">Uwagi</span><span class="sxs-lookup"><span data-stu-id="a2577-119">Remarks</span></span>

<span data-ttu-id="a2577-120">`coefficients` zostaną uzupełnione elementami tożsamości, jeśli określono mniej niż $2 ^ n $.</span><span class="sxs-lookup"><span data-stu-id="a2577-120">`coefficients` will be padded with identity elements if fewer than $2^n$ are specified.</span></span> <span data-ttu-id="a2577-121">Ta implementacja używa qubits pomocniczego $n-$1.</span><span class="sxs-lookup"><span data-stu-id="a2577-121">This implementation uses $n - 1$ auxiliary qubits.</span></span>

## <a name="references"></a><span data-ttu-id="a2577-122">Odwołania</span><span class="sxs-lookup"><span data-stu-id="a2577-122">References</span></span>

- <span data-ttu-id="a2577-123">W kierunku pierwszej symulacji Quantum przy użyciu Quantum przyspieszenie Andrew M. Childs, Dmitri Maslov, Yunseong, Neila J. Ross, Juan Su https://arxiv.org/abs/1711.10980</span><span class="sxs-lookup"><span data-stu-id="a2577-123">Toward the first quantum simulation with quantum speedup Andrew M. Childs, Dmitri Maslov, Yunseong Nam, Neil J. Ross, Yuan Su https://arxiv.org/abs/1711.10980</span></span>