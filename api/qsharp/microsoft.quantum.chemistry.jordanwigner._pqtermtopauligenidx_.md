---
uid: Microsoft.Quantum.Chemistry.JordanWigner._PQTermToPauliGenIdx_
title: _PQTermToPauliGenIdx_ , funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _PQTermToPauliGenIdx_
qsharp.summary: Converts a GeneratorIndex describing a PQ term to an expression 'GeneratorIndex[]' in terms of Paulis
ms.openlocfilehash: 1f9567f327b5afc3054acbf1a615b44a54453004
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714345"
---
# <a name="_pqtermtopauligenidx_-function"></a><span data-ttu-id="f44a5-102">_PQTermToPauliGenIdx_ , funkcja</span><span class="sxs-lookup"><span data-stu-id="f44a5-102">_PQTermToPauliGenIdx_ function</span></span>

<span data-ttu-id="f44a5-103">Przestrzeń nazw: [Microsoft. Quantum. Chemia. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="f44a5-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="f44a5-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f44a5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f44a5-105">Konwertuje element GeneratorIndex opisujący termin PQ na wyrażenie "GeneratorIndex []" w postaci Paul</span><span class="sxs-lookup"><span data-stu-id="f44a5-105">Converts a GeneratorIndex describing a PQ term to an expression 'GeneratorIndex[]' in terms of Paulis</span></span>

```qsharp
function _PQTermToPauliGenIdx_ (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.GeneratorIndex[]
```


## <a name="input"></a><span data-ttu-id="f44a5-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="f44a5-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="f44a5-107">termin: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="f44a5-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="f44a5-108">`GeneratorIndex` reprezentujący termin PQ.</span><span class="sxs-lookup"><span data-stu-id="f44a5-108">`GeneratorIndex` representing a PQ term.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="f44a5-109">Wynik: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span><span class="sxs-lookup"><span data-stu-id="f44a5-109">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span></span>

<span data-ttu-id="f44a5-110">"GeneratorIndex []" wyraża PQ termin jako warunki Pauli.</span><span class="sxs-lookup"><span data-stu-id="f44a5-110">'GeneratorIndex[]' expressing PQ term as Pauli terms.</span></span>