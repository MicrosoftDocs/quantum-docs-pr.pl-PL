---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfElseRCA
title: ApplyIfElseRCA, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfElseRCA
qsharp.summary: ''
ms.openlocfilehash: 6fbf186575775b3ae18a41727c225fb871f8dac0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192625"
---
# <a name="applyifelserca-operation"></a><span data-ttu-id="d0246-102">ApplyIfElseRCA, operacja</span><span class="sxs-lookup"><span data-stu-id="d0246-102">ApplyIfElseRCA operation</span></span>

<span data-ttu-id="d0246-103">Przestrzeń nazw: [Microsoft. Quantum. Symulacja. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="d0246-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="d0246-104">Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="d0246-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyIfElseRCA<'T, 'U> (measurementResult : Result, (onResultZeroOp : ('T => Unit is Adj + Ctl), zeroArg : 'T), (onResultOneOp : ('U => Unit is Adj + Ctl), oneArg : 'U)) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="d0246-105">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="d0246-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="d0246-106">measurementResult: __nieprawidłowy <Result>__</span><span class="sxs-lookup"><span data-stu-id="d0246-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--t--unit--is-adj--ctl"></a><span data-ttu-id="d0246-107">onResultZeroOp: t = [jednostka](xref:microsoft.quantum.lang-ref.unit) > jest korektą i listą CTL</span><span class="sxs-lookup"><span data-stu-id="d0246-107">onResultZeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>




### <a name="zeroarg--t"></a><span data-ttu-id="d0246-108">zeroArg: 'T</span><span class="sxs-lookup"><span data-stu-id="d0246-108">zeroArg : 'T</span></span>




### <a name="onresultoneop--u--unit--is-adj--ctl"></a><span data-ttu-id="d0246-109">onResultOneOp: ' U = [jednostka](xref:microsoft.quantum.lang-ref.unit) > to przymiotnik + CTL</span><span class="sxs-lookup"><span data-stu-id="d0246-109">onResultOneOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>




### <a name="onearg--u"></a><span data-ttu-id="d0246-110">oneArg: ' U</span><span class="sxs-lookup"><span data-stu-id="d0246-110">oneArg : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="d0246-111">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d0246-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="d0246-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="d0246-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d0246-113">'C</span><span class="sxs-lookup"><span data-stu-id="d0246-113">'T</span></span>


### <a name="u"></a><span data-ttu-id="d0246-114">' U</span><span class="sxs-lookup"><span data-stu-id="d0246-114">'U</span></span>

