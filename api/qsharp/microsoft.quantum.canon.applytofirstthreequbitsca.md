---
uid: Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsCA
title: ApplyToFirstThreeQubitsCA, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstThreeQubitsCA
qsharp.summary: Applies an operation to the first three qubits in the register. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: bd7a3ac260d370aae9da8691fcd34a8b6221d451
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717346"
---
# <a name="applytofirstthreequbitsca-operation"></a><span data-ttu-id="bf510-102">ApplyToFirstThreeQubitsCA, operacja</span><span class="sxs-lookup"><span data-stu-id="bf510-102">ApplyToFirstThreeQubitsCA operation</span></span>

<span data-ttu-id="bf510-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="bf510-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="bf510-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="bf510-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="bf510-105">Stosuje operację do pierwszych trzech qubits w rejestrze.</span><span class="sxs-lookup"><span data-stu-id="bf510-105">Applies an operation to the first three qubits in the register.</span></span>
<span data-ttu-id="bf510-106">Modyfikator `CA` wskazuje, że operacja jest sterowana i sąsiadująca.</span><span class="sxs-lookup"><span data-stu-id="bf510-106">The modifier `CA` indicates that the operation is controllable and adjointable.</span></span>

```qsharp
operation ApplyToFirstThreeQubitsCA (op : ((Qubit, Qubit, Qubit) => Unit is Adj + Ctl), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="bf510-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="bf510-107">Input</span></span>

### <a name="op--qubitqubitqubit--unit-adj--ctl"></a><span data-ttu-id="bf510-108">op: ([qubit](xref:microsoft.quantum.lang-ref.qubit),[qubit](xref:microsoft.quantum.lang-ref.qubit),[qubit](xref:microsoft.quantum.lang-ref.qubit)) => skorygowania [jednostki](xref:microsoft.quantum.lang-ref.unit) + CTL</span><span class="sxs-lookup"><span data-stu-id="bf510-108">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="bf510-109">Operacja, która ma zostać zastosowana do pierwszych trzech qubits</span><span class="sxs-lookup"><span data-stu-id="bf510-109">An operation to be applied to the first three qubits</span></span>


### <a name="register--qubit"></a><span data-ttu-id="bf510-110">Rejestr: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="bf510-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="bf510-111">Qubit tablicę do pierwszych trzech qubits, do których zostanie zastosowana operacja.</span><span class="sxs-lookup"><span data-stu-id="bf510-111">Qubit array to the first three qubits of which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="bf510-112">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bf510-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="bf510-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="bf510-113">Remarks</span></span>

<span data-ttu-id="bf510-114">Jest to równoważne z:</span><span class="sxs-lookup"><span data-stu-id="bf510-114">This is equivalent to:</span></span>

```qsharp
op(register[0], register[1], register[2]);
```

## <a name="see-also"></a><span data-ttu-id="bf510-115">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="bf510-115">See Also</span></span>

- [<span data-ttu-id="bf510-116">Microsoft. Quantum. Canon. ApplyToFirstThreeQubits</span><span class="sxs-lookup"><span data-stu-id="bf510-116">Microsoft.Quantum.Canon.ApplyToFirstThreeQubits</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubits)