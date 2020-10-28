---
uid: Microsoft.Quantum.Arrays.IndexOf
title: IndexOf, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexOf
qsharp.summary: Returns the first index of the first element in an array that satisfies a given predicate. If no such element exists, returns -1.
ms.openlocfilehash: 7ff80f13f432a18f216b2dee4bd65b1e82034fa5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719172"
---
# <a name="indexof-function"></a><span data-ttu-id="a1e6f-102">IndexOf, funkcja</span><span class="sxs-lookup"><span data-stu-id="a1e6f-102">IndexOf function</span></span>

<span data-ttu-id="a1e6f-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="a1e6f-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="a1e6f-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a1e6f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a1e6f-105">Zwraca pierwszy indeks pierwszego elementu w tablicy, który spełnia określony predykat.</span><span class="sxs-lookup"><span data-stu-id="a1e6f-105">Returns the first index of the first element in an array that satisfies a given predicate.</span></span> <span data-ttu-id="a1e6f-106">Jeśli taki element nie istnieje, zwraca wartość-1.</span><span class="sxs-lookup"><span data-stu-id="a1e6f-106">If no such element exists, returns -1.</span></span>

```qsharp
function IndexOf<'T> (predicate : ('T -> Bool), arr : 'T[]) : Int
```


## <a name="input"></a><span data-ttu-id="a1e6f-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="a1e6f-107">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="a1e6f-108">predykat: > [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="a1e6f-108">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="a1e6f-109">Funkcja predykatu działająca na elementach tablicy.</span><span class="sxs-lookup"><span data-stu-id="a1e6f-109">A predicate function acting on elements of the array.</span></span>


### <a name="arr--t"></a><span data-ttu-id="a1e6f-110">ARR: t []</span><span class="sxs-lookup"><span data-stu-id="a1e6f-110">arr : 'T[]</span></span>

<span data-ttu-id="a1e6f-111">Tablica, która ma być przeszukiwana przy użyciu danego predykatu.</span><span class="sxs-lookup"><span data-stu-id="a1e6f-111">An array to be searched using the given predicate.</span></span>



## <a name="output--int"></a><span data-ttu-id="a1e6f-112">Wynik: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a1e6f-112">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a1e6f-113">Najmniejszy indeks taki, `idx` który `predicate(arr[idx])` ma wartość true, lub-1, jeśli taki element nie istnieje.</span><span class="sxs-lookup"><span data-stu-id="a1e6f-113">Either the smallest index `idx` such that `predicate(arr[idx])` is true, or -1 if no such element exists.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="a1e6f-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="a1e6f-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a1e6f-115">'C</span><span class="sxs-lookup"><span data-stu-id="a1e6f-115">'T</span></span>

