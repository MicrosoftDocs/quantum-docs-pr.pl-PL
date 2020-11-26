---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfOneCA
title: ApplyIfOneCA, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfOneCA
qsharp.summary: ''
ms.openlocfilehash: e997cf4b20fdd2c52285191b732297ca99886c22
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230943"
---
# <a name="applyifoneca-operation"></a><span data-ttu-id="bfab9-102">ApplyIfOneCA, operacja</span><span class="sxs-lookup"><span data-stu-id="bfab9-102">ApplyIfOneCA operation</span></span>

<span data-ttu-id="bfab9-103">Przestrzeń nazw: [Microsoft. Quantum. Symulacja. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="bfab9-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="bfab9-104">Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="bfab9-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyIfOneCA<'T> (measurementResult : Result, (onResultOneOp : ('T => Unit is Ctl + Adj), oneArg : 'T)) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="bfab9-105">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="bfab9-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="bfab9-106">measurementResult: __nieprawidłowy <Result>__</span><span class="sxs-lookup"><span data-stu-id="bfab9-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultoneop--t--unit--is-adj--ctl"></a><span data-ttu-id="bfab9-107">onResultOneOp: t = [jednostka](xref:microsoft.quantum.lang-ref.unit) > jest korektą i listą CTL</span><span class="sxs-lookup"><span data-stu-id="bfab9-107">onResultOneOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>




### <a name="onearg--t"></a><span data-ttu-id="bfab9-108">oneArg: 'T</span><span class="sxs-lookup"><span data-stu-id="bfab9-108">oneArg : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="bfab9-109">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bfab9-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="bfab9-110">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="bfab9-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="bfab9-111">'C</span><span class="sxs-lookup"><span data-stu-id="bfab9-111">'T</span></span>

