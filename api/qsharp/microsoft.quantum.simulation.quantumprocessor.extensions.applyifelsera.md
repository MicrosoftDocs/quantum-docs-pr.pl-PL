---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfElseRA
title: ApplyIfElseRA, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfElseRA
qsharp.summary: ''
ms.openlocfilehash: bcc52c6e2b4dfc6354e12c57e19739ac021d2e8f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725414"
---
# <a name="applyifelsera-operation"></a><span data-ttu-id="0d30f-102">ApplyIfElseRA, operacja</span><span class="sxs-lookup"><span data-stu-id="0d30f-102">ApplyIfElseRA operation</span></span>

<span data-ttu-id="0d30f-103">Przestrzeń nazw: [Microsoft. Quantum. Symulacja. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="0d30f-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="0d30f-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0d30f-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyIfElseRA<'T, 'U> (measurementResult : Result, (onResultZeroOp : ('T => Unit is Adj), zeroArg : 'T), (onResultOneOp : ('U => Unit is Adj), oneArg : 'U)) : Unit
```


## <a name="input"></a><span data-ttu-id="0d30f-105">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="0d30f-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="0d30f-106">measurementResult: __nieprawidłowy <Result>__</span><span class="sxs-lookup"><span data-stu-id="0d30f-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--t--unit-adj"></a><span data-ttu-id="0d30f-107">onResultZeroOp: 'T => korekta [jednostki](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0d30f-107">onResultZeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>




### <a name="zeroarg--t"></a><span data-ttu-id="0d30f-108">zeroArg: 'T</span><span class="sxs-lookup"><span data-stu-id="0d30f-108">zeroArg : 'T</span></span>




### <a name="onresultoneop--u--unit-adj"></a><span data-ttu-id="0d30f-109">onResultOneOp: ' U => korekta [jednostki](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0d30f-109">onResultOneOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>




### <a name="onearg--u"></a><span data-ttu-id="0d30f-110">oneArg: ' U</span><span class="sxs-lookup"><span data-stu-id="0d30f-110">oneArg : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="0d30f-111">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0d30f-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="0d30f-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="0d30f-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="0d30f-113">'C</span><span class="sxs-lookup"><span data-stu-id="0d30f-113">'T</span></span>


### <a name="u"></a><span data-ttu-id="0d30f-114">' U</span><span class="sxs-lookup"><span data-stu-id="0d30f-114">'U</span></span>

