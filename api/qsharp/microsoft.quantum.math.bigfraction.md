---
uid: Microsoft.Quantum.Math.BigFraction
title: BigFraction typ zdefiniowany przez użytkownika
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BigFraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: 1c9b9e350c4fa3664b2c66da05149005b1170ec3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211087"
---
# <a name="bigfraction-user-defined-type"></a><span data-ttu-id="15ff6-102">BigFraction typ zdefiniowany przez użytkownika</span><span class="sxs-lookup"><span data-stu-id="15ff6-102">BigFraction user defined type</span></span>

<span data-ttu-id="15ff6-103">Przestrzeń nazw: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="15ff6-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="15ff6-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="15ff6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="15ff6-105">Reprezentuje liczbę racjonalną formularza `p/q` .</span><span class="sxs-lookup"><span data-stu-id="15ff6-105">Represents a rational number of the form `p/q`.</span></span> <span data-ttu-id="15ff6-106">Liczba całkowita `p` jest pierwszym elementem krotki i `q` jest drugim elementem krotki.</span><span class="sxs-lookup"><span data-stu-id="15ff6-106">Integer `p` is the first element of the tuple and `q` is the second element of the tuple.</span></span>

```qsharp

newtype BigFraction = (Numerator : BigInt, Denominator : BigInt);
```



## <a name="named-items"></a><span data-ttu-id="15ff6-107">Nazwane elementy</span><span class="sxs-lookup"><span data-stu-id="15ff6-107">Named Items</span></span>

### <a name="numerator--bigint"></a><span data-ttu-id="15ff6-108">Licznik: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="15ff6-108">Numerator : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="15ff6-109">Licznik części ułamkowej.</span><span class="sxs-lookup"><span data-stu-id="15ff6-109">Numerator of the fraction.</span></span>
### <a name="denominator--bigint"></a><span data-ttu-id="15ff6-110">Mianownik: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="15ff6-110">Denominator : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="15ff6-111">Mianownik ułamka/</span><span class="sxs-lookup"><span data-stu-id="15ff6-111">Denominator of the fraction/</span></span>