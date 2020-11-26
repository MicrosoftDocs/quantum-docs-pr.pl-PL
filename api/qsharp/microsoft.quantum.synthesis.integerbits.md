---
uid: Microsoft.Quantum.Synthesis.IntegerBits
title: IntegerBits, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: IntegerBits
qsharp.summary: Returns all positions in which bits of an integer are set.
ms.openlocfilehash: d6566716f5a63c090668d9582b7b000c16d1f6a5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96231096"
---
# <a name="integerbits-function"></a><span data-ttu-id="c5b16-102">IntegerBits, funkcja</span><span class="sxs-lookup"><span data-stu-id="c5b16-102">IntegerBits function</span></span>

<span data-ttu-id="c5b16-103">Przestrzeń nazw: [Microsoft. Quantum. Synteza](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="c5b16-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="c5b16-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c5b16-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c5b16-105">Zwraca wszystkie pozycje, w których są ustawiane bity liczby całkowitej.</span><span class="sxs-lookup"><span data-stu-id="c5b16-105">Returns all positions in which bits of an integer are set.</span></span>

```qsharp
function IntegerBits (value : Int, length : Int) : Int[]
```


## <a name="input"></a><span data-ttu-id="c5b16-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="c5b16-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="c5b16-107">wartość: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c5b16-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c5b16-108">Liczba nieujemna.</span><span class="sxs-lookup"><span data-stu-id="c5b16-108">A nonnegative number.</span></span>


### <a name="length--int"></a><span data-ttu-id="c5b16-109">Długość: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c5b16-109">length : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c5b16-110">Liczba bitów w rozszerzeniu binarnym `value` .</span><span class="sxs-lookup"><span data-stu-id="c5b16-110">The number of bits in the binary expansion of `value`.</span></span>



## <a name="output--int"></a><span data-ttu-id="c5b16-111">Wynik: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="c5b16-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="c5b16-112">Tablica zawierająca wszystkie pozycje bitowe (rozpoczynając od 0), które są 1 w rozszerzeniu binarnym, `value` biorąc pod uwagę wszystkie bity do położenia `length - 1` .</span><span class="sxs-lookup"><span data-stu-id="c5b16-112">An array containing all bit positions (starting from 0) that are 1 in the binary expansion of `value` considering all bits up to position `length - 1`.</span></span>  <span data-ttu-id="c5b16-113">Wszystkie pozycje są uporządkowane w tablicy według położenia w kolejności rosnącej.</span><span class="sxs-lookup"><span data-stu-id="c5b16-113">All positions are ordered in the array by position in an increasing order.</span></span>