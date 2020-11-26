---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionally
title: ApplyConditionally, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionally
qsharp.summary: ''
ms.openlocfilehash: 24d52576d2fb3e83f294874be4b0d1cd6a80f188
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229073"
---
# <a name="applyconditionally-operation"></a><span data-ttu-id="5dd0b-102">ApplyConditionally, operacja</span><span class="sxs-lookup"><span data-stu-id="5dd0b-102">ApplyConditionally operation</span></span>

<span data-ttu-id="5dd0b-103">Przestrzeń nazw: [Microsoft. Quantum. Symulacja. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="5dd0b-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="5dd0b-104">Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="5dd0b-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyConditionally<'T, 'U> (measurementResults : Result[], resultsValues : Result[], (onEqualOp : ('T => Unit), equalArg : 'T), (onNonEqualOp : ('U => Unit), nonEqualArg : 'U)) : Unit
```


## <a name="input"></a><span data-ttu-id="5dd0b-105">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="5dd0b-105">Input</span></span>

### <a name="measurementresults--__invalidresult__"></a><span data-ttu-id="5dd0b-106">measurementResults: __nieprawidłowy <Result>__[]</span><span class="sxs-lookup"><span data-stu-id="5dd0b-106">measurementResults : __invalid<Result>__[]</span></span>




### <a name="resultsvalues--__invalidresult__"></a><span data-ttu-id="5dd0b-107">resultsValues: __nieprawidłowy <Result>__[]</span><span class="sxs-lookup"><span data-stu-id="5dd0b-107">resultsValues : __invalid<Result>__[]</span></span>




### <a name="onequalop--t--unit"></a><span data-ttu-id="5dd0b-108">onEqualOp: 'T = [jednostka](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="5dd0b-108">onEqualOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="equalarg--t"></a><span data-ttu-id="5dd0b-109">equalArg: 'T</span><span class="sxs-lookup"><span data-stu-id="5dd0b-109">equalArg : 'T</span></span>




### <a name="onnonequalop--u--unit"></a><span data-ttu-id="5dd0b-110">onNonEqualOp: ' U = [jednostka](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="5dd0b-110">onNonEqualOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="nonequalarg--u"></a><span data-ttu-id="5dd0b-111">nonEqualArg: ' U</span><span class="sxs-lookup"><span data-stu-id="5dd0b-111">nonEqualArg : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="5dd0b-112">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5dd0b-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="5dd0b-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="5dd0b-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="5dd0b-114">'C</span><span class="sxs-lookup"><span data-stu-id="5dd0b-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="5dd0b-115">' U</span><span class="sxs-lookup"><span data-stu-id="5dd0b-115">'U</span></span>

