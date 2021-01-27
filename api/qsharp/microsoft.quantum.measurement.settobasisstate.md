---
uid: Microsoft.Quantum.Measurement.SetToBasisState
title: SetToBasisState, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: SetToBasisState
qsharp.summary: Sets a qubit to a given computational basis state by measuring the qubit and applying a bit flip if needed.
ms.openlocfilehash: dfa054360a5e82b7ae6ec5a6d52e7d5fe566f42e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854628"
---
# <a name="settobasisstate-operation"></a><span data-ttu-id="65ceb-102">SetToBasisState, operacja</span><span class="sxs-lookup"><span data-stu-id="65ceb-102">SetToBasisState operation</span></span>

<span data-ttu-id="65ceb-103">Przestrzeń nazw: [Microsoft. Quantum. Pomiar](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="65ceb-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="65ceb-104">Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="65ceb-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="65ceb-105">Ustawia qubit do danego stanu podstaw obliczeniowych przez zmierzenie qubit i zastosowanie bitowego przerzucania w razie potrzeby.</span><span class="sxs-lookup"><span data-stu-id="65ceb-105">Sets a qubit to a given computational basis state by measuring the qubit and applying a bit flip if needed.</span></span>

```qsharp
operation SetToBasisState (desired : Result, target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="65ceb-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="65ceb-106">Input</span></span>

### <a name="desired--__invalidresult__"></a><span data-ttu-id="65ceb-107">pożądane __: <Result> nieprawidłowe__</span><span class="sxs-lookup"><span data-stu-id="65ceb-107">desired : __invalid<Result>__</span></span>

<span data-ttu-id="65ceb-108">Stan bazowy, do którego należy ustawić qubit.</span><span class="sxs-lookup"><span data-stu-id="65ceb-108">The basis state that the qubit should be set to.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="65ceb-109">obiekt docelowy: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="65ceb-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="65ceb-110">Qubit, którego stan ma być ustawiony.</span><span class="sxs-lookup"><span data-stu-id="65ceb-110">The qubit whose state is to be set.</span></span>



## <a name="output--unit"></a><span data-ttu-id="65ceb-111">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="65ceb-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="65ceb-112">Uwagi</span><span class="sxs-lookup"><span data-stu-id="65ceb-112">Remarks</span></span>

<span data-ttu-id="65ceb-113">Jako niezmienna tej operacji wywoływanie `M(q)` natychmiast po `SetToBasisState(result, q)` powrocie zostanie zwrócone `result` .</span><span class="sxs-lookup"><span data-stu-id="65ceb-113">As an invariant of this operation, calling `M(q)` immediately after `SetToBasisState(result, q)` will return `result`.</span></span>