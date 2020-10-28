---
uid: Microsoft.Quantum.Measurement.SetToBasisState
title: SetToBasisState, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: SetToBasisState
qsharp.summary: Sets a qubit to a given computational basis state by measuring the qubit and applying a bit flip if needed.
ms.openlocfilehash: bb40ddcf6518a30f5d88eec21cf8e2c2d6e0bbaf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724672"
---
# <a name="settobasisstate-operation"></a><span data-ttu-id="5a98f-102">SetToBasisState, operacja</span><span class="sxs-lookup"><span data-stu-id="5a98f-102">SetToBasisState operation</span></span>

<span data-ttu-id="5a98f-103">Przestrzeń nazw: [Microsoft. Quantum. Pomiar](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="5a98f-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="5a98f-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5a98f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5a98f-105">Ustawia qubit do danego stanu podstaw obliczeniowych przez zmierzenie qubit i zastosowanie bitowego przerzucania w razie potrzeby.</span><span class="sxs-lookup"><span data-stu-id="5a98f-105">Sets a qubit to a given computational basis state by measuring the qubit and applying a bit flip if needed.</span></span>

```qsharp
operation SetToBasisState (desired : Result, target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="5a98f-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="5a98f-106">Input</span></span>

### <a name="desired--__invalidresult__"></a><span data-ttu-id="5a98f-107">pożądane __: <Result> nieprawidłowe__</span><span class="sxs-lookup"><span data-stu-id="5a98f-107">desired : __invalid<Result>__</span></span>

<span data-ttu-id="5a98f-108">Stan bazowy, do którego należy ustawić qubit.</span><span class="sxs-lookup"><span data-stu-id="5a98f-108">The basis state that the qubit should be set to.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="5a98f-109">obiekt docelowy: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="5a98f-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="5a98f-110">Qubit, którego stan ma być ustawiony.</span><span class="sxs-lookup"><span data-stu-id="5a98f-110">The qubit whose state is to be set.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5a98f-111">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5a98f-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="5a98f-112">Uwagi</span><span class="sxs-lookup"><span data-stu-id="5a98f-112">Remarks</span></span>

<span data-ttu-id="5a98f-113">Jako niezmienna tej operacji wywoływanie `M(q)` natychmiast po `SetToBasisState(result, q)` powrocie zostanie zwrócone `result` .</span><span class="sxs-lookup"><span data-stu-id="5a98f-113">As an invariant of this operation, calling `M(q)` immediately after `SetToBasisState(result, q)` will return `result`.</span></span>