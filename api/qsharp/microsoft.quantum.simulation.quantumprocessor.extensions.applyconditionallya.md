---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionallyA
title: ApplyConditionallyA, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionallyA
qsharp.summary: ''
ms.openlocfilehash: b6f7e7d6d51e531b0ec9e7e4f2f5772038421933
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92710528"
---
# <a name="applyconditionallya-operation"></a><span data-ttu-id="95504-102">ApplyConditionallyA, operacja</span><span class="sxs-lookup"><span data-stu-id="95504-102">ApplyConditionallyA operation</span></span>

<span data-ttu-id="95504-103">Przestrzeń nazw: [Microsoft. Quantum. Symulacja. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="95504-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="95504-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="95504-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyConditionallyA<'T, 'U> (measurementResults : Result[], resultsValues : Result[], (onEqualOp : ('T => Unit is Adj), equalArg : 'T), (onNonEqualOp : ('U => Unit is Adj), nonEqualArg : 'U)) : Unit
```


## <a name="input"></a><span data-ttu-id="95504-105">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="95504-105">Input</span></span>

### <a name="measurementresults--__invalidresult__"></a><span data-ttu-id="95504-106">measurementResults: __nieprawidłowy <Result>__ []</span><span class="sxs-lookup"><span data-stu-id="95504-106">measurementResults : __invalid<Result>__ []</span></span>




### <a name="resultsvalues--__invalidresult__"></a><span data-ttu-id="95504-107">resultsValues: __nieprawidłowy <Result>__ []</span><span class="sxs-lookup"><span data-stu-id="95504-107">resultsValues : __invalid<Result>__ []</span></span>




### <a name="onequalop--t--unit-adj"></a><span data-ttu-id="95504-108">onEqualOp: 'T => korekta [jednostki](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="95504-108">onEqualOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>




### <a name="equalarg--t"></a><span data-ttu-id="95504-109">equalArg: 'T</span><span class="sxs-lookup"><span data-stu-id="95504-109">equalArg : 'T</span></span>




### <a name="onnonequalop--u--unit-adj"></a><span data-ttu-id="95504-110">onNonEqualOp: ' U => korekta [jednostki](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="95504-110">onNonEqualOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>




### <a name="nonequalarg--u"></a><span data-ttu-id="95504-111">nonEqualArg: ' U</span><span class="sxs-lookup"><span data-stu-id="95504-111">nonEqualArg : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="95504-112">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="95504-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="95504-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="95504-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="95504-114">'C</span><span class="sxs-lookup"><span data-stu-id="95504-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="95504-115">' U</span><span class="sxs-lookup"><span data-stu-id="95504-115">'U</span></span>

