---
uid: Microsoft.Quantum.Arrays.Merged
title: Funkcja scalona
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Merged
qsharp.summary: Given two sorted arrays, returns a single array containing the elements of both in sorted order. Used internally by merge sort.
ms.openlocfilehash: 262e7450188370212a7e2a57bf15e9f8ab162814
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845605"
---
# <a name="merged-function"></a><span data-ttu-id="9cd86-102">Funkcja scalona</span><span class="sxs-lookup"><span data-stu-id="9cd86-102">Merged function</span></span>

<span data-ttu-id="9cd86-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="9cd86-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="9cd86-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9cd86-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9cd86-105">W przypadku dwóch posortowanych tablic funkcja zwraca pojedynczą tablicę zawierającą elementy obu elementów w sortowanej kolejności.</span><span class="sxs-lookup"><span data-stu-id="9cd86-105">Given two sorted arrays, returns a single array containing the elements of both in sorted order.</span></span> <span data-ttu-id="9cd86-106">Używane wewnętrznie przez scalanie sortowania.</span><span class="sxs-lookup"><span data-stu-id="9cd86-106">Used internally by merge sort.</span></span>

```qsharp
function Merged<'T> (comparison : (('T, 'T) -> Bool), left : 'T[], right : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="9cd86-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="9cd86-107">Input</span></span>

### <a name="comparison--tt---bool"></a><span data-ttu-id="9cd86-108">Porównanie: (t, t)-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="9cd86-108">comparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>




### <a name="left--t"></a><span data-ttu-id="9cd86-109">Left: t []</span><span class="sxs-lookup"><span data-stu-id="9cd86-109">left : 'T[]</span></span>




### <a name="right--t"></a><span data-ttu-id="9cd86-110">Right: t []</span><span class="sxs-lookup"><span data-stu-id="9cd86-110">right : 'T[]</span></span>





## <a name="output--t"></a><span data-ttu-id="9cd86-111">Wynik: t []</span><span class="sxs-lookup"><span data-stu-id="9cd86-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="9cd86-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="9cd86-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9cd86-113">'C</span><span class="sxs-lookup"><span data-stu-id="9cd86-113">'T</span></span>

