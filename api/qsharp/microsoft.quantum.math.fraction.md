---
uid: Microsoft.Quantum.Math.Fraction
title: Ułamek typu zdefiniowanego przez użytkownika
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: Fraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: a56d28e34938729a8e4ffda5f870e0b6a25be017
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857514"
---
# <a name="fraction-user-defined-type"></a><span data-ttu-id="f4a90-102">Ułamek typu zdefiniowanego przez użytkownika</span><span class="sxs-lookup"><span data-stu-id="f4a90-102">Fraction user defined type</span></span>

<span data-ttu-id="f4a90-103">Przestrzeń nazw: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="f4a90-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="f4a90-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f4a90-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f4a90-105">Reprezentuje liczbę racjonalną formularza `p/q` .</span><span class="sxs-lookup"><span data-stu-id="f4a90-105">Represents a rational number of the form `p/q`.</span></span> <span data-ttu-id="f4a90-106">Liczba całkowita `p` jest pierwszym elementem krotki i `q` jest drugim elementem krotki.</span><span class="sxs-lookup"><span data-stu-id="f4a90-106">Integer `p` is the first element of the tuple and `q` is the second element of the tuple.</span></span>

```qsharp

newtype Fraction = (Numerator : Int, Denominator : Int);
```



## <a name="named-items"></a><span data-ttu-id="f4a90-107">Nazwane elementy</span><span class="sxs-lookup"><span data-stu-id="f4a90-107">Named Items</span></span>

### <a name="numerator--int"></a><span data-ttu-id="f4a90-108">Licznik: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f4a90-108">Numerator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f4a90-109">Licznik części ułamkowej.</span><span class="sxs-lookup"><span data-stu-id="f4a90-109">Numerator of the fraction.</span></span>
### <a name="denominator--int"></a><span data-ttu-id="f4a90-110">Mianownik: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f4a90-110">Denominator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f4a90-111">Mianownik ułamka/</span><span class="sxs-lookup"><span data-stu-id="f4a90-111">Denominator of the fraction/</span></span>