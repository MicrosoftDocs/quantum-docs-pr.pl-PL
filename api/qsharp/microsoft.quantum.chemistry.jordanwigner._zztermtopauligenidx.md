---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ZZTermToPauliGenIdx
title: Funkcja _ZZTermToPauliGenIdx
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ZZTermToPauliGenIdx
qsharp.summary: Converts a GeneratorIndex describing a ZZ term to an expression 'GeneratorIndex[]' in terms of Paulis.
ms.openlocfilehash: f8a173e2adb4494a08b48158a010f264562bbaa6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714140"
---
# <a name="_zztermtopauligenidx-function"></a><span data-ttu-id="0e540-102">Funkcja _ZZTermToPauliGenIdx</span><span class="sxs-lookup"><span data-stu-id="0e540-102">_ZZTermToPauliGenIdx function</span></span>

<span data-ttu-id="0e540-103">Przestrzeń nazw: [Microsoft. Quantum. Chemia. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="0e540-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="0e540-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0e540-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0e540-105">Konwertuje GeneratorIndex opisujący termin ZZ na wyrażenie "GeneratorIndex []" w postaci Pauld.</span><span class="sxs-lookup"><span data-stu-id="0e540-105">Converts a GeneratorIndex describing a ZZ term to an expression 'GeneratorIndex[]' in terms of Paulis.</span></span>

```qsharp
function _ZZTermToPauliGenIdx (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.GeneratorIndex[]
```


## <a name="input"></a><span data-ttu-id="0e540-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="0e540-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="0e540-107">termin: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="0e540-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="0e540-108">`GeneratorIndex` reprezentujący termin ZZ.</span><span class="sxs-lookup"><span data-stu-id="0e540-108">`GeneratorIndex` representing a ZZ term.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="0e540-109">Wynik: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span><span class="sxs-lookup"><span data-stu-id="0e540-109">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span></span>

<span data-ttu-id="0e540-110">"GeneratorIndex []" wyraża ZZ termin jako warunki Pauli.</span><span class="sxs-lookup"><span data-stu-id="0e540-110">'GeneratorIndex[]' expressing ZZ term as Pauli terms.</span></span>