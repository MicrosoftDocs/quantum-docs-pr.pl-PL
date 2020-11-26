---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionallyCA
title: ApplyConditionallyCA, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionallyCA
qsharp.summary: ''
ms.openlocfilehash: 18db01f8e5e00c2f115b8ffe73c0f8eea275beb0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230246"
---
# <a name="applyconditionallyca-operation"></a><span data-ttu-id="56962-102">ApplyConditionallyCA, operacja</span><span class="sxs-lookup"><span data-stu-id="56962-102">ApplyConditionallyCA operation</span></span>

<span data-ttu-id="56962-103">Przestrzeń nazw: [Microsoft. Quantum. Symulacja. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="56962-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="56962-104">Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="56962-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyConditionallyCA<'T, 'U> (measurementResults : Result[], resultsValues : Result[], (onEqualOp : ('T => Unit is Ctl + Adj), equalArg : 'T), (onNonEqualOp : ('U => Unit is Ctl + Adj), nonEqualArg : 'U)) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="56962-105">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="56962-105">Input</span></span>

### <a name="measurementresults--__invalidresult__"></a><span data-ttu-id="56962-106">measurementResults: __nieprawidłowy <Result>__[]</span><span class="sxs-lookup"><span data-stu-id="56962-106">measurementResults : __invalid<Result>__[]</span></span>




### <a name="resultsvalues--__invalidresult__"></a><span data-ttu-id="56962-107">resultsValues: __nieprawidłowy <Result>__[]</span><span class="sxs-lookup"><span data-stu-id="56962-107">resultsValues : __invalid<Result>__[]</span></span>




### <a name="onequalop--t--unit--is-adj--ctl"></a><span data-ttu-id="56962-108">onEqualOp: t = [jednostka](xref:microsoft.quantum.lang-ref.unit) > jest korektą i listą CTL</span><span class="sxs-lookup"><span data-stu-id="56962-108">onEqualOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>




### <a name="equalarg--t"></a><span data-ttu-id="56962-109">equalArg: 'T</span><span class="sxs-lookup"><span data-stu-id="56962-109">equalArg : 'T</span></span>




### <a name="onnonequalop--u--unit--is-adj--ctl"></a><span data-ttu-id="56962-110">onNonEqualOp: ' U = [jednostka](xref:microsoft.quantum.lang-ref.unit) > to przymiotnik + CTL</span><span class="sxs-lookup"><span data-stu-id="56962-110">onNonEqualOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>




### <a name="nonequalarg--u"></a><span data-ttu-id="56962-111">nonEqualArg: ' U</span><span class="sxs-lookup"><span data-stu-id="56962-111">nonEqualArg : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="56962-112">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="56962-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="56962-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="56962-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="56962-114">'C</span><span class="sxs-lookup"><span data-stu-id="56962-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="56962-115">' U</span><span class="sxs-lookup"><span data-stu-id="56962-115">'U</span></span>

