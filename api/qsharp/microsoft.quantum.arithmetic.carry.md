---
uid: Microsoft.Quantum.Arithmetic.Carry
title: Przenieś operację
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: Carry
qsharp.summary: Implements a reversible carry gate. Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2` and the carry-out is xored to the qubit `carryOut`.
ms.openlocfilehash: 53f8d2a8ba89a912e3d4c08452208a899b2b85de
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223599"
---
# <a name="carry-operation"></a><span data-ttu-id="97212-102">Przenieś operację</span><span class="sxs-lookup"><span data-stu-id="97212-102">Carry operation</span></span>

<span data-ttu-id="97212-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="97212-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="97212-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="97212-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="97212-105">Implementuje bramę przenoszące odwracalnie.</span><span class="sxs-lookup"><span data-stu-id="97212-105">Implements a reversible carry gate.</span></span> <span data-ttu-id="97212-106">Nadano bit przenoszenia zakodowany w qubit `carryIn` i dwie summand bity zakodowane w `summand1` i `summand2` , oblicza bitową XOR `carryIn` , `summand1` a `summand2` w qubit `summand2` i przeprowadzenie jest XORed do qubit `carryOut` .</span><span class="sxs-lookup"><span data-stu-id="97212-106">Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2` and the carry-out is xored to the qubit `carryOut`.</span></span>

```qsharp
operation Carry (carryIn : Qubit, summand1 : Qubit, summand2 : Qubit, carryOut : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="97212-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="97212-107">Input</span></span>

### <a name="carryin--qubit"></a><span data-ttu-id="97212-108">przeprowadzenie: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="97212-108">carryIn : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="97212-109">Qubit.</span><span class="sxs-lookup"><span data-stu-id="97212-109">Carry-in qubit.</span></span>


### <a name="summand1--qubit"></a><span data-ttu-id="97212-110">summand1: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="97212-110">summand1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="97212-111">Pierwszy summand qubit.</span><span class="sxs-lookup"><span data-stu-id="97212-111">First summand qubit.</span></span>


### <a name="summand2--qubit"></a><span data-ttu-id="97212-112">summand2: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="97212-112">summand2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="97212-113">Druga summand qubit jest zastępowana dolną bitową sumą `summand1` i `summand2` .</span><span class="sxs-lookup"><span data-stu-id="97212-113">Second summand qubit, is replaced with the lower bit of the sum of `summand1` and `summand2`.</span></span>


### <a name="carryout--qubit"></a><span data-ttu-id="97212-114">carryOut: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="97212-114">carryOut : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="97212-115">Przeprowadzenie qubit, będzie XORed z wyższą bitową sumą.</span><span class="sxs-lookup"><span data-stu-id="97212-115">Carry-out qubit, will be xored with the higher bit of the sum.</span></span>



## <a name="output--unit"></a><span data-ttu-id="97212-116">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="97212-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

