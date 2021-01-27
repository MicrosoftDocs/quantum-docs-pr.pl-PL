---
uid: Microsoft.Quantum.Research.Chemistry._DeltaParityCNOTbitstring
title: Funkcja _DeltaParityCNOTbitstring
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _DeltaParityCNOTbitstring
qsharp.summary: Classical processing step of `ApplyDeltaParity`. This computes a list of control qubits for evaluating parity difference between any two PQRS... terms of even length.
ms.openlocfilehash: 3dd2d299a094577d377780d731e76287815e8d03
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847600"
---
# <a name="_deltaparitycnotbitstring-function"></a><span data-ttu-id="ba340-102">Funkcja _DeltaParityCNOTbitstring</span><span class="sxs-lookup"><span data-stu-id="ba340-102">_DeltaParityCNOTbitstring function</span></span>

<span data-ttu-id="ba340-103">Przestrzeń nazw: [Microsoft. Quantum. Research. Chemia](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="ba340-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="ba340-104">Pakiet: [Microsoft. Quantum. Research. Chemia](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="ba340-104">Package: [Microsoft.Quantum.Research.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span></span>


<span data-ttu-id="ba340-105">Etap klasycznego przetwarzania `ApplyDeltaParity` .</span><span class="sxs-lookup"><span data-stu-id="ba340-105">Classical processing step of `ApplyDeltaParity`.</span></span>
<span data-ttu-id="ba340-106">To oblicza listę qubits kontroli do oceny różnicy parzystości między dowolnymi dwoma PQRS... warunki nawet długości.</span><span class="sxs-lookup"><span data-stu-id="ba340-106">This computes a list of control qubits for evaluating parity difference between any two PQRS... terms of even length.</span></span>

```qsharp
function _DeltaParityCNOTbitstring (prevFermionicTerm : Int[], nextFermionicTerm : Int[]) : (Int, Bool[])
```


## <a name="input"></a><span data-ttu-id="ba340-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="ba340-107">Input</span></span>

### <a name="prevfermionicterm--int"></a><span data-ttu-id="ba340-108">prevFermionicTerm: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="ba340-108">prevFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>




### <a name="nextfermionicterm--int"></a><span data-ttu-id="ba340-109">nextFermionicTerm: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="ba340-109">nextFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>





## <a name="output--intbool"></a><span data-ttu-id="ba340-110">Wynik: ([int](xref:microsoft.quantum.lang-ref.int),[bool](xref:microsoft.quantum.lang-ref.bool)[])</span><span class="sxs-lookup"><span data-stu-id="ba340-110">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Bool](xref:microsoft.quantum.lang-ref.bool)[])</span></span>



## <a name="remarks"></a><span data-ttu-id="ba340-111">Uwagi</span><span class="sxs-lookup"><span data-stu-id="ba340-111">Remarks</span></span>

<span data-ttu-id="ba340-112">Przyjęto założenie, że długość warunków jest parzysta.</span><span class="sxs-lookup"><span data-stu-id="ba340-112">This assumes that the length of terms is even.</span></span>
<span data-ttu-id="ba340-113">Oblicza listę kontrolek z różnicą parzystości między dowolnym z dwóch warunków.</span><span class="sxs-lookup"><span data-stu-id="ba340-113">Computes list of controls for parity difference between any two terms.</span></span>
<span data-ttu-id="ba340-114">Przyjęto założenie, że listy wejściowe są sortowane w kolejności rosnącej.</span><span class="sxs-lookup"><span data-stu-id="ba340-114">This assumes that the input lists is sorted in ascending order.</span></span>