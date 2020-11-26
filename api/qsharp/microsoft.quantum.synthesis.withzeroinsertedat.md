---
uid: Microsoft.Quantum.Synthesis.WithZeroInsertedAt
title: WithZeroInsertedAt, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: WithZeroInsertedAt
qsharp.summary: Insert a 0-bit into an integer
ms.openlocfilehash: 414b703151b9152aa69709d9c28e68e5ae63506f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228869"
---
# <a name="withzeroinsertedat-function"></a><span data-ttu-id="877c9-102">WithZeroInsertedAt, funkcja</span><span class="sxs-lookup"><span data-stu-id="877c9-102">WithZeroInsertedAt function</span></span>

<span data-ttu-id="877c9-103">Przestrzeń nazw: [Microsoft. Quantum. Synteza](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="877c9-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="877c9-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="877c9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="877c9-105">Wstaw 0-bitowe do liczby całkowitej</span><span class="sxs-lookup"><span data-stu-id="877c9-105">Insert a 0-bit into an integer</span></span>

```qsharp
function WithZeroInsertedAt (position : Int, value : Int) : Int
```


## <a name="description"></a><span data-ttu-id="877c9-106">Opis</span><span class="sxs-lookup"><span data-stu-id="877c9-106">Description</span></span>

<span data-ttu-id="877c9-107">Ta operacja Pobiera liczbę całkowitą, wstawia 0 w bitach `position` i zwraca zaktualizowaną wartość jako liczbę całkowitą.</span><span class="sxs-lookup"><span data-stu-id="877c9-107">This operation takes an integer, inserts a 0 at bit `position`, and returns the updated value as an integer.</span></span>  <span data-ttu-id="877c9-108">Na przykład wstawianie 0 w pozycji 2 w liczbie 10 (10 zł _ {10} = 1010_ {2} $) zwraca liczbę 18 ($18 _ {10} = 10010_ {2} $).</span><span class="sxs-lookup"><span data-stu-id="877c9-108">For example, inserting a 0 at position 2 in the number 10 ($10_{10} = 1010_{2}$) returns the number 18 ($18_{10} = 10010_{2}$).</span></span>

## <a name="input"></a><span data-ttu-id="877c9-109">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="877c9-109">Input</span></span>

### <a name="position--int"></a><span data-ttu-id="877c9-110">Pozycja: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="877c9-110">position : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="877c9-111">Położenie, w którym wstawiono 0</span><span class="sxs-lookup"><span data-stu-id="877c9-111">The position at which 0 is inserted</span></span>


### <a name="value--int"></a><span data-ttu-id="877c9-112">wartość: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="877c9-112">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="877c9-113">Wartość, która została zmodyfikowana</span><span class="sxs-lookup"><span data-stu-id="877c9-113">The value that is modified</span></span>



## <a name="output--int"></a><span data-ttu-id="877c9-114">Wynik: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="877c9-114">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="877c9-115">Zmodyfikowana wartość</span><span class="sxs-lookup"><span data-stu-id="877c9-115">Modified value</span></span>