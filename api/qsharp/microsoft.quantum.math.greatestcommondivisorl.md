---
uid: Microsoft.Quantum.Math.GreatestCommonDivisorL
title: GreatestCommonDivisorL, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: GreatestCommonDivisorL
qsharp.summary: Computes the greatest common divisor of $a$ and $b$. The GCD is always positive.
ms.openlocfilehash: 1bd18758bb2dea8a4801cbfdf258d91f81c5d9a4
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96195514"
---
# <a name="greatestcommondivisorl-function"></a><span data-ttu-id="ca610-102">GreatestCommonDivisorL, funkcja</span><span class="sxs-lookup"><span data-stu-id="ca610-102">GreatestCommonDivisorL function</span></span>

<span data-ttu-id="ca610-103">Przestrzeń nazw: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="ca610-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="ca610-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ca610-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ca610-105">Oblicza największy wspólny dzielnik $a $ i $b $.</span><span class="sxs-lookup"><span data-stu-id="ca610-105">Computes the greatest common divisor of $a$ and $b$.</span></span> <span data-ttu-id="ca610-106">GCD jest zawsze dodatni.</span><span class="sxs-lookup"><span data-stu-id="ca610-106">The GCD is always positive.</span></span>

```qsharp
function GreatestCommonDivisorL (a : BigInt, b : BigInt) : BigInt
```


## <a name="input"></a><span data-ttu-id="ca610-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="ca610-107">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="ca610-108">Odp.: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="ca610-108">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="ca610-109">Pierwsza liczba, dla których jest obliczany największy wspólny dzielnik.</span><span class="sxs-lookup"><span data-stu-id="ca610-109">the first number of which extended greatest common divisor is being computed</span></span>


### <a name="b--bigint"></a><span data-ttu-id="ca610-110">b: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="ca610-110">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="ca610-111">Druga liczba, dla której obliczany jest rozszerzony największy wspólny dzielnik</span><span class="sxs-lookup"><span data-stu-id="ca610-111">the second number of which extended greatest common divisor is being computed</span></span>



## <a name="output--bigint"></a><span data-ttu-id="ca610-112">Dane wyjściowe: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="ca610-112">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="ca610-113">Największy wspólny dzielnik $a $ i $b $</span><span class="sxs-lookup"><span data-stu-id="ca610-113">Greatest common divisor of $a$ and $b$</span></span>