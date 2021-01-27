---
uid: Microsoft.Quantum.Math.ExpModI
title: ExpModI, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExpModI
qsharp.summary: Returns an integer raised to a given power, with respect to a given modulus.
ms.openlocfilehash: dd4fc7d98275f6a02e3b13163b92f0812c92a82f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857032"
---
# <a name="expmodi-function"></a><span data-ttu-id="da506-102">ExpModI, funkcja</span><span class="sxs-lookup"><span data-stu-id="da506-102">ExpModI function</span></span>

<span data-ttu-id="da506-103">Przestrzeń nazw: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="da506-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="da506-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="da506-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="da506-105">Zwraca liczbę całkowitą podniesioną do danej potęgi w odniesieniu do danego modułu.</span><span class="sxs-lookup"><span data-stu-id="da506-105">Returns an integer raised to a given power, with respect to a given modulus.</span></span>

```qsharp
function ExpModI (expBase : Int, power : Int, modulus : Int) : Int
```


## <a name="description"></a><span data-ttu-id="da506-106">Opis</span><span class="sxs-lookup"><span data-stu-id="da506-106">Description</span></span>

<span data-ttu-id="da506-107">Zezwól nam na expBase przez $x $, moc przez $p $ i modulo przez $N $.</span><span class="sxs-lookup"><span data-stu-id="da506-107">Let us denote expBase by $x$, power by $p$ and modulus by $N$.</span></span>
<span data-ttu-id="da506-108">Funkcja zwraca $x ^ p \operatorname{mod} N $.</span><span class="sxs-lookup"><span data-stu-id="da506-108">The function returns $x^p \operatorname{mod} N$.</span></span>

<span data-ttu-id="da506-109">Przyjęto założenie, że $N $, $x $ są pozytywne i potęga nie jest ujemna.</span><span class="sxs-lookup"><span data-stu-id="da506-109">We assume that $N$, $x$ are positive and power is non-negative.</span></span>

## <a name="input"></a><span data-ttu-id="da506-110">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="da506-110">Input</span></span>

### <a name="expbase--int"></a><span data-ttu-id="da506-111">expBase: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="da506-111">expBase : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="power--int"></a><span data-ttu-id="da506-112">potęga: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="da506-112">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="modulus--int"></a><span data-ttu-id="da506-113">Moduł: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="da506-113">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--int"></a><span data-ttu-id="da506-114">Wynik: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="da506-114">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>



## <a name="remarks"></a><span data-ttu-id="da506-115">Uwagi</span><span class="sxs-lookup"><span data-stu-id="da506-115">Remarks</span></span>

<span data-ttu-id="da506-116">Czas jest proporcjonalny do liczby bitów w `power` , a nie do `power` samego siebie.</span><span class="sxs-lookup"><span data-stu-id="da506-116">Takes time proportional to the number of bits in `power`, not the `power` itself.</span></span>