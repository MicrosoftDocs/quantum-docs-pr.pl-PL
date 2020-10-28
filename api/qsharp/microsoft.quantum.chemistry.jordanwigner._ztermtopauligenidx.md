---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ZTermToPauliGenIdx
title: Funkcja _ZTermToPauliGenIdx
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ZTermToPauliGenIdx
qsharp.summary: Converts a GeneratorIndex describing a Z term to an expression 'GeneratorIndex[]' in terms of Paulis.
ms.openlocfilehash: 1569ec742778549b8754cdca8b2d9872310e8976
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714177"
---
# <a name="_ztermtopauligenidx-function"></a><span data-ttu-id="3024f-102">Funkcja _ZTermToPauliGenIdx</span><span class="sxs-lookup"><span data-stu-id="3024f-102">_ZTermToPauliGenIdx function</span></span>

<span data-ttu-id="3024f-103">Przestrzeń nazw: [Microsoft. Quantum. Chemia. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="3024f-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="3024f-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3024f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3024f-105">Konwertuje GeneratorIndex opisujący termin Z na wyrażenie "GeneratorIndex []" w postaci Pauld.</span><span class="sxs-lookup"><span data-stu-id="3024f-105">Converts a GeneratorIndex describing a Z term to an expression 'GeneratorIndex[]' in terms of Paulis.</span></span>

```qsharp
function _ZTermToPauliGenIdx (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.GeneratorIndex[]
```


## <a name="input"></a><span data-ttu-id="3024f-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="3024f-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="3024f-107">termin: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="3024f-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="3024f-108">`GeneratorIndex` reprezentujący okres Z.</span><span class="sxs-lookup"><span data-stu-id="3024f-108">`GeneratorIndex` representing a Z term.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="3024f-109">Wynik: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span><span class="sxs-lookup"><span data-stu-id="3024f-109">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span></span>

<span data-ttu-id="3024f-110">"GeneratorIndex []" wyraża się Z terminem do Pauli warunków.</span><span class="sxs-lookup"><span data-stu-id="3024f-110">'GeneratorIndex[]' expressing Z term as Pauli terms.</span></span>