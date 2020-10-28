---
uid: Microsoft.Quantum.Chemistry.JordanWigner._V0123TermToPauliGenIdx_
title: _V0123TermToPauliGenIdx_ , funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _V0123TermToPauliGenIdx_
qsharp.summary: Converts a GeneratorIndex describing a PQRS term to an expression 'GeneratorIndex[]' in terms of Paulis
ms.openlocfilehash: b522691d6826933122e2ebac051b15e35b9902e2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714205"
---
# <a name="_v0123termtopauligenidx_-function"></a><span data-ttu-id="2552d-102">_V0123TermToPauliGenIdx_ , funkcja</span><span class="sxs-lookup"><span data-stu-id="2552d-102">_V0123TermToPauliGenIdx_ function</span></span>

<span data-ttu-id="2552d-103">Przestrzeń nazw: [Microsoft. Quantum. Chemia. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="2552d-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="2552d-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2552d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2552d-105">Konwertuje element GeneratorIndex opisujący termin PQRS na wyrażenie "GeneratorIndex []" w postaci Paul</span><span class="sxs-lookup"><span data-stu-id="2552d-105">Converts a GeneratorIndex describing a PQRS term to an expression 'GeneratorIndex[]' in terms of Paulis</span></span>

```qsharp
function _V0123TermToPauliGenIdx_ (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.GeneratorIndex[]
```


## <a name="input"></a><span data-ttu-id="2552d-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="2552d-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="2552d-107">termin: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="2552d-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="2552d-108">`GeneratorIndex` reprezentujący termin PQRS.</span><span class="sxs-lookup"><span data-stu-id="2552d-108">`GeneratorIndex` representing a PQRS term.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="2552d-109">Wynik: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span><span class="sxs-lookup"><span data-stu-id="2552d-109">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span></span>

<span data-ttu-id="2552d-110">"GeneratorIndex []" wyraża PQRS termin jako warunki Pauli.</span><span class="sxs-lookup"><span data-stu-id="2552d-110">'GeneratorIndex[]' expressing PQRS term as Pauli terms.</span></span>