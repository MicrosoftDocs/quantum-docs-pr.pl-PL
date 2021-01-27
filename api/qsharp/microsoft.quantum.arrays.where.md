---
uid: Microsoft.Quantum.Arrays.Where
title: WHERE — funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Where
qsharp.summary: Given a predicate and an array, returns the indices of that array where the predicate is true.
ms.openlocfilehash: 4a938114689177f7a9ee182e6e5f36debe4edac7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842221"
---
# <a name="where-function"></a><span data-ttu-id="00cdb-102">WHERE — funkcja</span><span class="sxs-lookup"><span data-stu-id="00cdb-102">Where function</span></span>

<span data-ttu-id="00cdb-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="00cdb-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="00cdb-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="00cdb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="00cdb-105">Podano predykat i tablicę, zwraca indeksy tej tablicy, w której predykat ma wartość true.</span><span class="sxs-lookup"><span data-stu-id="00cdb-105">Given a predicate and an array, returns the indices of that array where the predicate is true.</span></span>

```qsharp
function Where<'T> (predicate : ('T -> Bool), array : 'T[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="00cdb-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="00cdb-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="00cdb-107">predykat: > [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="00cdb-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="00cdb-108">Funkcja z `'T` do wartości logicznej, która jest używana do filtrowania elementów.</span><span class="sxs-lookup"><span data-stu-id="00cdb-108">A function from `'T` to Boolean that is used to filter elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="00cdb-109">Tablica: t []</span><span class="sxs-lookup"><span data-stu-id="00cdb-109">array : 'T[]</span></span>

<span data-ttu-id="00cdb-110">Tablica elementów `'T` .</span><span class="sxs-lookup"><span data-stu-id="00cdb-110">An array of elements over `'T`.</span></span>



## <a name="output--int"></a><span data-ttu-id="00cdb-111">Wynik: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="00cdb-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="00cdb-112">Tablica indeksów, gdzie `predicate` ma wartość true.</span><span class="sxs-lookup"><span data-stu-id="00cdb-112">An array of indices where `predicate` is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="00cdb-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="00cdb-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="00cdb-114">'C</span><span class="sxs-lookup"><span data-stu-id="00cdb-114">'T</span></span>

<span data-ttu-id="00cdb-115">Typ `array` elementów.</span><span class="sxs-lookup"><span data-stu-id="00cdb-115">The type of `array` elements.</span></span>