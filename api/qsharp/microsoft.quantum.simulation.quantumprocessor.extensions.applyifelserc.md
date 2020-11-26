---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfElseRC
title: ApplyIfElseRC, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfElseRC
qsharp.summary: ''
ms.openlocfilehash: 33b3adfca87410480108eafd090632006117f7b2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192642"
---
# <a name="applyifelserc-operation"></a><span data-ttu-id="03d24-102">ApplyIfElseRC, operacja</span><span class="sxs-lookup"><span data-stu-id="03d24-102">ApplyIfElseRC operation</span></span>

<span data-ttu-id="03d24-103">Przestrzeń nazw: [Microsoft. Quantum. Symulacja. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="03d24-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="03d24-104">Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="03d24-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyIfElseRC<'T, 'U> (measurementResult : Result, (onResultZeroOp : ('T => Unit is Ctl), zeroArg : 'T), (onResultOneOp : ('U => Unit is Ctl), oneArg : 'U)) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="03d24-105">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="03d24-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="03d24-106">measurementResult: __nieprawidłowy <Result>__</span><span class="sxs-lookup"><span data-stu-id="03d24-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--t--unit--is-ctl"></a><span data-ttu-id="03d24-107">onResultZeroOp: t = [jednostka](xref:microsoft.quantum.lang-ref.unit) > jest listą CTL</span><span class="sxs-lookup"><span data-stu-id="03d24-107">onResultZeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>




### <a name="zeroarg--t"></a><span data-ttu-id="03d24-108">zeroArg: 'T</span><span class="sxs-lookup"><span data-stu-id="03d24-108">zeroArg : 'T</span></span>




### <a name="onresultoneop--u--unit--is-ctl"></a><span data-ttu-id="03d24-109">onResultOneOp: "U = [jednostka](xref:microsoft.quantum.lang-ref.unit) > jest listą CTL</span><span class="sxs-lookup"><span data-stu-id="03d24-109">onResultOneOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>




### <a name="onearg--u"></a><span data-ttu-id="03d24-110">oneArg: ' U</span><span class="sxs-lookup"><span data-stu-id="03d24-110">oneArg : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="03d24-111">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="03d24-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="03d24-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="03d24-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="03d24-113">'C</span><span class="sxs-lookup"><span data-stu-id="03d24-113">'T</span></span>


### <a name="u"></a><span data-ttu-id="03d24-114">' U</span><span class="sxs-lookup"><span data-stu-id="03d24-114">'U</span></span>

