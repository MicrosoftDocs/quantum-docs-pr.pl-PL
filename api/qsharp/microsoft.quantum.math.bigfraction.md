---
uid: Microsoft.Quantum.Math.BigFraction
title: BigFraction typ zdefiniowany przez użytkownika
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BigFraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: bfbf49e7a3d060417e506a1977c20adc08b81f0e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846897"
---
# <a name="bigfraction-user-defined-type"></a><span data-ttu-id="c5c7c-102">BigFraction typ zdefiniowany przez użytkownika</span><span class="sxs-lookup"><span data-stu-id="c5c7c-102">BigFraction user defined type</span></span>

<span data-ttu-id="c5c7c-103">Przestrzeń nazw: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="c5c7c-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="c5c7c-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c5c7c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c5c7c-105">Reprezentuje liczbę racjonalną formularza `p/q` .</span><span class="sxs-lookup"><span data-stu-id="c5c7c-105">Represents a rational number of the form `p/q`.</span></span> <span data-ttu-id="c5c7c-106">Liczba całkowita `p` jest pierwszym elementem krotki i `q` jest drugim elementem krotki.</span><span class="sxs-lookup"><span data-stu-id="c5c7c-106">Integer `p` is the first element of the tuple and `q` is the second element of the tuple.</span></span>

```qsharp

newtype BigFraction = (Numerator : BigInt, Denominator : BigInt);
```



## <a name="named-items"></a><span data-ttu-id="c5c7c-107">Nazwane elementy</span><span class="sxs-lookup"><span data-stu-id="c5c7c-107">Named Items</span></span>

### <a name="numerator--bigint"></a><span data-ttu-id="c5c7c-108">Licznik: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="c5c7c-108">Numerator : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="c5c7c-109">Licznik części ułamkowej.</span><span class="sxs-lookup"><span data-stu-id="c5c7c-109">Numerator of the fraction.</span></span>
### <a name="denominator--bigint"></a><span data-ttu-id="c5c7c-110">Mianownik: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="c5c7c-110">Denominator : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="c5c7c-111">Mianownik ułamka/</span><span class="sxs-lookup"><span data-stu-id="c5c7c-111">Denominator of the fraction/</span></span>