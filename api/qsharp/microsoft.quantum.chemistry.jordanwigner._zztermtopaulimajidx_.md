---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ZZTermToPauliMajIdx_
title: _ZZTermToPauliMajIdx_ , funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ZZTermToPauliMajIdx_
qsharp.summary: Converts a GeneratorIndex describing a ZZ term to an expression 'GeneratorIndex[]' in terms of Paulis.
ms.openlocfilehash: 8c9223d54585f91e1616021bf0643e558d57589c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714126"
---
# <a name="_zztermtopaulimajidx_-function"></a><span data-ttu-id="4f730-102">_ZZTermToPauliMajIdx_ , funkcja</span><span class="sxs-lookup"><span data-stu-id="4f730-102">_ZZTermToPauliMajIdx_ function</span></span>

<span data-ttu-id="4f730-103">Przestrzeń nazw: [Microsoft. Quantum. Chemia. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="4f730-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="4f730-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4f730-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4f730-105">Konwertuje GeneratorIndex opisujący termin ZZ na wyrażenie "GeneratorIndex []" w postaci Pauld.</span><span class="sxs-lookup"><span data-stu-id="4f730-105">Converts a GeneratorIndex describing a ZZ term to an expression 'GeneratorIndex[]' in terms of Paulis.</span></span>

```qsharp
function _ZZTermToPauliMajIdx_ (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex
```


## <a name="input"></a><span data-ttu-id="4f730-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="4f730-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="4f730-107">termin: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="4f730-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="4f730-108">`GeneratorIndex` reprezentujący termin ZZ.</span><span class="sxs-lookup"><span data-stu-id="4f730-108">`GeneratorIndex` representing a ZZ term.</span></span>



## <a name="output--optimizedbetermindex"></a><span data-ttu-id="4f730-109">Wynik: [OptimizedBETermIndex](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex)</span><span class="sxs-lookup"><span data-stu-id="4f730-109">Output : [OptimizedBETermIndex](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex)</span></span>

<span data-ttu-id="4f730-110">"GeneratorIndex []" wyraża ZZ termin jako warunki Pauli.</span><span class="sxs-lookup"><span data-stu-id="4f730-110">'GeneratorIndex[]' expressing ZZ term as Pauli terms.</span></span>