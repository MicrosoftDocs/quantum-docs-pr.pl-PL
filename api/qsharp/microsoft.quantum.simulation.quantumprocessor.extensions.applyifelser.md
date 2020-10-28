---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfElseR
title: ApplyIfElseR, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfElseR
qsharp.summary: ''
ms.openlocfilehash: ca9db334bb62e043933f99e405612957831efdcb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724770"
---
# <a name="applyifelser-operation"></a><span data-ttu-id="f99cb-102">ApplyIfElseR, operacja</span><span class="sxs-lookup"><span data-stu-id="f99cb-102">ApplyIfElseR operation</span></span>

<span data-ttu-id="f99cb-103">Przestrzeń nazw: [Microsoft. Quantum. Symulacja. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="f99cb-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="f99cb-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f99cb-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyIfElseR<'T, 'U> (measurementResult : Result, (onResultZeroOp : ('T => Unit), zeroArg : 'T), (onResultOneOp : ('U => Unit), oneArg : 'U)) : Unit
```


## <a name="input"></a><span data-ttu-id="f99cb-105">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="f99cb-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="f99cb-106">measurementResult: __nieprawidłowy <Result>__</span><span class="sxs-lookup"><span data-stu-id="f99cb-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--t--unit"></a><span data-ttu-id="f99cb-107">onResultZeroOp: 'T = [jednostka](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="f99cb-107">onResultZeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="zeroarg--t"></a><span data-ttu-id="f99cb-108">zeroArg: 'T</span><span class="sxs-lookup"><span data-stu-id="f99cb-108">zeroArg : 'T</span></span>




### <a name="onresultoneop--u--unit"></a><span data-ttu-id="f99cb-109">onResultOneOp: ' U = [jednostka](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="f99cb-109">onResultOneOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="onearg--u"></a><span data-ttu-id="f99cb-110">oneArg: ' U</span><span class="sxs-lookup"><span data-stu-id="f99cb-110">oneArg : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="f99cb-111">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f99cb-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="f99cb-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="f99cb-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f99cb-113">'C</span><span class="sxs-lookup"><span data-stu-id="f99cb-113">'T</span></span>


### <a name="u"></a><span data-ttu-id="f99cb-114">' U</span><span class="sxs-lookup"><span data-stu-id="f99cb-114">'U</span></span>

