---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionallyIntrinsicC
title: ApplyConditionallyIntrinsicC, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionallyIntrinsicC
qsharp.summary: ''
ms.openlocfilehash: 64c6693181704d229e36a3e3748258f66e093d96
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855749"
---
# <a name="applyconditionallyintrinsicc-operation"></a><span data-ttu-id="dea46-102">ApplyConditionallyIntrinsicC, operacja</span><span class="sxs-lookup"><span data-stu-id="dea46-102">ApplyConditionallyIntrinsicC operation</span></span>

<span data-ttu-id="dea46-103">Przestrzeń nazw: [Microsoft. Quantum. Symulacja. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="dea46-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="dea46-104">Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="dea46-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyConditionallyIntrinsicC (measurementResults : Result[], resultsValues : Result[], onEqualOp : (Unit => Unit is Ctl), onNonEqualOp : (Unit => Unit is Ctl)) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="dea46-105">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="dea46-105">Input</span></span>

### <a name="measurementresults--__invalidresult__"></a><span data-ttu-id="dea46-106">measurementResults: __nieprawidłowy <Result>__[]</span><span class="sxs-lookup"><span data-stu-id="dea46-106">measurementResults : __invalid<Result>__[]</span></span>




### <a name="resultsvalues--__invalidresult__"></a><span data-ttu-id="dea46-107">resultsValues: __nieprawidłowy <Result>__[]</span><span class="sxs-lookup"><span data-stu-id="dea46-107">resultsValues : __invalid<Result>__[]</span></span>




### <a name="onequalop--unit--unit--is-ctl"></a><span data-ttu-id="dea46-108">onEqualOp: [](xref:microsoft.quantum.lang-ref.unit) => [Jednostka](xref:microsoft.quantum.lang-ref.unit) jednostki jest listą CTL</span><span class="sxs-lookup"><span data-stu-id="dea46-108">onEqualOp : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>




### <a name="onnonequalop--unit--unit--is-ctl"></a><span data-ttu-id="dea46-109">onNonEqualOp: [](xref:microsoft.quantum.lang-ref.unit) => [Jednostka](xref:microsoft.quantum.lang-ref.unit) jednostki jest listą CTL</span><span class="sxs-lookup"><span data-stu-id="dea46-109">onNonEqualOp : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>





## <a name="output--unit"></a><span data-ttu-id="dea46-110">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="dea46-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

