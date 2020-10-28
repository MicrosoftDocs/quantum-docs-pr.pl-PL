---
uid: Microsoft.Quantum.Chemistry.JordanWigner._PQTermToPauliMajIdx_
title: _PQTermToPauliMajIdx_ , funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _PQTermToPauliMajIdx_
qsharp.summary: Converts a GeneratorIndex describing a PQ term to an expression 'GeneratorIndex[]' in terms of Paulis
ms.openlocfilehash: b75e9b61e05d6451bab378108c75b10334ac1e44
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714331"
---
# <a name="_pqtermtopaulimajidx_-function"></a><span data-ttu-id="a72d0-102">_PQTermToPauliMajIdx_ , funkcja</span><span class="sxs-lookup"><span data-stu-id="a72d0-102">_PQTermToPauliMajIdx_ function</span></span>

<span data-ttu-id="a72d0-103">Przestrzeń nazw: [Microsoft. Quantum. Chemia. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="a72d0-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="a72d0-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a72d0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a72d0-105">Konwertuje element GeneratorIndex opisujący termin PQ na wyrażenie "GeneratorIndex []" w postaci Paul</span><span class="sxs-lookup"><span data-stu-id="a72d0-105">Converts a GeneratorIndex describing a PQ term to an expression 'GeneratorIndex[]' in terms of Paulis</span></span>

```qsharp
function _PQTermToPauliMajIdx_ (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex
```


## <a name="input"></a><span data-ttu-id="a72d0-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="a72d0-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="a72d0-107">termin: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="a72d0-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="a72d0-108">`GeneratorIndex` reprezentujący termin PQ.</span><span class="sxs-lookup"><span data-stu-id="a72d0-108">`GeneratorIndex` representing a PQ term.</span></span>



## <a name="output--optimizedbetermindex"></a><span data-ttu-id="a72d0-109">Wynik: [OptimizedBETermIndex](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex)</span><span class="sxs-lookup"><span data-stu-id="a72d0-109">Output : [OptimizedBETermIndex](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex)</span></span>

<span data-ttu-id="a72d0-110">"GeneratorIndex []" wyraża PQ termin jako warunki Pauli.</span><span class="sxs-lookup"><span data-stu-id="a72d0-110">'GeneratorIndex[]' expressing PQ term as Pauli terms.</span></span>