---
uid: Microsoft.Quantum.Synthesis.TruthTablesFromPermutationFolder
title: TruthTablesFromPermutationFolder, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: TruthTablesFromPermutationFolder
qsharp.summary: Decomposition logic for a single variable index
ms.openlocfilehash: 6b00c9e880ed7b7b3bf446dcb17dab3bab7a83a7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724457"
---
# <a name="truthtablesfrompermutationfolder-function"></a><span data-ttu-id="3b755-102">TruthTablesFromPermutationFolder, funkcja</span><span class="sxs-lookup"><span data-stu-id="3b755-102">TruthTablesFromPermutationFolder function</span></span>

<span data-ttu-id="3b755-103">Przestrzeń nazw: [Microsoft. Quantum. Synteza](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="3b755-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="3b755-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3b755-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3b755-105">Logika dekompozycji dla pojedynczego indeksu zmiennej</span><span class="sxs-lookup"><span data-stu-id="3b755-105">Decomposition logic for a single variable index</span></span>

```qsharp
function TruthTablesFromPermutationFolder (numVars : Int, state : Microsoft.Quantum.Synthesis.DecompositionState, index : Int) : Microsoft.Quantum.Synthesis.DecompositionState
```


## <a name="description"></a><span data-ttu-id="3b755-106">Opis</span><span class="sxs-lookup"><span data-stu-id="3b755-106">Description</span></span>

<span data-ttu-id="3b755-107">Powoduje to przyjęcie bieżącego stanu i wygenerowanie zaktualizowanej permutacji oraz dodanie nowych funkcji dla kontrolowanych bram.</span><span class="sxs-lookup"><span data-stu-id="3b755-107">This takes the current state and generates an updated permutation and possibly adds new functions for controlled gates.</span></span>

## <a name="input"></a><span data-ttu-id="3b755-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="3b755-108">Input</span></span>

### <a name="numvars--int"></a><span data-ttu-id="3b755-109">numVars: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3b755-109">numVars : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="state--decompositionstate"></a><span data-ttu-id="3b755-110">stan: [DecompositionState](xref:Microsoft.Quantum.Synthesis.DecompositionState)</span><span class="sxs-lookup"><span data-stu-id="3b755-110">state : [DecompositionState](xref:Microsoft.Quantum.Synthesis.DecompositionState)</span></span>




### <a name="index--int"></a><span data-ttu-id="3b755-111">indeks: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3b755-111">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--decompositionstate"></a><span data-ttu-id="3b755-112">Wynik: [DecompositionState](xref:Microsoft.Quantum.Synthesis.DecompositionState)</span><span class="sxs-lookup"><span data-stu-id="3b755-112">Output : [DecompositionState](xref:Microsoft.Quantum.Synthesis.DecompositionState)</span></span>

