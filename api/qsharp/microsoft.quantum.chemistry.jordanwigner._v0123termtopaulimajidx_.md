---
uid: Microsoft.Quantum.Chemistry.JordanWigner._V0123TermToPauliMajIdx_
title: _V0123TermToPauliMajIdx_ , funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _V0123TermToPauliMajIdx_
qsharp.summary: Converts a GeneratorIndex describing a PQRS term to an expression 'GeneratorIndex[]' in terms of Paulis
ms.openlocfilehash: 7295b510de2621698d48d40ac28e234d0c8915eb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714191"
---
# <a name="_v0123termtopaulimajidx_-function"></a><span data-ttu-id="4296f-102">_V0123TermToPauliMajIdx_ , funkcja</span><span class="sxs-lookup"><span data-stu-id="4296f-102">_V0123TermToPauliMajIdx_ function</span></span>

<span data-ttu-id="4296f-103">Przestrzeń nazw: [Microsoft. Quantum. Chemia. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="4296f-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="4296f-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4296f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4296f-105">Konwertuje element GeneratorIndex opisujący termin PQRS na wyrażenie "GeneratorIndex []" w postaci Paul</span><span class="sxs-lookup"><span data-stu-id="4296f-105">Converts a GeneratorIndex describing a PQRS term to an expression 'GeneratorIndex[]' in terms of Paulis</span></span>

```qsharp
function _V0123TermToPauliMajIdx_ (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex[]
```


## <a name="input"></a><span data-ttu-id="4296f-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="4296f-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="4296f-107">termin: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="4296f-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="4296f-108">`GeneratorIndex` reprezentujący termin PQRS.</span><span class="sxs-lookup"><span data-stu-id="4296f-108">`GeneratorIndex` representing a PQRS term.</span></span>



## <a name="output--optimizedbetermindex"></a><span data-ttu-id="4296f-109">Wynik: [OptimizedBETermIndex](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex)[]</span><span class="sxs-lookup"><span data-stu-id="4296f-109">Output : [OptimizedBETermIndex](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex)[]</span></span>

<span data-ttu-id="4296f-110">"GeneratorIndex []" wyraża PQRS termin jako warunki Pauli.</span><span class="sxs-lookup"><span data-stu-id="4296f-110">'GeneratorIndex[]' expressing PQRS term as Pauli terms.</span></span>