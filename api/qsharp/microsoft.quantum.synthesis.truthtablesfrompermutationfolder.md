---
uid: Microsoft.Quantum.Synthesis.TruthTablesFromPermutationFolder
title: TruthTablesFromPermutationFolder, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: TruthTablesFromPermutationFolder
qsharp.summary: Decomposition logic for a single variable index
ms.openlocfilehash: 86e112782825303805029b2f9f6cfd9d6ce9e8b6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96231028"
---
# <a name="truthtablesfrompermutationfolder-function"></a><span data-ttu-id="d117b-102">TruthTablesFromPermutationFolder, funkcja</span><span class="sxs-lookup"><span data-stu-id="d117b-102">TruthTablesFromPermutationFolder function</span></span>

<span data-ttu-id="d117b-103">Przestrzeń nazw: [Microsoft. Quantum. Synteza](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="d117b-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="d117b-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d117b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d117b-105">Logika dekompozycji dla pojedynczego indeksu zmiennej</span><span class="sxs-lookup"><span data-stu-id="d117b-105">Decomposition logic for a single variable index</span></span>

```qsharp
function TruthTablesFromPermutationFolder (numVars : Int, state : Microsoft.Quantum.Synthesis.DecompositionState, index : Int) : Microsoft.Quantum.Synthesis.DecompositionState
```


## <a name="description"></a><span data-ttu-id="d117b-106">Opis</span><span class="sxs-lookup"><span data-stu-id="d117b-106">Description</span></span>

<span data-ttu-id="d117b-107">Powoduje to przyjęcie bieżącego stanu i wygenerowanie zaktualizowanej permutacji oraz dodanie nowych funkcji dla kontrolowanych bram.</span><span class="sxs-lookup"><span data-stu-id="d117b-107">This takes the current state and generates an updated permutation and possibly adds new functions for controlled gates.</span></span>

## <a name="input"></a><span data-ttu-id="d117b-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="d117b-108">Input</span></span>

### <a name="numvars--int"></a><span data-ttu-id="d117b-109">numVars: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d117b-109">numVars : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="state--decompositionstate"></a><span data-ttu-id="d117b-110">stan: [DecompositionState](xref:Microsoft.Quantum.Synthesis.DecompositionState)</span><span class="sxs-lookup"><span data-stu-id="d117b-110">state : [DecompositionState](xref:Microsoft.Quantum.Synthesis.DecompositionState)</span></span>




### <a name="index--int"></a><span data-ttu-id="d117b-111">indeks: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d117b-111">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--decompositionstate"></a><span data-ttu-id="d117b-112">Wynik: [DecompositionState](xref:Microsoft.Quantum.Synthesis.DecompositionState)</span><span class="sxs-lookup"><span data-stu-id="d117b-112">Output : [DecompositionState](xref:Microsoft.Quantum.Synthesis.DecompositionState)</span></span>

