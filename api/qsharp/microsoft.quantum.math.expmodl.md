---
uid: Microsoft.Quantum.Math.ExpModL
title: ExpModL, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExpModL
qsharp.summary: Returns an integer raised to a given power, with respect to a given modulus.
ms.openlocfilehash: 73d434bd364847b4e5e06d1a9f460424e0c50850
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723729"
---
# <a name="expmodl-function"></a><span data-ttu-id="6f6b4-102">ExpModL, funkcja</span><span class="sxs-lookup"><span data-stu-id="6f6b4-102">ExpModL function</span></span>

<span data-ttu-id="6f6b4-103">Przestrzeń nazw: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="6f6b4-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="6f6b4-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6f6b4-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6f6b4-105">Zwraca liczbę całkowitą podniesioną do danej potęgi w odniesieniu do danego modułu.</span><span class="sxs-lookup"><span data-stu-id="6f6b4-105">Returns an integer raised to a given power, with respect to a given modulus.</span></span>

```qsharp
function ExpModL (expBase : BigInt, power : BigInt, modulus : BigInt) : BigInt
```


## <a name="description"></a><span data-ttu-id="6f6b4-106">Opis</span><span class="sxs-lookup"><span data-stu-id="6f6b4-106">Description</span></span>

<span data-ttu-id="6f6b4-107">Zezwól nam na expBase przez $x $, moc przez $p $ i modulo przez $N $.</span><span class="sxs-lookup"><span data-stu-id="6f6b4-107">Let us denote expBase by $x$, power by $p$ and modulus by $N$.</span></span>
<span data-ttu-id="6f6b4-108">Funkcja zwraca $x ^ p \operatorname{mod} N $.</span><span class="sxs-lookup"><span data-stu-id="6f6b4-108">The function returns $x^p \operatorname{mod} N$.</span></span>

<span data-ttu-id="6f6b4-109">Przyjęto założenie, że $N $, $x $ są pozytywne i potęga nie jest ujemna.</span><span class="sxs-lookup"><span data-stu-id="6f6b4-109">We assume that $N$, $x$ are positive and power is non-negative.</span></span>

## <a name="input"></a><span data-ttu-id="6f6b4-110">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="6f6b4-110">Input</span></span>

### <a name="expbase--bigint"></a><span data-ttu-id="6f6b4-111">expBase: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="6f6b4-111">expBase : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>




### <a name="power--bigint"></a><span data-ttu-id="6f6b4-112">potęga: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="6f6b4-112">power : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>




### <a name="modulus--bigint"></a><span data-ttu-id="6f6b4-113">Moduł: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="6f6b4-113">modulus : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>





## <a name="output--bigint"></a><span data-ttu-id="6f6b4-114">Dane wyjściowe: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="6f6b4-114">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>



## <a name="remarks"></a><span data-ttu-id="6f6b4-115">Uwagi</span><span class="sxs-lookup"><span data-stu-id="6f6b4-115">Remarks</span></span>

<span data-ttu-id="6f6b4-116">Czas jest proporcjonalny do liczby bitów w `power` , a nie do `power` samego siebie.</span><span class="sxs-lookup"><span data-stu-id="6f6b4-116">Takes time proportional to the number of bits in `power`, not the `power` itself.</span></span>