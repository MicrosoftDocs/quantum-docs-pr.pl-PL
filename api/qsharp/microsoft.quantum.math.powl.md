---
uid: Microsoft.Quantum.Math.PowL
title: PowL, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PowL
qsharp.summary: Returns a number raised to a given power.
ms.openlocfilehash: 22c05cf85acf691490049ce9ac27a7c6b2a4899e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724751"
---
# <a name="powl-function"></a><span data-ttu-id="31311-102">PowL, funkcja</span><span class="sxs-lookup"><span data-stu-id="31311-102">PowL function</span></span>

<span data-ttu-id="31311-103">Przestrzeń nazw: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="31311-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="31311-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="31311-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="31311-105">Zwraca liczbę podniesioną do danej potęgi.</span><span class="sxs-lookup"><span data-stu-id="31311-105">Returns a number raised to a given power.</span></span>

```qsharp
function PowL (a : BigInt, power : Int) : BigInt
```


## <a name="input"></a><span data-ttu-id="31311-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="31311-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="31311-107">Odp.: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="31311-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="31311-108">Numer $a $, który ma zostać wywołany.</span><span class="sxs-lookup"><span data-stu-id="31311-108">The number $a$ that is to be raised.</span></span>


### <a name="power--int"></a><span data-ttu-id="31311-109">potęga: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="31311-109">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="31311-110">$B potęgi $, do której ma zostać zgłoszony $a $.</span><span class="sxs-lookup"><span data-stu-id="31311-110">The power $b$ to which $a$ should be raised.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="31311-111">Dane wyjściowe: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="31311-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="31311-112">$a potęgi ^ b $</span><span class="sxs-lookup"><span data-stu-id="31311-112">The power $a^b$</span></span>