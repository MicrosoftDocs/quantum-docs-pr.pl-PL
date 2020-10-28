---
uid: Microsoft.Quantum.Math.GreatestCommonDivisorL
title: GreatestCommonDivisorL, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: GreatestCommonDivisorL
qsharp.summary: Computes the greatest common divisor of $a$ and $b$. The GCD is always positive.
ms.openlocfilehash: 77bdb040908e9a8af81dee09451a3582f7b7d159
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723645"
---
# <a name="greatestcommondivisorl-function"></a><span data-ttu-id="22434-102">GreatestCommonDivisorL, funkcja</span><span class="sxs-lookup"><span data-stu-id="22434-102">GreatestCommonDivisorL function</span></span>

<span data-ttu-id="22434-103">Przestrzeń nazw: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="22434-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="22434-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="22434-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="22434-105">Oblicza największy wspólny dzielnik $a $ i $b $.</span><span class="sxs-lookup"><span data-stu-id="22434-105">Computes the greatest common divisor of $a$ and $b$.</span></span> <span data-ttu-id="22434-106">GCD jest zawsze dodatni.</span><span class="sxs-lookup"><span data-stu-id="22434-106">The GCD is always positive.</span></span>

```qsharp
function GreatestCommonDivisorL (a : BigInt, b : BigInt) : BigInt
```


## <a name="input"></a><span data-ttu-id="22434-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="22434-107">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="22434-108">Odp.: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="22434-108">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="22434-109">Pierwsza liczba, dla których jest obliczany największy wspólny dzielnik.</span><span class="sxs-lookup"><span data-stu-id="22434-109">the first number of which extended greatest common divisor is being computed</span></span>


### <a name="b--bigint"></a><span data-ttu-id="22434-110">b: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="22434-110">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="22434-111">Druga liczba, dla której obliczany jest rozszerzony największy wspólny dzielnik</span><span class="sxs-lookup"><span data-stu-id="22434-111">the second number of which extended greatest common divisor is being computed</span></span>



## <a name="output--bigint"></a><span data-ttu-id="22434-112">Dane wyjściowe: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="22434-112">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="22434-113">Największy wspólny dzielnik $a $ i $b $</span><span class="sxs-lookup"><span data-stu-id="22434-113">Greatest common divisor of $a$ and $b$</span></span>