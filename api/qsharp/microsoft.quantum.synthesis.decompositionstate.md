---
uid: Microsoft.Quantum.Synthesis.DecompositionState
title: DecompositionState typ zdefiniowany przez użytkownika
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: DecompositionState
qsharp.summary: State during decomposition based on variable indexes
ms.openlocfilehash: cd2a55013f1232d4158dd6c33143b7cf6c0aafbc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203199"
---
# <a name="decompositionstate-user-defined-type"></a><span data-ttu-id="3bcfa-102">DecompositionState typ zdefiniowany przez użytkownika</span><span class="sxs-lookup"><span data-stu-id="3bcfa-102">DecompositionState user defined type</span></span>

<span data-ttu-id="3bcfa-103">Przestrzeń nazw: [Microsoft. Quantum. Synteza](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="3bcfa-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="3bcfa-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3bcfa-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3bcfa-105">Stan podczas dekompozycji na podstawie indeksów zmiennych</span><span class="sxs-lookup"><span data-stu-id="3bcfa-105">State during decomposition based on variable indexes</span></span>

```qsharp

newtype DecompositionState = (Perm : Int[], Lfunctions : (BigInt, Int)[], Rfunctions : (BigInt, Int)[]);
```



## <a name="named-items"></a><span data-ttu-id="3bcfa-106">Nazwane elementy</span><span class="sxs-lookup"><span data-stu-id="3bcfa-106">Named Items</span></span>

### <a name="perm--int"></a><span data-ttu-id="3bcfa-107">Uprawnienie: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="3bcfa-107">Perm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>


### <a name="lfunctions--bigintint"></a><span data-ttu-id="3bcfa-108">Lfunctions: ([bigint](xref:microsoft.quantum.lang-ref.bigint),[int](xref:microsoft.quantum.lang-ref.int)) []</span><span class="sxs-lookup"><span data-stu-id="3bcfa-108">Lfunctions : ([BigInt](xref:microsoft.quantum.lang-ref.bigint),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>


### <a name="rfunctions--bigintint"></a><span data-ttu-id="3bcfa-109">Rfunctions: ([bigint](xref:microsoft.quantum.lang-ref.bigint),[int](xref:microsoft.quantum.lang-ref.int)) []</span><span class="sxs-lookup"><span data-stu-id="3bcfa-109">Rfunctions : ([BigInt](xref:microsoft.quantum.lang-ref.bigint),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>



## <a name="description"></a><span data-ttu-id="3bcfa-110">Opis</span><span class="sxs-lookup"><span data-stu-id="3bcfa-110">Description</span></span>

<span data-ttu-id="3bcfa-111">Stan zawiera bieżącą permutację i aktualnie wygenerowane funkcje dla kontrolowanych bram po lewej stronie oraz kontrolowane bramy po prawej stronie.</span><span class="sxs-lookup"><span data-stu-id="3bcfa-111">The state holds the current permutation and the currently generated functions for controlled gates on the left, and controlled gates on the right.</span></span>