---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfZeroA
title: ApplyIfZeroA, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfZeroA
qsharp.summary: ''
ms.openlocfilehash: d57f07beddc94d11a2143ba5d1fd975760260731
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230875"
---
# <a name="applyifzeroa-operation"></a><span data-ttu-id="1f92f-102">ApplyIfZeroA, operacja</span><span class="sxs-lookup"><span data-stu-id="1f92f-102">ApplyIfZeroA operation</span></span>

<span data-ttu-id="1f92f-103">Przestrzeń nazw: [Microsoft. Quantum. Symulacja. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="1f92f-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="1f92f-104">Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="1f92f-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyIfZeroA<'T> (measurementResult : Result, (onResultZeroOp : ('T => Unit is Adj), zeroArg : 'T)) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="1f92f-105">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="1f92f-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="1f92f-106">measurementResult: __nieprawidłowy <Result>__</span><span class="sxs-lookup"><span data-stu-id="1f92f-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--t--unit--is-adj"></a><span data-ttu-id="1f92f-107">onResultZeroOp: t = [jednostka](xref:microsoft.quantum.lang-ref.unit) > jest korektą</span><span class="sxs-lookup"><span data-stu-id="1f92f-107">onResultZeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>




### <a name="zeroarg--t"></a><span data-ttu-id="1f92f-108">zeroArg: 'T</span><span class="sxs-lookup"><span data-stu-id="1f92f-108">zeroArg : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="1f92f-109">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1f92f-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="1f92f-110">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="1f92f-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="1f92f-111">'C</span><span class="sxs-lookup"><span data-stu-id="1f92f-111">'T</span></span>

