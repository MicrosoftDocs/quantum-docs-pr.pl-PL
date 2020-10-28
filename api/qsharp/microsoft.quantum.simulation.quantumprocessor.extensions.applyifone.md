---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfOne
title: ApplyIfOne, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfOne
qsharp.summary: ''
ms.openlocfilehash: 0a844e0cd8b4faaa28037985918a4d2d187ebc1e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722040"
---
# <a name="applyifone-operation"></a><span data-ttu-id="55f04-102">ApplyIfOne, operacja</span><span class="sxs-lookup"><span data-stu-id="55f04-102">ApplyIfOne operation</span></span>

<span data-ttu-id="55f04-103">Przestrzeń nazw: [Microsoft. Quantum. Symulacja. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="55f04-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="55f04-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="55f04-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyIfOne<'T> (measurementResult : Result, (onResultOneOp : ('T => Unit), oneArg : 'T)) : Unit
```


## <a name="input"></a><span data-ttu-id="55f04-105">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="55f04-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="55f04-106">measurementResult: __nieprawidłowy <Result>__</span><span class="sxs-lookup"><span data-stu-id="55f04-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultoneop--t--unit"></a><span data-ttu-id="55f04-107">onResultOneOp: 'T = [jednostka](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="55f04-107">onResultOneOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="onearg--t"></a><span data-ttu-id="55f04-108">oneArg: 'T</span><span class="sxs-lookup"><span data-stu-id="55f04-108">oneArg : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="55f04-109">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="55f04-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="55f04-110">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="55f04-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="55f04-111">'C</span><span class="sxs-lookup"><span data-stu-id="55f04-111">'T</span></span>

