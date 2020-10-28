---
uid: Microsoft.Quantum.Canon.ControlledOnInt
title: ControlledOnInt, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ControlledOnInt
qsharp.summary: Returns a unitary operator that applies an oracle on the target register if the control register state corresponds to a specified positive integer.
ms.openlocfilehash: 4c48f3257f91fc50040d02cae7c2f7bdf87ea7c5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716417"
---
# <a name="controlledonint-function"></a><span data-ttu-id="17484-102">ControlledOnInt, funkcja</span><span class="sxs-lookup"><span data-stu-id="17484-102">ControlledOnInt function</span></span>

<span data-ttu-id="17484-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="17484-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="17484-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="17484-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="17484-105">Zwraca operator jednostki, który stosuje platformę Oracle w rejestrze docelowym, jeśli stan rejestru kontroli odpowiada określonej dodatniej liczbie całkowitej.</span><span class="sxs-lookup"><span data-stu-id="17484-105">Returns a unitary operator that applies an oracle on the target register if the control register state corresponds to a specified positive integer.</span></span>

```qsharp
function ControlledOnInt<'T> (numberState : Int, oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="17484-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="17484-106">Input</span></span>

### <a name="numberstate--int"></a><span data-ttu-id="17484-107">numberState: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="17484-107">numberState : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="17484-108">Dodatnia liczba całkowita.</span><span class="sxs-lookup"><span data-stu-id="17484-108">Positive integer.</span></span>


### <a name="oracle--t--unit-adj--ctl"></a><span data-ttu-id="17484-109">Oracle: 'T => skorygowania [jednostki](xref:microsoft.quantum.lang-ref.unit) + CTL</span><span class="sxs-lookup"><span data-stu-id="17484-109">oracle : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="17484-110">Operator jednostkowy.</span><span class="sxs-lookup"><span data-stu-id="17484-110">Unitary operator.</span></span>



## <a name="output--qubitt--unit-adj--ctl"></a><span data-ttu-id="17484-111">Output: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[], t) => skorygowania [jednostki](xref:microsoft.quantum.lang-ref.unit) + CTL</span><span class="sxs-lookup"><span data-stu-id="17484-111">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="17484-112">Operator jednostkowy stosowany `oracle` w rejestrze docelowym, jeśli stan rejestru kontroli odpowiada stanowi liczby `numberState` .</span><span class="sxs-lookup"><span data-stu-id="17484-112">A unitary operator that applies `oracle` on the target register if the control register state corresponds to the number state `numberState`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="17484-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="17484-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="17484-114">'C</span><span class="sxs-lookup"><span data-stu-id="17484-114">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="17484-115">Uwagi</span><span class="sxs-lookup"><span data-stu-id="17484-115">Remarks</span></span>

<span data-ttu-id="17484-116">Wartość `numberState` jest interpretowana przy użyciu kodowania little-endian.</span><span class="sxs-lookup"><span data-stu-id="17484-116">The value of `numberState` is interpreted using a little-endian encoding.</span></span>