---
uid: Microsoft.Quantum.Measurement.SetToBasisState
title: SetToBasisState, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: SetToBasisState
qsharp.summary: Sets a qubit to a given computational basis state by measuring the qubit and applying a bit flip if needed.
ms.openlocfilehash: 2612bfe488c830abd835be89b2f8ea6795abf675
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194155"
---
# <a name="settobasisstate-operation"></a><span data-ttu-id="e6a57-102">SetToBasisState, operacja</span><span class="sxs-lookup"><span data-stu-id="e6a57-102">SetToBasisState operation</span></span>

<span data-ttu-id="e6a57-103">Przestrzeń nazw: [Microsoft. Quantum. Pomiar](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="e6a57-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="e6a57-104">Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="e6a57-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="e6a57-105">Ustawia qubit do danego stanu podstaw obliczeniowych przez zmierzenie qubit i zastosowanie bitowego przerzucania w razie potrzeby.</span><span class="sxs-lookup"><span data-stu-id="e6a57-105">Sets a qubit to a given computational basis state by measuring the qubit and applying a bit flip if needed.</span></span>

```qsharp
operation SetToBasisState (desired : Result, target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="e6a57-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="e6a57-106">Input</span></span>

### <a name="desired--__invalidresult__"></a><span data-ttu-id="e6a57-107">pożądane __: <Result> nieprawidłowe__</span><span class="sxs-lookup"><span data-stu-id="e6a57-107">desired : __invalid<Result>__</span></span>

<span data-ttu-id="e6a57-108">Stan bazowy, do którego należy ustawić qubit.</span><span class="sxs-lookup"><span data-stu-id="e6a57-108">The basis state that the qubit should be set to.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="e6a57-109">obiekt docelowy: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="e6a57-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="e6a57-110">Qubit, którego stan ma być ustawiony.</span><span class="sxs-lookup"><span data-stu-id="e6a57-110">The qubit whose state is to be set.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e6a57-111">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e6a57-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="e6a57-112">Uwagi</span><span class="sxs-lookup"><span data-stu-id="e6a57-112">Remarks</span></span>

<span data-ttu-id="e6a57-113">Jako niezmienna tej operacji wywoływanie `M(q)` natychmiast po `SetToBasisState(result, q)` powrocie zostanie zwrócone `result` .</span><span class="sxs-lookup"><span data-stu-id="e6a57-113">As an invariant of this operation, calling `M(q)` immediately after `SetToBasisState(result, q)` will return `result`.</span></span>