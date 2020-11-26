---
uid: Microsoft.Quantum.Canon.ControlledOnBitString
title: ControlledOnBitString, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ControlledOnBitString
qsharp.summary: Returns a unitary operation that applies an oracle on the target register if the control register state corresponds to a specified bit mask.
ms.openlocfilehash: 9435406506fc99fe211f5dce628b21c18ee4f9fe
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216663"
---
# <a name="controlledonbitstring-function"></a><span data-ttu-id="74419-102">ControlledOnBitString, funkcja</span><span class="sxs-lookup"><span data-stu-id="74419-102">ControlledOnBitString function</span></span>

<span data-ttu-id="74419-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="74419-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="74419-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="74419-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="74419-105">Zwraca operację jednostkową, która stosuje platformę Oracle w rejestrze docelowym, jeśli stan rejestru kontroli odpowiada określonej masce bitów.</span><span class="sxs-lookup"><span data-stu-id="74419-105">Returns a unitary operation that applies an oracle on the target register if the control register state corresponds to a specified bit mask.</span></span>

```qsharp
function ControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)
```


## <a name="description"></a><span data-ttu-id="74419-106">Opis</span><span class="sxs-lookup"><span data-stu-id="74419-106">Description</span></span>

<span data-ttu-id="74419-107">Wynikiem tej funkcji jest operacja, która może być reprezentowana przez transformację jednostkową $U $, która \begin{align} U \ket{b_0 b_1 \cdots b_ {n-1}} \ket{\psi} = \ket{b_0 b_1 \cdots b_ {n-1}} \otimes \begin{Cases} V \ket{\psi} & \textrm{if} (b_0 b_1 \cdots b_ {n-1}) = \texttt{BITS} \\ \\ \ket{\psi} & \textrm{Otherwise} \end{cases}, \end{align}, gdzie $V $ to transformacja jednostkowa, która reprezentuje akcję `oracle` operacji.</span><span class="sxs-lookup"><span data-stu-id="74419-107">The output of this function is an operation that can be represented by a unitary transformation $U$ such that \begin{align} U \ket{b_0 b_1 \cdots b_{n - 1}} \ket{\psi} = \ket{b_0 b_1 \cdots b_{n-1}} \otimes \begin{cases} V \ket{\psi} & \textrm{if} (b_0 b_1 \cdots b_{n - 1}) = \texttt{bits} \\\\ \ket{\psi} & \textrm{otherwise} \end{cases}, \end{align} where $V$ is a unitary transformation that represents the action of the `oracle` operation.</span></span>

## <a name="input"></a><span data-ttu-id="74419-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="74419-108">Input</span></span>

### <a name="bits--bool"></a><span data-ttu-id="74419-109">bity: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="74419-109">bits : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="74419-110">Ciąg bitowy, który kontroluje daną operację jednostkową na.</span><span class="sxs-lookup"><span data-stu-id="74419-110">The bit string to control the given unitary operation on.</span></span>


### <a name="oracle--t--unit--is-adj--ctl"></a><span data-ttu-id="74419-111">Oracle: t = [jednostka](xref:microsoft.quantum.lang-ref.unit) > jest korektą i listą CTL</span><span class="sxs-lookup"><span data-stu-id="74419-111">oracle : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="74419-112">Operacja jednostkowa do zastosowania w rejestrze docelowym.</span><span class="sxs-lookup"><span data-stu-id="74419-112">The unitary operation to be applied on the target register.</span></span>



## <a name="output--qubitt--unit--is-adj--ctl"></a><span data-ttu-id="74419-113">Output: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[], t) => [Unit](xref:microsoft.quantum.lang-ref.unit)  to przymiotnik + CTL</span><span class="sxs-lookup"><span data-stu-id="74419-113">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="74419-114">Operacja jednostkowa stosowana `oracle` w rejestrze docelowym, jeśli stan rejestru kontroli odpowiada masce bitów `bits` .</span><span class="sxs-lookup"><span data-stu-id="74419-114">A unitary operation that applies `oracle` on the target register if the control register state corresponds to the bit mask `bits`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="74419-115">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="74419-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="74419-116">'C</span><span class="sxs-lookup"><span data-stu-id="74419-116">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="74419-117">Uwagi</span><span class="sxs-lookup"><span data-stu-id="74419-117">Remarks</span></span>

<span data-ttu-id="74419-118">Wzorzec określony przez `bits` może być krótszy niż `controlRegister` , w którym to przypadku dodatkowe qubits kontroli są ignorowane (to nie jest ani kontrolowane w $ \ket {0} $ ani $ \ket {1} $).</span><span class="sxs-lookup"><span data-stu-id="74419-118">The pattern given by `bits` may be shorter than `controlRegister`, in which case additional control qubits are ignored (that is, neither controlled on $\ket{0}$ nor $\ket{1}$).</span></span>
<span data-ttu-id="74419-119">Jeśli `bits` jest dłuższa niż `controlRegister` , zostanie zgłoszony błąd.</span><span class="sxs-lookup"><span data-stu-id="74419-119">If `bits` is longer than `controlRegister`, an error is raised.</span></span>

<span data-ttu-id="74419-120">Dana tablica logiczna `bits` i operacja jednostkowa `oracle` są wynikiem operacji, która wykonuje następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="74419-120">Given a Boolean array `bits` and a unitary operation `oracle`, the output of this function is an operation that performs the following steps:</span></span>

* <span data-ttu-id="74419-121">Zastosuj `X` operację do każdego qubitu rejestru kontroli, który odnosi się do `false` elementu `bits` ;</span><span class="sxs-lookup"><span data-stu-id="74419-121">apply an `X` operation to each qubit of the control register that corresponds to `false` element of the `bits`;</span></span>
* <span data-ttu-id="74419-122">Zastosuj `Controlled oracle` do rejestrów kontrolki i celu;</span><span class="sxs-lookup"><span data-stu-id="74419-122">apply `Controlled oracle` to the control and target registers;</span></span>
* <span data-ttu-id="74419-123">Zastosuj `X` operację do każdego qubitu rejestru kontroli, który odnosi się do `false` elementu ponownie, `bits` Aby przywrócić pierwotny stan.</span><span class="sxs-lookup"><span data-stu-id="74419-123">apply an `X` operation to each qubit of the control register that corresponds to `false` element of the `bits` again to return the control register to the original state.</span></span>

<span data-ttu-id="74419-124">Dane wyjściowe `Controlled` Funktor są szczególnym przypadkiem, `ControlledOnBitString` gdzie `bits` jest równe `[true, ..., true]` .</span><span class="sxs-lookup"><span data-stu-id="74419-124">The output of the `Controlled` functor is a special case of `ControlledOnBitString` where `bits` is equal to `[true, ..., true]`.</span></span>