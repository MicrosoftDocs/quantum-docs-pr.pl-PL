---
uid: Microsoft.Quantum.Math.BigFraction
title: BigFraction typ zdefiniowany przez użytkownika
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BigFraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: a8daa54947097b95040a2dfa7a4d1b90bfaff856
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723211"
---
# <a name="bigfraction-user-defined-type"></a><span data-ttu-id="cdefd-102">BigFraction typ zdefiniowany przez użytkownika</span><span class="sxs-lookup"><span data-stu-id="cdefd-102">BigFraction user defined type</span></span>

<span data-ttu-id="cdefd-103">Przestrzeń nazw: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="cdefd-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="cdefd-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="cdefd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="cdefd-105">Reprezentuje liczbę racjonalną formularza `p/q` .</span><span class="sxs-lookup"><span data-stu-id="cdefd-105">Represents a rational number of the form `p/q`.</span></span> <span data-ttu-id="cdefd-106">Liczba całkowita `p` jest pierwszym elementem krotki i `q` jest drugim elementem krotki.</span><span class="sxs-lookup"><span data-stu-id="cdefd-106">Integer `p` is the first element of the tuple and `q` is the second element of the tuple.</span></span>

```qsharp

newtype BigFraction = (Numerator : BigInt, Denominator : BigInt);
```



## <a name="named-items"></a><span data-ttu-id="cdefd-107">Nazwane elementy</span><span class="sxs-lookup"><span data-stu-id="cdefd-107">Named Items</span></span>

### <a name="numerator--bigint"></a><span data-ttu-id="cdefd-108">Licznik: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="cdefd-108">Numerator : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="cdefd-109">Licznik części ułamkowej.</span><span class="sxs-lookup"><span data-stu-id="cdefd-109">Numerator of the fraction.</span></span>
### <a name="denominator--bigint"></a><span data-ttu-id="cdefd-110">Mianownik: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="cdefd-110">Denominator : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="cdefd-111">Mianownik ułamka/</span><span class="sxs-lookup"><span data-stu-id="cdefd-111">Denominator of the fraction/</span></span>