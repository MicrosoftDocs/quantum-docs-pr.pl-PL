---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ZTermToPauliMajIdx_
title: _ZTermToPauliMajIdx_ , funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ZTermToPauliMajIdx_
qsharp.summary: Converts a GeneratorIndex describing a Z term to an expression 'GeneratorIndex[]' in terms of Paulis.
ms.openlocfilehash: 890e60c4b7c5bc474c9f00b59dac6bfddb0e891b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714149"
---
# <a name="_ztermtopaulimajidx_-function"></a><span data-ttu-id="31818-102">_ZTermToPauliMajIdx_ , funkcja</span><span class="sxs-lookup"><span data-stu-id="31818-102">_ZTermToPauliMajIdx_ function</span></span>

<span data-ttu-id="31818-103">Przestrzeń nazw: [Microsoft. Quantum. Chemia. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="31818-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="31818-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="31818-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="31818-105">Konwertuje GeneratorIndex opisujący termin Z na wyrażenie "GeneratorIndex []" w postaci Pauld.</span><span class="sxs-lookup"><span data-stu-id="31818-105">Converts a GeneratorIndex describing a Z term to an expression 'GeneratorIndex[]' in terms of Paulis.</span></span>

```qsharp
function _ZTermToPauliMajIdx_ (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex
```


## <a name="input"></a><span data-ttu-id="31818-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="31818-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="31818-107">termin: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="31818-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="31818-108">`GeneratorIndex` reprezentujący okres Z.</span><span class="sxs-lookup"><span data-stu-id="31818-108">`GeneratorIndex` representing a Z term.</span></span>



## <a name="output--optimizedbetermindex"></a><span data-ttu-id="31818-109">Wynik: [OptimizedBETermIndex](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex)</span><span class="sxs-lookup"><span data-stu-id="31818-109">Output : [OptimizedBETermIndex](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex)</span></span>

<span data-ttu-id="31818-110">"GeneratorIndex []" wyraża się Z terminem do Pauli warunków.</span><span class="sxs-lookup"><span data-stu-id="31818-110">'GeneratorIndex[]' expressing Z term as Pauli terms.</span></span>