---
uid: Microsoft.Quantum.Canon.ApplyControlledOnInt
title: ApplyControlledOnInt, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyControlledOnInt
qsharp.summary: Applies a unitary operation on the target register if the control register state corresponds to a specified positive integer.
ms.openlocfilehash: 499a25104742b2d03886065baad4d535ea92e83b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845095"
---
# <a name="applycontrolledonint-operation"></a><span data-ttu-id="01b54-102">ApplyControlledOnInt, operacja</span><span class="sxs-lookup"><span data-stu-id="01b54-102">ApplyControlledOnInt operation</span></span>

<span data-ttu-id="01b54-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="01b54-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="01b54-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="01b54-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="01b54-105">Stosuje operacje jednostkowe w rejestrze docelowym, jeśli stan rejestru kontroli odpowiada określonej dodatniej liczbie całkowitej.</span><span class="sxs-lookup"><span data-stu-id="01b54-105">Applies a unitary operation on the target register if the control register state corresponds to a specified positive integer.</span></span>

```qsharp
operation ApplyControlledOnInt<'T> (numberState : Int, oracle : ('T => Unit is Adj + Ctl), controlRegister : Qubit[], targetRegister : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="01b54-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="01b54-106">Input</span></span>

### <a name="numberstate--int"></a><span data-ttu-id="01b54-107">numberState: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="01b54-107">numberState : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="01b54-108">Nieujemna liczba całkowita, w której `oracle` powinna być kontrolowana operacja.</span><span class="sxs-lookup"><span data-stu-id="01b54-108">A nonnegative integer on which the operation `oracle` should be controlled.</span></span>


### <a name="oracle--t--unit--is-adj--ctl"></a><span data-ttu-id="01b54-109">Oracle: t = [jednostka](xref:microsoft.quantum.lang-ref.unit) > jest korektą i listą CTL</span><span class="sxs-lookup"><span data-stu-id="01b54-109">oracle : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="01b54-110">Operacja jednostkowa, która ma być kontrolowana.</span><span class="sxs-lookup"><span data-stu-id="01b54-110">A unitary operation to be controlled.</span></span>


### <a name="controlregister--qubit"></a><span data-ttu-id="01b54-111">controlRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="01b54-111">controlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="01b54-112">Rejestr Quantum kontrolujący aplikację `oracle` .</span><span class="sxs-lookup"><span data-stu-id="01b54-112">A quantum register that controls application of `oracle`.</span></span>


### <a name="targetregister--t"></a><span data-ttu-id="01b54-113">targetRegister: 'T</span><span class="sxs-lookup"><span data-stu-id="01b54-113">targetRegister : 'T</span></span>

<span data-ttu-id="01b54-114">Rejestr, który ma zostać zastosowany `oracle` .</span><span class="sxs-lookup"><span data-stu-id="01b54-114">A register on which to apply `oracle`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="01b54-115">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="01b54-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="01b54-116">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="01b54-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="01b54-117">'C</span><span class="sxs-lookup"><span data-stu-id="01b54-117">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="01b54-118">Uwagi</span><span class="sxs-lookup"><span data-stu-id="01b54-118">Remarks</span></span>

<span data-ttu-id="01b54-119">Wartość `numberState` jest interpretowana przy użyciu kodowania little-endian.</span><span class="sxs-lookup"><span data-stu-id="01b54-119">The value of `numberState` is interpreted using a little-endian encoding.</span></span>

<span data-ttu-id="01b54-120">`numberState` musi mieć co najwyżej $2 ^ \texttt{Length (controlRegister)}-$1.</span><span class="sxs-lookup"><span data-stu-id="01b54-120">`numberState` must be at most $2^\texttt{Length(controlRegister)} - 1$.</span></span>
<span data-ttu-id="01b54-121">Na przykład `numberState = 537` oznacza, że `oracle` jest stosowana, jeśli `controlRegister` jest w stanie $ \ket {537} $.</span><span class="sxs-lookup"><span data-stu-id="01b54-121">For example, `numberState = 537` means that `oracle` is applied if and only if `controlRegister` is in the state $\ket{537}$.</span></span>