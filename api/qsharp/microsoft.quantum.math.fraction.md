---
uid: Microsoft.Quantum.Math.Fraction
title: Ułamek typu zdefiniowanego przez użytkownika
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: Fraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: 350d470c374fc8e0a3f4c4a9a68ad8566ab88727
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723659"
---
# <a name="fraction-user-defined-type"></a><span data-ttu-id="869d8-102">Ułamek typu zdefiniowanego przez użytkownika</span><span class="sxs-lookup"><span data-stu-id="869d8-102">Fraction user defined type</span></span>

<span data-ttu-id="869d8-103">Przestrzeń nazw: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="869d8-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="869d8-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="869d8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="869d8-105">Reprezentuje liczbę racjonalną formularza `p/q` .</span><span class="sxs-lookup"><span data-stu-id="869d8-105">Represents a rational number of the form `p/q`.</span></span> <span data-ttu-id="869d8-106">Liczba całkowita `p` jest pierwszym elementem krotki i `q` jest drugim elementem krotki.</span><span class="sxs-lookup"><span data-stu-id="869d8-106">Integer `p` is the first element of the tuple and `q` is the second element of the tuple.</span></span>

```qsharp

newtype Fraction = (Numerator : Int, Denominator : Int);
```



## <a name="named-items"></a><span data-ttu-id="869d8-107">Nazwane elementy</span><span class="sxs-lookup"><span data-stu-id="869d8-107">Named Items</span></span>

### <a name="numerator--int"></a><span data-ttu-id="869d8-108">Licznik: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="869d8-108">Numerator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="869d8-109">Licznik części ułamkowej.</span><span class="sxs-lookup"><span data-stu-id="869d8-109">Numerator of the fraction.</span></span>
### <a name="denominator--int"></a><span data-ttu-id="869d8-110">Mianownik: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="869d8-110">Denominator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="869d8-111">Mianownik ułamka/</span><span class="sxs-lookup"><span data-stu-id="869d8-111">Denominator of the fraction/</span></span>