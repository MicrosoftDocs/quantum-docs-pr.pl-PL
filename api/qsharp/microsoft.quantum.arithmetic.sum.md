---
uid: Microsoft.Quantum.Arithmetic.Sum
title: Suma operacji
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: Sum
qsharp.summary: Implements a reversible sum gate. Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2`.
ms.openlocfilehash: b31d8ab39676ee6723e5fc053eba9e0af3ac2b2f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719505"
---
# <a name="sum-operation"></a><span data-ttu-id="45f8b-102">Suma operacji</span><span class="sxs-lookup"><span data-stu-id="45f8b-102">Sum operation</span></span>

<span data-ttu-id="45f8b-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="45f8b-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="45f8b-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="45f8b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="45f8b-105">Implementuje bramę sum odwracalnych.</span><span class="sxs-lookup"><span data-stu-id="45f8b-105">Implements a reversible sum gate.</span></span> <span data-ttu-id="45f8b-106">Nadawana jest zakodowana w qubit `carryIn` i dwie summand bity zakodowane w `summand1` i `summand2` , które oblicza bitowe XOR `carryIn` `summand1` i `summand2` w qubit `summand2` .</span><span class="sxs-lookup"><span data-stu-id="45f8b-106">Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2`.</span></span>

```qsharp
operation Sum (carryIn : Qubit, summand1 : Qubit, summand2 : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="45f8b-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="45f8b-107">Input</span></span>

### <a name="carryin--qubit"></a><span data-ttu-id="45f8b-108">przeprowadzenie: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="45f8b-108">carryIn : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="45f8b-109">Qubit.</span><span class="sxs-lookup"><span data-stu-id="45f8b-109">Carry-in qubit.</span></span>


### <a name="summand1--qubit"></a><span data-ttu-id="45f8b-110">summand1: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="45f8b-110">summand1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="45f8b-111">Pierwszy summand qubit.</span><span class="sxs-lookup"><span data-stu-id="45f8b-111">First summand qubit.</span></span>


### <a name="summand2--qubit"></a><span data-ttu-id="45f8b-112">summand2: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="45f8b-112">summand2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="45f8b-113">Druga summand qubit jest zastępowana dolną bitową sumą `summand1` i `summand2` .</span><span class="sxs-lookup"><span data-stu-id="45f8b-113">Second summand qubit, is replaced with the lower bit of the sum of `summand1` and `summand2`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="45f8b-114">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="45f8b-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="45f8b-115">Uwagi</span><span class="sxs-lookup"><span data-stu-id="45f8b-115">Remarks</span></span>

<span data-ttu-id="45f8b-116">W przeciwieństwie do `Carry` operacji to nie oblicza bitu przeprowadzenia.</span><span class="sxs-lookup"><span data-stu-id="45f8b-116">In contrast to the `Carry` operation, this does not compute the carry-out bit.</span></span>