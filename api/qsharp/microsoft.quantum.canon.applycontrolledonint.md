---
uid: Microsoft.Quantum.Canon.ApplyControlledOnInt
title: ApplyControlledOnInt, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyControlledOnInt
qsharp.summary: Applies a unitary operation on the target register if the control register state corresponds to a specified positive integer.
ms.openlocfilehash: c8ea76946143967de4b6ac65986a1c4407ecb633
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718353"
---
# <a name="applycontrolledonint-operation"></a><span data-ttu-id="39ae6-102">ApplyControlledOnInt, operacja</span><span class="sxs-lookup"><span data-stu-id="39ae6-102">ApplyControlledOnInt operation</span></span>

<span data-ttu-id="39ae6-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="39ae6-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="39ae6-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="39ae6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="39ae6-105">Stosuje operacje jednostkowe w rejestrze docelowym, jeśli stan rejestru kontroli odpowiada określonej dodatniej liczbie całkowitej.</span><span class="sxs-lookup"><span data-stu-id="39ae6-105">Applies a unitary operation on the target register if the control register state corresponds to a specified positive integer.</span></span>

```qsharp
operation ApplyControlledOnInt<'T> (numberState : Int, oracle : ('T => Unit is Adj + Ctl), controlRegister : Qubit[], targetRegister : 'T) : Unit
```


## <a name="input"></a><span data-ttu-id="39ae6-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="39ae6-106">Input</span></span>

### <a name="numberstate--int"></a><span data-ttu-id="39ae6-107">numberState: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="39ae6-107">numberState : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="39ae6-108">Nieujemna liczba całkowita, w której `oracle` powinna być kontrolowana operacja.</span><span class="sxs-lookup"><span data-stu-id="39ae6-108">A nonnegative integer on which the operation `oracle` should be controlled.</span></span>


### <a name="oracle--t--unit-adj--ctl"></a><span data-ttu-id="39ae6-109">Oracle: 'T => skorygowania [jednostki](xref:microsoft.quantum.lang-ref.unit) + CTL</span><span class="sxs-lookup"><span data-stu-id="39ae6-109">oracle : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="39ae6-110">Operacja jednostkowa, która ma być kontrolowana.</span><span class="sxs-lookup"><span data-stu-id="39ae6-110">A unitary operation to be controlled.</span></span>


### <a name="controlregister--qubit"></a><span data-ttu-id="39ae6-111">controlRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="39ae6-111">controlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="39ae6-112">Rejestr Quantum kontrolujący aplikację `oracle` .</span><span class="sxs-lookup"><span data-stu-id="39ae6-112">A quantum register that controls application of `oracle`.</span></span>


### <a name="targetregister--t"></a><span data-ttu-id="39ae6-113">targetRegister: 'T</span><span class="sxs-lookup"><span data-stu-id="39ae6-113">targetRegister : 'T</span></span>

<span data-ttu-id="39ae6-114">Rejestr, który ma zostać zastosowany `oracle` .</span><span class="sxs-lookup"><span data-stu-id="39ae6-114">A register on which to apply `oracle`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="39ae6-115">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="39ae6-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="39ae6-116">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="39ae6-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="39ae6-117">'C</span><span class="sxs-lookup"><span data-stu-id="39ae6-117">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="39ae6-118">Uwagi</span><span class="sxs-lookup"><span data-stu-id="39ae6-118">Remarks</span></span>

<span data-ttu-id="39ae6-119">Wartość `numberState` jest interpretowana przy użyciu kodowania little-endian.</span><span class="sxs-lookup"><span data-stu-id="39ae6-119">The value of `numberState` is interpreted using a little-endian encoding.</span></span>

<span data-ttu-id="39ae6-120">`numberState` musi mieć co najwyżej $2 ^ \texttt{Length (controlRegister)}-$1.</span><span class="sxs-lookup"><span data-stu-id="39ae6-120">`numberState` must be at most $2^\texttt{Length(controlRegister)} - 1$.</span></span>
<span data-ttu-id="39ae6-121">Na przykład `numberState = 537` oznacza, że `oracle` jest stosowana, jeśli `controlRegister` jest w stanie $ \ket {537} $.</span><span class="sxs-lookup"><span data-stu-id="39ae6-121">For example, `numberState = 537` means that `oracle` is applied if and only if `controlRegister` is in the state $\ket{537}$.</span></span>