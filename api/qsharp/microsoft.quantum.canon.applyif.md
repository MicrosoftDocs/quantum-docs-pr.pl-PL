---
uid: Microsoft.Quantum.Canon.ApplyIf
title: ApplyIf, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIf
qsharp.summary: Applies an operation conditioned on a classical bit.
ms.openlocfilehash: 109a5c4748d183f199e420b4b1aef687613d220c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841867"
---
# <a name="applyif-operation"></a><span data-ttu-id="3fade-102">ApplyIf, operacja</span><span class="sxs-lookup"><span data-stu-id="3fade-102">ApplyIf operation</span></span>

<span data-ttu-id="3fade-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="3fade-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="3fade-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3fade-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3fade-105">Stosuje operację warunkową przy użyciu klasycznego bitu.</span><span class="sxs-lookup"><span data-stu-id="3fade-105">Applies an operation conditioned on a classical bit.</span></span>

```qsharp
operation ApplyIf<'T> (op : ('T => Unit), bit : Bool, target : 'T) : Unit
```


## <a name="description"></a><span data-ttu-id="3fade-106">Opis</span><span class="sxs-lookup"><span data-stu-id="3fade-106">Description</span></span>

<span data-ttu-id="3fade-107">Dana operacja `op` i wartość bitowa `bit` mają zastosowanie do elementu `op` `target` if `bit` is `true` .</span><span class="sxs-lookup"><span data-stu-id="3fade-107">Given an operation `op` and a bit value `bit`, applies `op` to the `target` if `bit` is `true`.</span></span> <span data-ttu-id="3fade-108">Jeśli `false` nie, nic się nie dzieje z `target` .</span><span class="sxs-lookup"><span data-stu-id="3fade-108">If `false`, nothing happens to the `target`.</span></span>

## <a name="input"></a><span data-ttu-id="3fade-109">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="3fade-109">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="3fade-110">op: 'T = [jednostka](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="3fade-110">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="3fade-111">Operacja, która ma być stosowana warunkowo.</span><span class="sxs-lookup"><span data-stu-id="3fade-111">An operation to be conditionally applied.</span></span>


### <a name="bit--bool"></a><span data-ttu-id="3fade-112">bit: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="3fade-112">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="3fade-113">wartość logiczna, która kontroluje, czy operacja jest stosowana, czy nie.</span><span class="sxs-lookup"><span data-stu-id="3fade-113">a boolean that controls whether op is applied or not.</span></span>


### <a name="target--t"></a><span data-ttu-id="3fade-114">element docelowy: 'T</span><span class="sxs-lookup"><span data-stu-id="3fade-114">target : 'T</span></span>

<span data-ttu-id="3fade-115">Dane wejściowe, do których zostanie zastosowana operacja.</span><span class="sxs-lookup"><span data-stu-id="3fade-115">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3fade-116">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3fade-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="3fade-117">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="3fade-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="3fade-118">'C</span><span class="sxs-lookup"><span data-stu-id="3fade-118">'T</span></span>

<span data-ttu-id="3fade-119">Typ wejściowy operacji, która ma być stosowana warunkowo.</span><span class="sxs-lookup"><span data-stu-id="3fade-119">The input type of the operation to be conditionally applied.</span></span>

## <a name="example"></a><span data-ttu-id="3fade-120">Przykład</span><span class="sxs-lookup"><span data-stu-id="3fade-120">Example</span></span>

<span data-ttu-id="3fade-121">Poniżej przygotowuje się rejestr qubits do stanu podstawy obliczeniowej reprezentowanego przez klasyczny ciąg bitowy wyrażony jako tablica `Bool` wartości:</span><span class="sxs-lookup"><span data-stu-id="3fade-121">The following prepares a register of qubits into a computational basis state represented by a classical bit string given as an array of `Bool` values:</span></span>

```qsharp
let bitstring = [true, false, true];
using (register = Qubit(3)) {
    ApplyToEach(ApplyIf(X, _, _), Zipped(bitstring, register));
    // register should now be in the state |101⟩.
    ...
}
```

## <a name="see-also"></a><span data-ttu-id="3fade-122">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="3fade-122">See Also</span></span>

- [<span data-ttu-id="3fade-123">Microsoft. Quantum. Canon. ApplyIfC</span><span class="sxs-lookup"><span data-stu-id="3fade-123">Microsoft.Quantum.Canon.ApplyIfC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [<span data-ttu-id="3fade-124">Microsoft. Quantum. Canon. ApplyIfA</span><span class="sxs-lookup"><span data-stu-id="3fade-124">Microsoft.Quantum.Canon.ApplyIfA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [<span data-ttu-id="3fade-125">Microsoft. Quantum. Canon. ApplyIfCA</span><span class="sxs-lookup"><span data-stu-id="3fade-125">Microsoft.Quantum.Canon.ApplyIfCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfCA)