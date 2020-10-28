---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfZeroC
title: ApplyIfZeroC, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfZeroC
qsharp.summary: ''
ms.openlocfilehash: 6de4fcf86495136f2caec6fb6f873a18d751c977
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725689"
---
# <a name="applyifzeroc-operation"></a><span data-ttu-id="f2692-102">ApplyIfZeroC, operacja</span><span class="sxs-lookup"><span data-stu-id="f2692-102">ApplyIfZeroC operation</span></span>

<span data-ttu-id="f2692-103">Przestrzeń nazw: [Microsoft. Quantum. Symulacja. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="f2692-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="f2692-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f2692-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyIfZeroC<'T> (measurementResult : Result, (onResultZeroOp : ('T => Unit is Ctl), zeroArg : 'T)) : Unit
```


## <a name="input"></a><span data-ttu-id="f2692-105">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="f2692-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="f2692-106">measurementResult: __nieprawidłowy <Result>__</span><span class="sxs-lookup"><span data-stu-id="f2692-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--t--unit-ctl"></a><span data-ttu-id="f2692-107">onResultZeroOp: t => [jednostki](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="f2692-107">onResultZeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>




### <a name="zeroarg--t"></a><span data-ttu-id="f2692-108">zeroArg: 'T</span><span class="sxs-lookup"><span data-stu-id="f2692-108">zeroArg : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="f2692-109">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f2692-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="f2692-110">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="f2692-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f2692-111">'C</span><span class="sxs-lookup"><span data-stu-id="f2692-111">'T</span></span>

