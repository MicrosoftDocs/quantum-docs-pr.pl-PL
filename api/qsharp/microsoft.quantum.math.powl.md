---
uid: Microsoft.Quantum.Math.PowL
title: PowL, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PowL
qsharp.summary: Returns a number raised to a given power.
ms.openlocfilehash: f7282a3639ca87dae731e39594576aa73c4602ac
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857462"
---
# <a name="powl-function"></a><span data-ttu-id="9df11-102">PowL, funkcja</span><span class="sxs-lookup"><span data-stu-id="9df11-102">PowL function</span></span>

<span data-ttu-id="9df11-103">Przestrzeń nazw: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="9df11-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="9df11-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9df11-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9df11-105">Zwraca liczbę podniesioną do danej potęgi.</span><span class="sxs-lookup"><span data-stu-id="9df11-105">Returns a number raised to a given power.</span></span>

```qsharp
function PowL (a : BigInt, power : Int) : BigInt
```


## <a name="input"></a><span data-ttu-id="9df11-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="9df11-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="9df11-107">Odp.: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="9df11-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="9df11-108">Numer $a $, który ma zostać wywołany.</span><span class="sxs-lookup"><span data-stu-id="9df11-108">The number $a$ that is to be raised.</span></span>


### <a name="power--int"></a><span data-ttu-id="9df11-109">potęga: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9df11-109">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9df11-110">$B potęgi $, do której ma zostać zgłoszony $a $.</span><span class="sxs-lookup"><span data-stu-id="9df11-110">The power $b$ to which $a$ should be raised.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="9df11-111">Dane wyjściowe: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="9df11-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="9df11-112">$a potęgi ^ b $</span><span class="sxs-lookup"><span data-stu-id="9df11-112">The power $a^b$</span></span>