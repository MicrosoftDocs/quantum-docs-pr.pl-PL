---
uid: Microsoft.Quantum.Math.ExpModL
title: ExpModL, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExpModL
qsharp.summary: Returns an integer raised to a given power, with respect to a given modulus.
ms.openlocfilehash: 07da113caeb9f6f3f3f3f92f13478f33021bfa14
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210753"
---
# <a name="expmodl-function"></a><span data-ttu-id="68bf0-102">ExpModL, funkcja</span><span class="sxs-lookup"><span data-stu-id="68bf0-102">ExpModL function</span></span>

<span data-ttu-id="68bf0-103">Przestrzeń nazw: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="68bf0-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="68bf0-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="68bf0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="68bf0-105">Zwraca liczbę całkowitą podniesioną do danej potęgi w odniesieniu do danego modułu.</span><span class="sxs-lookup"><span data-stu-id="68bf0-105">Returns an integer raised to a given power, with respect to a given modulus.</span></span>

```qsharp
function ExpModL (expBase : BigInt, power : BigInt, modulus : BigInt) : BigInt
```


## <a name="description"></a><span data-ttu-id="68bf0-106">Opis</span><span class="sxs-lookup"><span data-stu-id="68bf0-106">Description</span></span>

<span data-ttu-id="68bf0-107">Zezwól nam na expBase przez $x $, moc przez $p $ i modulo przez $N $.</span><span class="sxs-lookup"><span data-stu-id="68bf0-107">Let us denote expBase by $x$, power by $p$ and modulus by $N$.</span></span>
<span data-ttu-id="68bf0-108">Funkcja zwraca $x ^ p \operatorname{mod} N $.</span><span class="sxs-lookup"><span data-stu-id="68bf0-108">The function returns $x^p \operatorname{mod} N$.</span></span>

<span data-ttu-id="68bf0-109">Przyjęto założenie, że $N $, $x $ są pozytywne i potęga nie jest ujemna.</span><span class="sxs-lookup"><span data-stu-id="68bf0-109">We assume that $N$, $x$ are positive and power is non-negative.</span></span>

## <a name="input"></a><span data-ttu-id="68bf0-110">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="68bf0-110">Input</span></span>

### <a name="expbase--bigint"></a><span data-ttu-id="68bf0-111">expBase: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="68bf0-111">expBase : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>




### <a name="power--bigint"></a><span data-ttu-id="68bf0-112">potęga: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="68bf0-112">power : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>




### <a name="modulus--bigint"></a><span data-ttu-id="68bf0-113">Moduł: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="68bf0-113">modulus : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>





## <a name="output--bigint"></a><span data-ttu-id="68bf0-114">Dane wyjściowe: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="68bf0-114">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>



## <a name="remarks"></a><span data-ttu-id="68bf0-115">Uwagi</span><span class="sxs-lookup"><span data-stu-id="68bf0-115">Remarks</span></span>

<span data-ttu-id="68bf0-116">Czas jest proporcjonalny do liczby bitów w `power` , a nie do `power` samego siebie.</span><span class="sxs-lookup"><span data-stu-id="68bf0-116">Takes time proportional to the number of bits in `power`, not the `power` itself.</span></span>