---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionallyIntrinsicC
title: ApplyConditionallyIntrinsicC, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionallyIntrinsicC
qsharp.summary: ''
ms.openlocfilehash: 54367d89636eb69462040e83cc3c4b6a9f734c0c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720141"
---
# <a name="applyconditionallyintrinsicc-operation"></a><span data-ttu-id="029f0-102">ApplyConditionallyIntrinsicC, operacja</span><span class="sxs-lookup"><span data-stu-id="029f0-102">ApplyConditionallyIntrinsicC operation</span></span>

<span data-ttu-id="029f0-103">Przestrzeń nazw: [Microsoft. Quantum. Symulacja. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="029f0-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="029f0-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="029f0-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyConditionallyIntrinsicC (measurementResults : Result[], resultsValues : Result[], onEqualOp : (Unit => Unit is Ctl), onNonEqualOp : (Unit => Unit is Ctl)) : Unit
```


## <a name="input"></a><span data-ttu-id="029f0-105">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="029f0-105">Input</span></span>

### <a name="measurementresults--__invalidresult__"></a><span data-ttu-id="029f0-106">measurementResults: __nieprawidłowy <Result>__ []</span><span class="sxs-lookup"><span data-stu-id="029f0-106">measurementResults : __invalid<Result>__ []</span></span>




### <a name="resultsvalues--__invalidresult__"></a><span data-ttu-id="029f0-107">resultsValues: __nieprawidłowy <Result>__ []</span><span class="sxs-lookup"><span data-stu-id="029f0-107">resultsValues : __invalid<Result>__ []</span></span>




### <a name="onequalop--unit--unit-ctl"></a><span data-ttu-id="029f0-108">onEqualOp: [Unit](xref:microsoft.quantum.lang-ref.unit) => lista CTL [jednostki](xref:microsoft.quantum.lang-ref.unit) jednostki</span><span class="sxs-lookup"><span data-stu-id="029f0-108">onEqualOp : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>




### <a name="onnonequalop--unit--unit-ctl"></a><span data-ttu-id="029f0-109">onNonEqualOp: [Unit](xref:microsoft.quantum.lang-ref.unit) => lista CTL [jednostki](xref:microsoft.quantum.lang-ref.unit) jednostki</span><span class="sxs-lookup"><span data-stu-id="029f0-109">onNonEqualOp : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>





## <a name="output--unit"></a><span data-ttu-id="029f0-110">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="029f0-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

