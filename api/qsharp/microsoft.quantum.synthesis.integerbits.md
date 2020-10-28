---
uid: Microsoft.Quantum.Synthesis.IntegerBits
title: IntegerBits, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: IntegerBits
qsharp.summary: Returns all positions in which bits of an integer are set.
ms.openlocfilehash: ab459cd841cdac116cf0e98c094834f628b6a2d3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719844"
---
# <a name="integerbits-function"></a><span data-ttu-id="98b29-102">IntegerBits, funkcja</span><span class="sxs-lookup"><span data-stu-id="98b29-102">IntegerBits function</span></span>

<span data-ttu-id="98b29-103">Przestrzeń nazw: [Microsoft. Quantum. Synteza](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="98b29-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="98b29-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="98b29-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="98b29-105">Zwraca wszystkie pozycje, w których są ustawiane bity liczby całkowitej.</span><span class="sxs-lookup"><span data-stu-id="98b29-105">Returns all positions in which bits of an integer are set.</span></span>

```qsharp
function IntegerBits (value : Int, length : Int) : Int[]
```


## <a name="input"></a><span data-ttu-id="98b29-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="98b29-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="98b29-107">wartość: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="98b29-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="98b29-108">Liczba nieujemna.</span><span class="sxs-lookup"><span data-stu-id="98b29-108">A nonnegative number.</span></span>


### <a name="length--int"></a><span data-ttu-id="98b29-109">Długość: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="98b29-109">length : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="98b29-110">Liczba bitów w rozszerzeniu binarnym `value` .</span><span class="sxs-lookup"><span data-stu-id="98b29-110">The number of bits in the binary expansion of `value`.</span></span>



## <a name="output--int"></a><span data-ttu-id="98b29-111">Wynik: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="98b29-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="98b29-112">Tablica zawierająca wszystkie pozycje bitowe (rozpoczynając od 0), które są 1 w rozszerzeniu binarnym, `value` biorąc pod uwagę wszystkie bity do położenia `length - 1` .</span><span class="sxs-lookup"><span data-stu-id="98b29-112">An array containing all bit positions (starting from 0) that are 1 in the binary expansion of `value` considering all bits up to position `length - 1`.</span></span>  <span data-ttu-id="98b29-113">Wszystkie pozycje są uporządkowane w tablicy według położenia w kolejności rosnącej.</span><span class="sxs-lookup"><span data-stu-id="98b29-113">All positions are ordered in the array by position in an increasing order.</span></span>