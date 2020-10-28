---
uid: Microsoft.Quantum.Arrays.IsEmpty
title: IsEmpty — funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IsEmpty
qsharp.summary: Returns true if and only if an array is empty.
ms.openlocfilehash: f658c2a25b6991d9a826706a7e95b68169901f0e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719112"
---
# <a name="isempty-function"></a><span data-ttu-id="45091-102">IsEmpty — funkcja</span><span class="sxs-lookup"><span data-stu-id="45091-102">IsEmpty function</span></span>

<span data-ttu-id="45091-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="45091-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="45091-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="45091-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="45091-105">Zwraca wartość true, jeśli i tylko wtedy, gdy tablica jest pusta.</span><span class="sxs-lookup"><span data-stu-id="45091-105">Returns true if and only if an array is empty.</span></span>

```qsharp
function IsEmpty<'T> (array : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="45091-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="45091-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="45091-107">Tablica: t []</span><span class="sxs-lookup"><span data-stu-id="45091-107">array : 'T[]</span></span>

<span data-ttu-id="45091-108">Tablica, która ma zostać sprawdzona.</span><span class="sxs-lookup"><span data-stu-id="45091-108">The array to be checked.</span></span>



## <a name="output--bool"></a><span data-ttu-id="45091-109">Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="45091-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="45091-110">`true` Jeśli i tylko wtedy, gdy tablica jest pusta (ma długość 0).</span><span class="sxs-lookup"><span data-stu-id="45091-110">`true` if and only if the array is empty (has length 0).</span></span>

## <a name="type-parameters"></a><span data-ttu-id="45091-111">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="45091-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="45091-112">'C</span><span class="sxs-lookup"><span data-stu-id="45091-112">'T</span></span>

