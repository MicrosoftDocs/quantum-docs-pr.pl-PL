---
uid: Microsoft.Quantum.Chemistry.JordanWigner._PQandPQQRTermToPauliMajIdx_
title: _PQandPQQRTermToPauliMajIdx_ , funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _PQandPQQRTermToPauliMajIdx_
qsharp.summary: Converts a GeneratorIndex describing a PQ or PQQR term to an expression 'GeneratorIndex[]' in terms of Paulis
ms.openlocfilehash: 4ba13f42064d9311ffb29dbd9363aa3be978e702
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714364"
---
# <a name="_pqandpqqrtermtopaulimajidx_-function"></a><span data-ttu-id="eea5a-102">_PQandPQQRTermToPauliMajIdx_ , funkcja</span><span class="sxs-lookup"><span data-stu-id="eea5a-102">_PQandPQQRTermToPauliMajIdx_ function</span></span>

<span data-ttu-id="eea5a-103">Przestrzeń nazw: [Microsoft. Quantum. Chemia. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="eea5a-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="eea5a-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="eea5a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="eea5a-105">Konwertuje GeneratorIndex opisujący termin PQ lub PQQR na wyrażenie "GeneratorIndex []" w postaci Paul</span><span class="sxs-lookup"><span data-stu-id="eea5a-105">Converts a GeneratorIndex describing a PQ or PQQR term to an expression 'GeneratorIndex[]' in terms of Paulis</span></span>

```qsharp
function _PQandPQQRTermToPauliMajIdx_ (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex
```


## <a name="input"></a><span data-ttu-id="eea5a-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="eea5a-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="eea5a-107">termin: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="eea5a-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="eea5a-108">`GeneratorIndex` reprezentujący termin PQ lub PQQR.</span><span class="sxs-lookup"><span data-stu-id="eea5a-108">`GeneratorIndex` representing a PQ or PQQR term.</span></span>



## <a name="output--optimizedbetermindex"></a><span data-ttu-id="eea5a-109">Wynik: [OptimizedBETermIndex](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex)</span><span class="sxs-lookup"><span data-stu-id="eea5a-109">Output : [OptimizedBETermIndex](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex)</span></span>

<span data-ttu-id="eea5a-110">"GeneratorIndex []" wyrażanie PQ lub PQQR termin jako warunków Pauli.</span><span class="sxs-lookup"><span data-stu-id="eea5a-110">'GeneratorIndex[]' expressing PQ or PQQR term as Pauli terms.</span></span>