---
uid: Microsoft.Quantum.Arithmetic.Carry
title: Przenieś operację
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: Carry
qsharp.summary: Implements a reversible carry gate. Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2` and the carry-out is xored to the qubit `carryOut`.
ms.openlocfilehash: dfb08a9a9c805c0b611ab993c9b1eb949810a7da
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843354"
---
# <a name="carry-operation"></a><span data-ttu-id="69c4f-102">Przenieś operację</span><span class="sxs-lookup"><span data-stu-id="69c4f-102">Carry operation</span></span>

<span data-ttu-id="69c4f-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="69c4f-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="69c4f-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="69c4f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="69c4f-105">Implementuje bramę przenoszące odwracalnie.</span><span class="sxs-lookup"><span data-stu-id="69c4f-105">Implements a reversible carry gate.</span></span> <span data-ttu-id="69c4f-106">Nadano bit przenoszenia zakodowany w qubit `carryIn` i dwie summand bity zakodowane w `summand1` i `summand2` , oblicza bitową XOR `carryIn` , `summand1` a `summand2` w qubit `summand2` i przeprowadzenie jest XORed do qubit `carryOut` .</span><span class="sxs-lookup"><span data-stu-id="69c4f-106">Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2` and the carry-out is xored to the qubit `carryOut`.</span></span>

```qsharp
operation Carry (carryIn : Qubit, summand1 : Qubit, summand2 : Qubit, carryOut : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="69c4f-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="69c4f-107">Input</span></span>

### <a name="carryin--qubit"></a><span data-ttu-id="69c4f-108">przeprowadzenie: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="69c4f-108">carryIn : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="69c4f-109">Qubit.</span><span class="sxs-lookup"><span data-stu-id="69c4f-109">Carry-in qubit.</span></span>


### <a name="summand1--qubit"></a><span data-ttu-id="69c4f-110">summand1: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="69c4f-110">summand1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="69c4f-111">Pierwszy summand qubit.</span><span class="sxs-lookup"><span data-stu-id="69c4f-111">First summand qubit.</span></span>


### <a name="summand2--qubit"></a><span data-ttu-id="69c4f-112">summand2: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="69c4f-112">summand2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="69c4f-113">Druga summand qubit jest zastępowana dolną bitową sumą `summand1` i `summand2` .</span><span class="sxs-lookup"><span data-stu-id="69c4f-113">Second summand qubit, is replaced with the lower bit of the sum of `summand1` and `summand2`.</span></span>


### <a name="carryout--qubit"></a><span data-ttu-id="69c4f-114">carryOut: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="69c4f-114">carryOut : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="69c4f-115">Przeprowadzenie qubit, będzie XORed z wyższą bitową sumą.</span><span class="sxs-lookup"><span data-stu-id="69c4f-115">Carry-out qubit, will be xored with the higher bit of the sum.</span></span>



## <a name="output--unit"></a><span data-ttu-id="69c4f-116">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="69c4f-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

