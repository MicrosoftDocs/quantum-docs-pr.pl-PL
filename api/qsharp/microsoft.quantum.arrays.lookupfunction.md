---
uid: Microsoft.Quantum.Arrays.LookupFunction
title: LookupFunction, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: LookupFunction
qsharp.summary: Given an array, returns a function which returns elements of that array.
ms.openlocfilehash: 22b56bb7e9f03ebc5b2225efb2e6450d56022664
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845696"
---
# <a name="lookupfunction-function"></a><span data-ttu-id="04dc4-102">LookupFunction, funkcja</span><span class="sxs-lookup"><span data-stu-id="04dc4-102">LookupFunction function</span></span>

<span data-ttu-id="04dc4-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="04dc4-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="04dc4-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="04dc4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="04dc4-105">Dana tablica zwraca funkcję, która zwraca elementy tej tablicy.</span><span class="sxs-lookup"><span data-stu-id="04dc4-105">Given an array, returns a function which returns elements of that array.</span></span>

```qsharp
function LookupFunction<'T> (array : 'T[]) : (Int -> 'T)
```


## <a name="input"></a><span data-ttu-id="04dc4-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="04dc4-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="04dc4-107">Tablica: t []</span><span class="sxs-lookup"><span data-stu-id="04dc4-107">array : 'T[]</span></span>

<span data-ttu-id="04dc4-108">Tablica, która ma być reprezentowana jako funkcja wyszukiwania.</span><span class="sxs-lookup"><span data-stu-id="04dc4-108">The array to be represented as a lookup function.</span></span>



## <a name="output--int---t"></a><span data-ttu-id="04dc4-109">Wynik: [int](xref:microsoft.quantum.lang-ref.int) -> 't</span><span class="sxs-lookup"><span data-stu-id="04dc4-109">Output : [Int](xref:microsoft.quantum.lang-ref.int) -> 'T</span></span>

<span data-ttu-id="04dc4-110">Funkcja `f` , która `f(idx) == f[idx]` .</span><span class="sxs-lookup"><span data-stu-id="04dc4-110">A function `f` such that `f(idx) == f[idx]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="04dc4-111">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="04dc4-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="04dc4-112">'C</span><span class="sxs-lookup"><span data-stu-id="04dc4-112">'T</span></span>

<span data-ttu-id="04dc4-113">Typ elementów tablicy reprezentowanej jako funkcja wyszukiwania.</span><span class="sxs-lookup"><span data-stu-id="04dc4-113">The type of the elements of the array being represented as a lookup function.</span></span>

## <a name="remarks"></a><span data-ttu-id="04dc4-114">Uwagi</span><span class="sxs-lookup"><span data-stu-id="04dc4-114">Remarks</span></span>

<span data-ttu-id="04dc4-115">Ta funkcja jest głównie przydatna do współdziałania z funkcjami i operacjami, które przyjmują `Int -> 'T` funkcje jako argumenty.</span><span class="sxs-lookup"><span data-stu-id="04dc4-115">This function is mainly useful for interoperating with functions and operations that take `Int -> 'T` functions as their arguments.</span></span> <span data-ttu-id="04dc4-116">Jest to typowe, na przykład w bibliotece reprezentacji generatora, gdzie funkcje są używane, aby uniknąć konieczności rejestrowania całej tablicy w pamięci.</span><span class="sxs-lookup"><span data-stu-id="04dc4-116">This is common, for instance, in the generator representation library, where functions are used to avoid the need to record an entire array in memory.</span></span>