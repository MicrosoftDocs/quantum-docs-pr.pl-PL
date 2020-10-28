---
uid: Microsoft.Quantum.Math.ExpModI
title: ExpModI, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExpModI
qsharp.summary: Returns an integer raised to a given power, with respect to a given modulus.
ms.openlocfilehash: e31273702a9850d0162f160ca412ff6d50f38b28
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723365"
---
# <a name="expmodi-function"></a><span data-ttu-id="912dd-102">ExpModI, funkcja</span><span class="sxs-lookup"><span data-stu-id="912dd-102">ExpModI function</span></span>

<span data-ttu-id="912dd-103">Przestrzeń nazw: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="912dd-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="912dd-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="912dd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="912dd-105">Zwraca liczbę całkowitą podniesioną do danej potęgi w odniesieniu do danego modułu.</span><span class="sxs-lookup"><span data-stu-id="912dd-105">Returns an integer raised to a given power, with respect to a given modulus.</span></span>

```qsharp
function ExpModI (expBase : Int, power : Int, modulus : Int) : Int
```


## <a name="description"></a><span data-ttu-id="912dd-106">Opis</span><span class="sxs-lookup"><span data-stu-id="912dd-106">Description</span></span>

<span data-ttu-id="912dd-107">Zezwól nam na expBase przez $x $, moc przez $p $ i modulo przez $N $.</span><span class="sxs-lookup"><span data-stu-id="912dd-107">Let us denote expBase by $x$, power by $p$ and modulus by $N$.</span></span>
<span data-ttu-id="912dd-108">Funkcja zwraca $x ^ p \operatorname{mod} N $.</span><span class="sxs-lookup"><span data-stu-id="912dd-108">The function returns $x^p \operatorname{mod} N$.</span></span>

<span data-ttu-id="912dd-109">Przyjęto założenie, że $N $, $x $ są pozytywne i potęga nie jest ujemna.</span><span class="sxs-lookup"><span data-stu-id="912dd-109">We assume that $N$, $x$ are positive and power is non-negative.</span></span>

## <a name="input"></a><span data-ttu-id="912dd-110">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="912dd-110">Input</span></span>

### <a name="expbase--int"></a><span data-ttu-id="912dd-111">expBase: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="912dd-111">expBase : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="power--int"></a><span data-ttu-id="912dd-112">potęga: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="912dd-112">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="modulus--int"></a><span data-ttu-id="912dd-113">Moduł: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="912dd-113">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--int"></a><span data-ttu-id="912dd-114">Wynik: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="912dd-114">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>



## <a name="remarks"></a><span data-ttu-id="912dd-115">Uwagi</span><span class="sxs-lookup"><span data-stu-id="912dd-115">Remarks</span></span>

<span data-ttu-id="912dd-116">Czas jest proporcjonalny do liczby bitów w `power` , a nie do `power` samego siebie.</span><span class="sxs-lookup"><span data-stu-id="912dd-116">Takes time proportional to the number of bits in `power`, not the `power` itself.</span></span>