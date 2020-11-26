---
uid: Microsoft.Quantum.Canon.ControlledOnInt
title: ControlledOnInt, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ControlledOnInt
qsharp.summary: Returns a unitary operator that applies an oracle on the target register if the control register state corresponds to a specified positive integer.
ms.openlocfilehash: 3cc5c00d9c7295106901149e06571ef1963d1323
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207262"
---
# <a name="controlledonint-function"></a><span data-ttu-id="63e0c-102">ControlledOnInt, funkcja</span><span class="sxs-lookup"><span data-stu-id="63e0c-102">ControlledOnInt function</span></span>

<span data-ttu-id="63e0c-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="63e0c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="63e0c-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="63e0c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="63e0c-105">Zwraca operator jednostki, który stosuje platformę Oracle w rejestrze docelowym, jeśli stan rejestru kontroli odpowiada określonej dodatniej liczbie całkowitej.</span><span class="sxs-lookup"><span data-stu-id="63e0c-105">Returns a unitary operator that applies an oracle on the target register if the control register state corresponds to a specified positive integer.</span></span>

```qsharp
function ControlledOnInt<'T> (numberState : Int, oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="63e0c-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="63e0c-106">Input</span></span>

### <a name="numberstate--int"></a><span data-ttu-id="63e0c-107">numberState: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="63e0c-107">numberState : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="63e0c-108">Dodatnia liczba całkowita.</span><span class="sxs-lookup"><span data-stu-id="63e0c-108">Positive integer.</span></span>


### <a name="oracle--t--unit--is-adj--ctl"></a><span data-ttu-id="63e0c-109">Oracle: t = [jednostka](xref:microsoft.quantum.lang-ref.unit) > jest korektą i listą CTL</span><span class="sxs-lookup"><span data-stu-id="63e0c-109">oracle : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="63e0c-110">Operator jednostkowy.</span><span class="sxs-lookup"><span data-stu-id="63e0c-110">Unitary operator.</span></span>



## <a name="output--qubitt--unit--is-adj--ctl"></a><span data-ttu-id="63e0c-111">Output: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[], t) => [Unit](xref:microsoft.quantum.lang-ref.unit)  to przymiotnik + CTL</span><span class="sxs-lookup"><span data-stu-id="63e0c-111">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="63e0c-112">Operator jednostkowy stosowany `oracle` w rejestrze docelowym, jeśli stan rejestru kontroli odpowiada stanowi liczby `numberState` .</span><span class="sxs-lookup"><span data-stu-id="63e0c-112">A unitary operator that applies `oracle` on the target register if the control register state corresponds to the number state `numberState`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="63e0c-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="63e0c-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="63e0c-114">'C</span><span class="sxs-lookup"><span data-stu-id="63e0c-114">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="63e0c-115">Uwagi</span><span class="sxs-lookup"><span data-stu-id="63e0c-115">Remarks</span></span>

<span data-ttu-id="63e0c-116">Wartość `numberState` jest interpretowana przy użyciu kodowania little-endian.</span><span class="sxs-lookup"><span data-stu-id="63e0c-116">The value of `numberState` is interpreted using a little-endian encoding.</span></span>