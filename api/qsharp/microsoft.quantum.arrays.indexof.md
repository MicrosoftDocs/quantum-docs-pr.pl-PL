---
uid: Microsoft.Quantum.Arrays.IndexOf
title: IndexOf, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexOf
qsharp.summary: Returns the first index of the first element in an array that satisfies a given predicate. If no such element exists, returns -1.
ms.openlocfilehash: 64db55e831078a7130a3ced6a30bfbd2299c392d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848523"
---
# <a name="indexof-function"></a><span data-ttu-id="fbc4a-102">IndexOf, funkcja</span><span class="sxs-lookup"><span data-stu-id="fbc4a-102">IndexOf function</span></span>

<span data-ttu-id="fbc4a-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="fbc4a-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="fbc4a-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fbc4a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fbc4a-105">Zwraca pierwszy indeks pierwszego elementu w tablicy, który spełnia określony predykat.</span><span class="sxs-lookup"><span data-stu-id="fbc4a-105">Returns the first index of the first element in an array that satisfies a given predicate.</span></span> <span data-ttu-id="fbc4a-106">Jeśli taki element nie istnieje, zwraca wartość-1.</span><span class="sxs-lookup"><span data-stu-id="fbc4a-106">If no such element exists, returns -1.</span></span>

```qsharp
function IndexOf<'T> (predicate : ('T -> Bool), arr : 'T[]) : Int
```


## <a name="input"></a><span data-ttu-id="fbc4a-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="fbc4a-107">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="fbc4a-108">predykat: > [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="fbc4a-108">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="fbc4a-109">Funkcja predykatu działająca na elementach tablicy.</span><span class="sxs-lookup"><span data-stu-id="fbc4a-109">A predicate function acting on elements of the array.</span></span>


### <a name="arr--t"></a><span data-ttu-id="fbc4a-110">ARR: t []</span><span class="sxs-lookup"><span data-stu-id="fbc4a-110">arr : 'T[]</span></span>

<span data-ttu-id="fbc4a-111">Tablica, która ma być przeszukiwana przy użyciu danego predykatu.</span><span class="sxs-lookup"><span data-stu-id="fbc4a-111">An array to be searched using the given predicate.</span></span>



## <a name="output--int"></a><span data-ttu-id="fbc4a-112">Wynik: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="fbc4a-112">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="fbc4a-113">Najmniejszy indeks taki, `idx` który `predicate(arr[idx])` ma wartość true, lub-1, jeśli taki element nie istnieje.</span><span class="sxs-lookup"><span data-stu-id="fbc4a-113">Either the smallest index `idx` such that `predicate(arr[idx])` is true, or -1 if no such element exists.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="fbc4a-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="fbc4a-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="fbc4a-115">'C</span><span class="sxs-lookup"><span data-stu-id="fbc4a-115">'T</span></span>



## <a name="example"></a><span data-ttu-id="fbc4a-116">Przykład</span><span class="sxs-lookup"><span data-stu-id="fbc4a-116">Example</span></span>

<span data-ttu-id="fbc4a-117">Załóżmy, że `IsEven : Int -> Bool` jest funkcją, która zwraca wartość, `true` Jeśli i tylko wtedy, gdy jej dane wejściowe są parzyste.</span><span class="sxs-lookup"><span data-stu-id="fbc4a-117">Suppose that `IsEven : Int -> Bool` is a function that returns `true` if and only if its input is even.</span></span> <span data-ttu-id="fbc4a-118">Następnie można go użyć w `IndexOf` celu znalezienia pierwszego elementu parzystego w tablicy:</span><span class="sxs-lookup"><span data-stu-id="fbc4a-118">Then, this can be used with `IndexOf` to find the first even element in an array:</span></span>

```qsharp
let items = [1, 3, 17, 2, 21];
let idx = IndexOf(IsEven, items); // returns 3
```