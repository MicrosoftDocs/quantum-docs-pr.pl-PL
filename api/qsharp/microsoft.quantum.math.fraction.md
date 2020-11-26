---
uid: Microsoft.Quantum.Math.Fraction
title: Ułamek typu zdefiniowanego przez użytkownika
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: Fraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: 1838bb2b605b109742948ec0633b08ca01baea98
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210679"
---
# <a name="fraction-user-defined-type"></a><span data-ttu-id="83d88-102">Ułamek typu zdefiniowanego przez użytkownika</span><span class="sxs-lookup"><span data-stu-id="83d88-102">Fraction user defined type</span></span>

<span data-ttu-id="83d88-103">Przestrzeń nazw: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="83d88-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="83d88-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="83d88-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="83d88-105">Reprezentuje liczbę racjonalną formularza `p/q` .</span><span class="sxs-lookup"><span data-stu-id="83d88-105">Represents a rational number of the form `p/q`.</span></span> <span data-ttu-id="83d88-106">Liczba całkowita `p` jest pierwszym elementem krotki i `q` jest drugim elementem krotki.</span><span class="sxs-lookup"><span data-stu-id="83d88-106">Integer `p` is the first element of the tuple and `q` is the second element of the tuple.</span></span>

```qsharp

newtype Fraction = (Numerator : Int, Denominator : Int);
```



## <a name="named-items"></a><span data-ttu-id="83d88-107">Nazwane elementy</span><span class="sxs-lookup"><span data-stu-id="83d88-107">Named Items</span></span>

### <a name="numerator--int"></a><span data-ttu-id="83d88-108">Licznik: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="83d88-108">Numerator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="83d88-109">Licznik części ułamkowej.</span><span class="sxs-lookup"><span data-stu-id="83d88-109">Numerator of the fraction.</span></span>
### <a name="denominator--int"></a><span data-ttu-id="83d88-110">Mianownik: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="83d88-110">Denominator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="83d88-111">Mianownik ułamka/</span><span class="sxs-lookup"><span data-stu-id="83d88-111">Denominator of the fraction/</span></span>