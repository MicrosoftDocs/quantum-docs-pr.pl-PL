---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionallyC
title: ApplyConditionallyC, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionallyC
qsharp.summary: ''
ms.openlocfilehash: 09496d384a70fa9fb6826304ce9909034297a118
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847849"
---
# <a name="applyconditionallyc-operation"></a><span data-ttu-id="7008b-102">ApplyConditionallyC, operacja</span><span class="sxs-lookup"><span data-stu-id="7008b-102">ApplyConditionallyC operation</span></span>

<span data-ttu-id="7008b-103">Przestrzeń nazw: [Microsoft. Quantum. Symulacja. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="7008b-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="7008b-104">Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="7008b-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyConditionallyC<'T, 'U> (measurementResults : Result[], resultsValues : Result[], (onEqualOp : ('T => Unit is Ctl), equalArg : 'T), (onNonEqualOp : ('U => Unit is Ctl), nonEqualArg : 'U)) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="7008b-105">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="7008b-105">Input</span></span>

### <a name="measurementresults--__invalidresult__"></a><span data-ttu-id="7008b-106">measurementResults: __nieprawidłowy <Result>__[]</span><span class="sxs-lookup"><span data-stu-id="7008b-106">measurementResults : __invalid<Result>__[]</span></span>




### <a name="resultsvalues--__invalidresult__"></a><span data-ttu-id="7008b-107">resultsValues: __nieprawidłowy <Result>__[]</span><span class="sxs-lookup"><span data-stu-id="7008b-107">resultsValues : __invalid<Result>__[]</span></span>




### <a name="onequalop--t--unit--is-ctl"></a><span data-ttu-id="7008b-108">onEqualOp: t = [jednostka](xref:microsoft.quantum.lang-ref.unit) > jest listą CTL</span><span class="sxs-lookup"><span data-stu-id="7008b-108">onEqualOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>




### <a name="equalarg--t"></a><span data-ttu-id="7008b-109">equalArg: 'T</span><span class="sxs-lookup"><span data-stu-id="7008b-109">equalArg : 'T</span></span>




### <a name="onnonequalop--u--unit--is-ctl"></a><span data-ttu-id="7008b-110">onNonEqualOp: "U = [jednostka](xref:microsoft.quantum.lang-ref.unit) > jest listą CTL</span><span class="sxs-lookup"><span data-stu-id="7008b-110">onNonEqualOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>




### <a name="nonequalarg--u"></a><span data-ttu-id="7008b-111">nonEqualArg: ' U</span><span class="sxs-lookup"><span data-stu-id="7008b-111">nonEqualArg : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="7008b-112">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7008b-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="7008b-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="7008b-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7008b-114">'C</span><span class="sxs-lookup"><span data-stu-id="7008b-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="7008b-115">' U</span><span class="sxs-lookup"><span data-stu-id="7008b-115">'U</span></span>

