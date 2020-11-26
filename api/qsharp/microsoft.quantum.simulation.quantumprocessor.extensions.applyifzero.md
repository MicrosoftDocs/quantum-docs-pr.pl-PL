---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfZero
title: ApplyIfZero, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfZero
qsharp.summary: ''
ms.openlocfilehash: 867e2e78ea787c2376fb2b1dcc6c72694fe08621
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230909"
---
# <a name="applyifzero-operation"></a><span data-ttu-id="afc74-102">ApplyIfZero, operacja</span><span class="sxs-lookup"><span data-stu-id="afc74-102">ApplyIfZero operation</span></span>

<span data-ttu-id="afc74-103">Przestrzeń nazw: [Microsoft. Quantum. Symulacja. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="afc74-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="afc74-104">Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="afc74-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyIfZero<'T> (measurementResult : Result, (onResultZeroOp : ('T => Unit), zeroArg : 'T)) : Unit
```


## <a name="input"></a><span data-ttu-id="afc74-105">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="afc74-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="afc74-106">measurementResult: __nieprawidłowy <Result>__</span><span class="sxs-lookup"><span data-stu-id="afc74-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--t--unit"></a><span data-ttu-id="afc74-107">onResultZeroOp: 'T = [jednostka](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="afc74-107">onResultZeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="zeroarg--t"></a><span data-ttu-id="afc74-108">zeroArg: 'T</span><span class="sxs-lookup"><span data-stu-id="afc74-108">zeroArg : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="afc74-109">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="afc74-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="afc74-110">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="afc74-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="afc74-111">'C</span><span class="sxs-lookup"><span data-stu-id="afc74-111">'T</span></span>

