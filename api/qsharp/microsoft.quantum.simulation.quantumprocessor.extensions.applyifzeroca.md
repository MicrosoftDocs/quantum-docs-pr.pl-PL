---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfZeroCA
title: ApplyIfZeroCA, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfZeroCA
qsharp.summary: ''
ms.openlocfilehash: accc3ca9c0d99c48c713333ce1cc907054c2a860
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230790"
---
# <a name="applyifzeroca-operation"></a><span data-ttu-id="bab74-102">ApplyIfZeroCA, operacja</span><span class="sxs-lookup"><span data-stu-id="bab74-102">ApplyIfZeroCA operation</span></span>

<span data-ttu-id="bab74-103">Przestrzeń nazw: [Microsoft. Quantum. Symulacja. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="bab74-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="bab74-104">Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="bab74-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyIfZeroCA<'T> (measurementResult : Result, (onResultZeroOp : ('T => Unit is Ctl + Adj), zeroArg : 'T)) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="bab74-105">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="bab74-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="bab74-106">measurementResult: __nieprawidłowy <Result>__</span><span class="sxs-lookup"><span data-stu-id="bab74-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--t--unit--is-adj--ctl"></a><span data-ttu-id="bab74-107">onResultZeroOp: t = [jednostka](xref:microsoft.quantum.lang-ref.unit) > jest korektą i listą CTL</span><span class="sxs-lookup"><span data-stu-id="bab74-107">onResultZeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>




### <a name="zeroarg--t"></a><span data-ttu-id="bab74-108">zeroArg: 'T</span><span class="sxs-lookup"><span data-stu-id="bab74-108">zeroArg : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="bab74-109">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bab74-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="bab74-110">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="bab74-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="bab74-111">'C</span><span class="sxs-lookup"><span data-stu-id="bab74-111">'T</span></span>

