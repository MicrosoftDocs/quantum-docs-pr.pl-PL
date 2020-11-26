---
uid: Microsoft.Quantum.Math.PowL
title: PowL, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PowL
qsharp.summary: Returns a number raised to a given power.
ms.openlocfilehash: b3207d1854f6b69cdb5b68d354000a0b6746c0c2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228325"
---
# <a name="powl-function"></a><span data-ttu-id="9b8e0-102">PowL, funkcja</span><span class="sxs-lookup"><span data-stu-id="9b8e0-102">PowL function</span></span>

<span data-ttu-id="9b8e0-103">Przestrzeń nazw: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="9b8e0-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="9b8e0-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9b8e0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9b8e0-105">Zwraca liczbę podniesioną do danej potęgi.</span><span class="sxs-lookup"><span data-stu-id="9b8e0-105">Returns a number raised to a given power.</span></span>

```qsharp
function PowL (a : BigInt, power : Int) : BigInt
```


## <a name="input"></a><span data-ttu-id="9b8e0-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="9b8e0-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="9b8e0-107">Odp.: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="9b8e0-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="9b8e0-108">Numer $a $, który ma zostać wywołany.</span><span class="sxs-lookup"><span data-stu-id="9b8e0-108">The number $a$ that is to be raised.</span></span>


### <a name="power--int"></a><span data-ttu-id="9b8e0-109">potęga: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9b8e0-109">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9b8e0-110">$B potęgi $, do której ma zostać zgłoszony $a $.</span><span class="sxs-lookup"><span data-stu-id="9b8e0-110">The power $b$ to which $a$ should be raised.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="9b8e0-111">Dane wyjściowe: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="9b8e0-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="9b8e0-112">$a potęgi ^ b $</span><span class="sxs-lookup"><span data-stu-id="9b8e0-112">The power $a^b$</span></span>