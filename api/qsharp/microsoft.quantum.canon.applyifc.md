---
uid: Microsoft.Quantum.Canon.ApplyIfC
title: ApplyIfC, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfC
qsharp.summary: Applies a controllable operation conditioned on a classical bit.
ms.openlocfilehash: ef16b23349b604d174e72d9ae06d2052e2ab60f8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841859"
---
# <a name="applyifc-operation"></a><span data-ttu-id="484f5-102">ApplyIfC, operacja</span><span class="sxs-lookup"><span data-stu-id="484f5-102">ApplyIfC operation</span></span>

<span data-ttu-id="484f5-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="484f5-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="484f5-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="484f5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="484f5-105">Stosuje operację z możliwością kontrolowania dla klasycznego bitu.</span><span class="sxs-lookup"><span data-stu-id="484f5-105">Applies a controllable operation conditioned on a classical bit.</span></span>

```qsharp
operation ApplyIfC<'T> (op : ('T => Unit is Ctl), bit : Bool, target : 'T) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="484f5-106">Opis</span><span class="sxs-lookup"><span data-stu-id="484f5-106">Description</span></span>

<span data-ttu-id="484f5-107">Dana operacja `op` i wartość bitowa `bit` mają zastosowanie do elementu `op` `target` if `bit` is `true` .</span><span class="sxs-lookup"><span data-stu-id="484f5-107">Given an operation `op` and a bit value `bit`, applies `op` to the `target` if `bit` is `true`.</span></span> <span data-ttu-id="484f5-108">Jeśli `false` nie, nic się nie dzieje z `target` .</span><span class="sxs-lookup"><span data-stu-id="484f5-108">If `false`, nothing happens to the `target`.</span></span>
<span data-ttu-id="484f5-109">Sufiks `C` wskazuje, że operacja do zastosowania jest sterowana.</span><span class="sxs-lookup"><span data-stu-id="484f5-109">The suffix `C` indicates that the operation to be applied is controllable.</span></span>

## <a name="input"></a><span data-ttu-id="484f5-110">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="484f5-110">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="484f5-111">op: t = [jednostka](xref:microsoft.quantum.lang-ref.unit) > jest listą CTL</span><span class="sxs-lookup"><span data-stu-id="484f5-111">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="484f5-112">Operacja, która ma być stosowana warunkowo.</span><span class="sxs-lookup"><span data-stu-id="484f5-112">An operation to be conditionally applied.</span></span>


### <a name="bit--bool"></a><span data-ttu-id="484f5-113">bit: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="484f5-113">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="484f5-114">wartość logiczna, która kontroluje, czy operacja jest stosowana, czy nie.</span><span class="sxs-lookup"><span data-stu-id="484f5-114">a boolean that controls whether op is applied or not.</span></span>


### <a name="target--t"></a><span data-ttu-id="484f5-115">element docelowy: 'T</span><span class="sxs-lookup"><span data-stu-id="484f5-115">target : 'T</span></span>

<span data-ttu-id="484f5-116">Dane wejściowe, do których zostanie zastosowana operacja.</span><span class="sxs-lookup"><span data-stu-id="484f5-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="484f5-117">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="484f5-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="484f5-118">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="484f5-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="484f5-119">'C</span><span class="sxs-lookup"><span data-stu-id="484f5-119">'T</span></span>

<span data-ttu-id="484f5-120">Typ wejściowy operacji, która ma być stosowana warunkowo.</span><span class="sxs-lookup"><span data-stu-id="484f5-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="example"></a><span data-ttu-id="484f5-121">Przykład</span><span class="sxs-lookup"><span data-stu-id="484f5-121">Example</span></span>

<span data-ttu-id="484f5-122">Poniżej przygotowuje się rejestr qubits do stanu podstawy obliczeniowej reprezentowanego przez klasyczny ciąg bitowy wyrażony jako tablica `Bool` wartości:</span><span class="sxs-lookup"><span data-stu-id="484f5-122">The following prepares a register of qubits into a computational basis state represented by a classical bit string given as an array of `Bool` values:</span></span>

```qsharp
let bitstring = [true, false, true];
using (register = Qubit(3)) {
    ApplyToEach(ApplyIf(X, _, _), Zipped(bitstring, register));
    // register should now be in the state |101⟩.
    ...
}
```

## <a name="see-also"></a><span data-ttu-id="484f5-123">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="484f5-123">See Also</span></span>

- [<span data-ttu-id="484f5-124">Microsoft. Quantum. Canon. ApplyIfC</span><span class="sxs-lookup"><span data-stu-id="484f5-124">Microsoft.Quantum.Canon.ApplyIfC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [<span data-ttu-id="484f5-125">Microsoft. Quantum. Canon. ApplyIfA</span><span class="sxs-lookup"><span data-stu-id="484f5-125">Microsoft.Quantum.Canon.ApplyIfA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [<span data-ttu-id="484f5-126">Microsoft. Quantum. Canon. ApplyIfCA</span><span class="sxs-lookup"><span data-stu-id="484f5-126">Microsoft.Quantum.Canon.ApplyIfCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfCA)