---
uid: Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsCA
title: ApplyToFirstTwoQubitsCA, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstTwoQubitsCA
qsharp.summary: Applies an operation to the first two qubits in the register. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: 0c5e29fbca8449f8122f2a9f988797e94e27da60
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717262"
---
# <a name="applytofirsttwoqubitsca-operation"></a><span data-ttu-id="378fd-102">ApplyToFirstTwoQubitsCA, operacja</span><span class="sxs-lookup"><span data-stu-id="378fd-102">ApplyToFirstTwoQubitsCA operation</span></span>

<span data-ttu-id="378fd-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="378fd-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="378fd-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="378fd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="378fd-105">Stosuje operację do pierwszych dwóch qubits w rejestrze.</span><span class="sxs-lookup"><span data-stu-id="378fd-105">Applies an operation to the first two qubits in the register.</span></span>
<span data-ttu-id="378fd-106">Modyfikator `CA` wskazuje, że operacja jest sterowana i sąsiadująca.</span><span class="sxs-lookup"><span data-stu-id="378fd-106">The modifier `CA` indicates that the operation is controllable and adjointable.</span></span>

```qsharp
operation ApplyToFirstTwoQubitsCA (op : ((Qubit, Qubit) => Unit is Adj + Ctl), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="378fd-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="378fd-107">Input</span></span>

### <a name="op--qubitqubit--unit-adj--ctl"></a><span data-ttu-id="378fd-108">op: ([qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => skorygowanie [jednostki](xref:microsoft.quantum.lang-ref.unit) + CTL</span><span class="sxs-lookup"><span data-stu-id="378fd-108">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="378fd-109">Operacja, która ma zostać zastosowana do pierwszych dwóch qubits</span><span class="sxs-lookup"><span data-stu-id="378fd-109">An operation to be applied to the first two qubits</span></span>


### <a name="register--qubit"></a><span data-ttu-id="378fd-110">Rejestr: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="378fd-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="378fd-111">Qubit tablicę do pierwszych dwóch qubits, do których zostanie zastosowana operacja.</span><span class="sxs-lookup"><span data-stu-id="378fd-111">Qubit array to the first two qubits of which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="378fd-112">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="378fd-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="378fd-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="378fd-113">Remarks</span></span>

<span data-ttu-id="378fd-114">Jest to równoważne z:</span><span class="sxs-lookup"><span data-stu-id="378fd-114">This is equivalent to:</span></span>

```qsharp
op(register[0], register[1]);
```

## <a name="see-also"></a><span data-ttu-id="378fd-115">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="378fd-115">See Also</span></span>

- [<span data-ttu-id="378fd-116">Microsoft. Quantum. Canon. ApplyToFirstTwoQubits</span><span class="sxs-lookup"><span data-stu-id="378fd-116">Microsoft.Quantum.Canon.ApplyToFirstTwoQubits</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstTwoQubits)