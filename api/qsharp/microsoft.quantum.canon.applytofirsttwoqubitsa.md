---
uid: Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsA
title: ApplyToFirstTwoQubitsA, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstTwoQubitsA
qsharp.summary: Applies an operation to the first two qubits in the register. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: 911e9bc3d02bf6c0395c30fa167a6cb730dc666e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717304"
---
# <a name="applytofirsttwoqubitsa-operation"></a><span data-ttu-id="c9941-102">ApplyToFirstTwoQubitsA, operacja</span><span class="sxs-lookup"><span data-stu-id="c9941-102">ApplyToFirstTwoQubitsA operation</span></span>

<span data-ttu-id="c9941-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c9941-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c9941-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c9941-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c9941-105">Stosuje operację do pierwszych dwóch qubits w rejestrze.</span><span class="sxs-lookup"><span data-stu-id="c9941-105">Applies an operation to the first two qubits in the register.</span></span>
<span data-ttu-id="c9941-106">Modyfikator `A` wskazuje, że operacja jest sąsiedni.</span><span class="sxs-lookup"><span data-stu-id="c9941-106">The modifier `A` indicates that the operation is adjointable.</span></span>

```qsharp
operation ApplyToFirstTwoQubitsA (op : ((Qubit, Qubit) => Unit is Adj), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="c9941-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="c9941-107">Input</span></span>

### <a name="op--qubitqubit--unit-adj"></a><span data-ttu-id="c9941-108">op: ([qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => korekta [jednostki](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c9941-108">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="c9941-109">Operacja, która ma zostać zastosowana do pierwszych dwóch qubits</span><span class="sxs-lookup"><span data-stu-id="c9941-109">An operation to be applied to the first two qubits</span></span>


### <a name="register--qubit"></a><span data-ttu-id="c9941-110">Rejestr: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="c9941-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="c9941-111">Qubit tablicę do pierwszych dwóch qubits, do których zostanie zastosowana operacja.</span><span class="sxs-lookup"><span data-stu-id="c9941-111">Qubit array to the first two qubits of which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c9941-112">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c9941-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="c9941-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="c9941-113">Remarks</span></span>

<span data-ttu-id="c9941-114">Jest to równoważne z:</span><span class="sxs-lookup"><span data-stu-id="c9941-114">This is equivalent to:</span></span>

```qsharp
op(register[0], register[1]);
```

## <a name="see-also"></a><span data-ttu-id="c9941-115">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="c9941-115">See Also</span></span>

- [<span data-ttu-id="c9941-116">Microsoft. Quantum. Canon. ApplyToFirstTwoQubits</span><span class="sxs-lookup"><span data-stu-id="c9941-116">Microsoft.Quantum.Canon.ApplyToFirstTwoQubits</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstTwoQubits)