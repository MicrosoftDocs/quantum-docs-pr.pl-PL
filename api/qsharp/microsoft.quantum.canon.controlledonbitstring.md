---
uid: Microsoft.Quantum.Canon.ControlledOnBitString
title: ControlledOnBitString, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ControlledOnBitString
qsharp.summary: Returns a unitary operation that applies an oracle on the target register if the control register state corresponds to a specified bit mask.
ms.openlocfilehash: 176170cc972ca67b812b84f79cf97ba5418be9b6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840805"
---
# <a name="controlledonbitstring-function"></a><span data-ttu-id="6a1f4-102">ControlledOnBitString, funkcja</span><span class="sxs-lookup"><span data-stu-id="6a1f4-102">ControlledOnBitString function</span></span>

<span data-ttu-id="6a1f4-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="6a1f4-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="6a1f4-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6a1f4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6a1f4-105">Zwraca operację jednostkową, która stosuje platformę Oracle w rejestrze docelowym, jeśli stan rejestru kontroli odpowiada określonej masce bitów.</span><span class="sxs-lookup"><span data-stu-id="6a1f4-105">Returns a unitary operation that applies an oracle on the target register if the control register state corresponds to a specified bit mask.</span></span>

```qsharp
function ControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)
```


## <a name="description"></a><span data-ttu-id="6a1f4-106">Opis</span><span class="sxs-lookup"><span data-stu-id="6a1f4-106">Description</span></span>

<span data-ttu-id="6a1f4-107">Wynikiem tej funkcji jest operacja, która może być reprezentowana przez transformację jednostkową $U $, która \begin{align} U \ket{b_0 b_1 \cdots b_ {n-1}} \ket{\psi} = \ket{b_0 b_1 \cdots b_ {n-1}} \otimes \begin{Cases} V \ket{\psi} & \textrm{if} (b_0 b_1 \cdots b_ {n-1}) = \texttt{BITS} \\ \\ \ket{\psi} & \textrm{Otherwise} \end{cases}, \end{align}, gdzie $V $ to transformacja jednostkowa, która reprezentuje akcję `oracle` operacji.</span><span class="sxs-lookup"><span data-stu-id="6a1f4-107">The output of this function is an operation that can be represented by a unitary transformation $U$ such that \begin{align} U \ket{b_0 b_1 \cdots b_{n - 1}} \ket{\psi} = \ket{b_0 b_1 \cdots b_{n-1}} \otimes \begin{cases} V \ket{\psi} & \textrm{if} (b_0 b_1 \cdots b_{n - 1}) = \texttt{bits} \\\\ \ket{\psi} & \textrm{otherwise} \end{cases}, \end{align} where $V$ is a unitary transformation that represents the action of the `oracle` operation.</span></span>

## <a name="input"></a><span data-ttu-id="6a1f4-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="6a1f4-108">Input</span></span>

### <a name="bits--bool"></a><span data-ttu-id="6a1f4-109">bity: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="6a1f4-109">bits : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="6a1f4-110">Ciąg bitowy, który kontroluje daną operację jednostkową na.</span><span class="sxs-lookup"><span data-stu-id="6a1f4-110">The bit string to control the given unitary operation on.</span></span>


### <a name="oracle--t--unit--is-adj--ctl"></a><span data-ttu-id="6a1f4-111">Oracle: t = [jednostka](xref:microsoft.quantum.lang-ref.unit) > jest korektą i listą CTL</span><span class="sxs-lookup"><span data-stu-id="6a1f4-111">oracle : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="6a1f4-112">Operacja jednostkowa do zastosowania w rejestrze docelowym.</span><span class="sxs-lookup"><span data-stu-id="6a1f4-112">The unitary operation to be applied on the target register.</span></span>



## <a name="output--qubitt--unit--is-adj--ctl"></a><span data-ttu-id="6a1f4-113">Output: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[], t) => [Unit](xref:microsoft.quantum.lang-ref.unit)  to przymiotnik + CTL</span><span class="sxs-lookup"><span data-stu-id="6a1f4-113">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="6a1f4-114">Operacja jednostkowa stosowana `oracle` w rejestrze docelowym, jeśli stan rejestru kontroli odpowiada masce bitów `bits` .</span><span class="sxs-lookup"><span data-stu-id="6a1f4-114">A unitary operation that applies `oracle` on the target register if the control register state corresponds to the bit mask `bits`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="6a1f4-115">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="6a1f4-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6a1f4-116">'C</span><span class="sxs-lookup"><span data-stu-id="6a1f4-116">'T</span></span>



## <a name="example"></a><span data-ttu-id="6a1f4-117">Przykład</span><span class="sxs-lookup"><span data-stu-id="6a1f4-117">Example</span></span>

<span data-ttu-id="6a1f4-118">Następujące fragmenty kodu są równoważne:</span><span class="sxs-lookup"><span data-stu-id="6a1f4-118">The following code snippets are equivalent:</span></span>

```qsharp
(ControlledOnBitString(bits, oracle))(controlRegister, targetRegister);
```

<span data-ttu-id="6a1f4-119">oraz</span><span class="sxs-lookup"><span data-stu-id="6a1f4-119">and</span></span>

```qsharp
within {
    ApplyPauliFromBitString(PauliX, false, bits, controlRegister);
} apply {
    Controlled oracle(controlRegister, targetRegister);
}
```

<span data-ttu-id="6a1f4-120">Poniższy kod przygotowuje stan $ \frac {1} {2} (\ket {00} -\ket {01} + \ket {10} + \ket {11} ) $:</span><span class="sxs-lookup"><span data-stu-id="6a1f4-120">The following code prepares a state $\frac{1}{2}(\ket{00} - \ket{01} + \ket{10} + \ket{11})$:</span></span>

```qsharp
using (register = Qubit[2]) {
    ApplyToEach(H, register);
    (ControlledOnBitString([false], Z))(register[0..0], register[1]);
}
```

## <a name="remarks"></a><span data-ttu-id="6a1f4-121">Uwagi</span><span class="sxs-lookup"><span data-stu-id="6a1f4-121">Remarks</span></span>

<span data-ttu-id="6a1f4-122">Wzorzec określony przez `bits` może być krótszy niż `controlRegister` , w którym to przypadku dodatkowe qubits kontroli są ignorowane (to nie jest ani kontrolowane w $ \ket {0} $ ani $ \ket {1} $).</span><span class="sxs-lookup"><span data-stu-id="6a1f4-122">The pattern given by `bits` may be shorter than `controlRegister`, in which case additional control qubits are ignored (that is, neither controlled on $\ket{0}$ nor $\ket{1}$).</span></span>
<span data-ttu-id="6a1f4-123">Jeśli `bits` jest dłuższa niż `controlRegister` , zostanie zgłoszony błąd.</span><span class="sxs-lookup"><span data-stu-id="6a1f4-123">If `bits` is longer than `controlRegister`, an error is raised.</span></span>

<span data-ttu-id="6a1f4-124">Dana tablica logiczna `bits` i operacja jednostkowa `oracle` są wynikiem operacji, która wykonuje następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="6a1f4-124">Given a Boolean array `bits` and a unitary operation `oracle`, the output of this function is an operation that performs the following steps:</span></span>

* <span data-ttu-id="6a1f4-125">Zastosuj `X` operację do każdego qubitu rejestru kontroli, który odnosi się do `false` elementu `bits` ;</span><span class="sxs-lookup"><span data-stu-id="6a1f4-125">apply an `X` operation to each qubit of the control register that corresponds to `false` element of the `bits`;</span></span>
* <span data-ttu-id="6a1f4-126">Zastosuj `Controlled oracle` do rejestrów kontrolki i celu;</span><span class="sxs-lookup"><span data-stu-id="6a1f4-126">apply `Controlled oracle` to the control and target registers;</span></span>
* <span data-ttu-id="6a1f4-127">Zastosuj `X` operację do każdego qubitu rejestru kontroli, który odnosi się do `false` elementu ponownie, `bits` Aby przywrócić pierwotny stan.</span><span class="sxs-lookup"><span data-stu-id="6a1f4-127">apply an `X` operation to each qubit of the control register that corresponds to `false` element of the `bits` again to return the control register to the original state.</span></span>

<span data-ttu-id="6a1f4-128">Dane wyjściowe `Controlled` Funktor są szczególnym przypadkiem, `ControlledOnBitString` gdzie `bits` jest równe `[true, ..., true]` .</span><span class="sxs-lookup"><span data-stu-id="6a1f4-128">The output of the `Controlled` functor is a special case of `ControlledOnBitString` where `bits` is equal to `[true, ..., true]`.</span></span>