---
uid: Microsoft.Quantum.Arithmetic.Sum
title: Suma operacji
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: Sum
qsharp.summary: Implements a reversible sum gate. Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2`.
ms.openlocfilehash: 7758e29c9f08f4d05253defbe5a43a5316289522
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221797"
---
# <a name="sum-operation"></a><span data-ttu-id="dd710-102">Suma operacji</span><span class="sxs-lookup"><span data-stu-id="dd710-102">Sum operation</span></span>

<span data-ttu-id="dd710-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="dd710-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="dd710-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="dd710-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="dd710-105">Implementuje bramę sum odwracalnych.</span><span class="sxs-lookup"><span data-stu-id="dd710-105">Implements a reversible sum gate.</span></span> <span data-ttu-id="dd710-106">Nadawana jest zakodowana w qubit `carryIn` i dwie summand bity zakodowane w `summand1` i `summand2` , które oblicza bitowe XOR `carryIn` `summand1` i `summand2` w qubit `summand2` .</span><span class="sxs-lookup"><span data-stu-id="dd710-106">Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2`.</span></span>

```qsharp
operation Sum (carryIn : Qubit, summand1 : Qubit, summand2 : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="dd710-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="dd710-107">Input</span></span>

### <a name="carryin--qubit"></a><span data-ttu-id="dd710-108">przeprowadzenie: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="dd710-108">carryIn : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="dd710-109">Qubit.</span><span class="sxs-lookup"><span data-stu-id="dd710-109">Carry-in qubit.</span></span>


### <a name="summand1--qubit"></a><span data-ttu-id="dd710-110">summand1: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="dd710-110">summand1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="dd710-111">Pierwszy summand qubit.</span><span class="sxs-lookup"><span data-stu-id="dd710-111">First summand qubit.</span></span>


### <a name="summand2--qubit"></a><span data-ttu-id="dd710-112">summand2: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="dd710-112">summand2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="dd710-113">Druga summand qubit jest zastępowana dolną bitową sumą `summand1` i `summand2` .</span><span class="sxs-lookup"><span data-stu-id="dd710-113">Second summand qubit, is replaced with the lower bit of the sum of `summand1` and `summand2`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="dd710-114">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="dd710-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="dd710-115">Uwagi</span><span class="sxs-lookup"><span data-stu-id="dd710-115">Remarks</span></span>

<span data-ttu-id="dd710-116">W przeciwieństwie do `Carry` operacji to nie oblicza bitu przeprowadzenia.</span><span class="sxs-lookup"><span data-stu-id="dd710-116">In contrast to the `Carry` operation, this does not compute the carry-out bit.</span></span>