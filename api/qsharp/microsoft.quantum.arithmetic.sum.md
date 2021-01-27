---
uid: Microsoft.Quantum.Arithmetic.Sum
title: Suma operacji
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: Sum
qsharp.summary: Implements a reversible sum gate. Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2`.
ms.openlocfilehash: e659c77a876e10df75f28ca1798fb0335e1bfb22
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847752"
---
# <a name="sum-operation"></a><span data-ttu-id="cfec1-102">Suma operacji</span><span class="sxs-lookup"><span data-stu-id="cfec1-102">Sum operation</span></span>

<span data-ttu-id="cfec1-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="cfec1-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="cfec1-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cfec1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="cfec1-105">Implementuje bramę sum odwracalnych.</span><span class="sxs-lookup"><span data-stu-id="cfec1-105">Implements a reversible sum gate.</span></span> <span data-ttu-id="cfec1-106">Nadawana jest zakodowana w qubit `carryIn` i dwie summand bity zakodowane w `summand1` i `summand2` , które oblicza bitowe XOR `carryIn` `summand1` i `summand2` w qubit `summand2` .</span><span class="sxs-lookup"><span data-stu-id="cfec1-106">Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2`.</span></span>

```qsharp
operation Sum (carryIn : Qubit, summand1 : Qubit, summand2 : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="cfec1-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="cfec1-107">Input</span></span>

### <a name="carryin--qubit"></a><span data-ttu-id="cfec1-108">przeprowadzenie: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="cfec1-108">carryIn : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="cfec1-109">Qubit.</span><span class="sxs-lookup"><span data-stu-id="cfec1-109">Carry-in qubit.</span></span>


### <a name="summand1--qubit"></a><span data-ttu-id="cfec1-110">summand1: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="cfec1-110">summand1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="cfec1-111">Pierwszy summand qubit.</span><span class="sxs-lookup"><span data-stu-id="cfec1-111">First summand qubit.</span></span>


### <a name="summand2--qubit"></a><span data-ttu-id="cfec1-112">summand2: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="cfec1-112">summand2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="cfec1-113">Druga summand qubit jest zastępowana dolną bitową sumą `summand1` i `summand2` .</span><span class="sxs-lookup"><span data-stu-id="cfec1-113">Second summand qubit, is replaced with the lower bit of the sum of `summand1` and `summand2`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="cfec1-114">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cfec1-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="cfec1-115">Uwagi</span><span class="sxs-lookup"><span data-stu-id="cfec1-115">Remarks</span></span>

<span data-ttu-id="cfec1-116">W przeciwieństwie do `Carry` operacji to nie oblicza bitu przeprowadzenia.</span><span class="sxs-lookup"><span data-stu-id="cfec1-116">In contrast to the `Carry` operation, this does not compute the carry-out bit.</span></span>