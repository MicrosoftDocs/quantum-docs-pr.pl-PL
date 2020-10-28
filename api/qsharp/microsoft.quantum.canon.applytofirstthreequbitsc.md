---
uid: Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsC
title: ApplyToFirstThreeQubitsC, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstThreeQubitsC
qsharp.summary: Applies an operation to the first three qubits in the register. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: 9450b084cd77f75511fe631cda9a4f9fc426142d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717374"
---
# <a name="applytofirstthreequbitsc-operation"></a><span data-ttu-id="f1d4d-102">ApplyToFirstThreeQubitsC, operacja</span><span class="sxs-lookup"><span data-stu-id="f1d4d-102">ApplyToFirstThreeQubitsC operation</span></span>

<span data-ttu-id="f1d4d-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f1d4d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f1d4d-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f1d4d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f1d4d-105">Stosuje operację do pierwszych trzech qubits w rejestrze.</span><span class="sxs-lookup"><span data-stu-id="f1d4d-105">Applies an operation to the first three qubits in the register.</span></span>
<span data-ttu-id="f1d4d-106">Modyfikator `C` wskazuje, że operacja jest sterowana.</span><span class="sxs-lookup"><span data-stu-id="f1d4d-106">The modifier `C` indicates that the operation is controllable.</span></span>

```qsharp
operation ApplyToFirstThreeQubitsC (op : ((Qubit, Qubit, Qubit) => Unit is Ctl), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="f1d4d-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="f1d4d-107">Input</span></span>

### <a name="op--qubitqubitqubit--unit-ctl"></a><span data-ttu-id="f1d4d-108">op: ([qubit](xref:microsoft.quantum.lang-ref.qubit),[qubit](xref:microsoft.quantum.lang-ref.qubit),[qubit](xref:microsoft.quantum.lang-ref.qubit)) => [jednostki](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="f1d4d-108">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="f1d4d-109">Operacja, która ma zostać zastosowana do pierwszych trzech qubits</span><span class="sxs-lookup"><span data-stu-id="f1d4d-109">An operation to be applied to the first three qubits</span></span>


### <a name="register--qubit"></a><span data-ttu-id="f1d4d-110">Rejestr: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="f1d4d-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="f1d4d-111">Qubit tablicę do pierwszych trzech qubits, do których zostanie zastosowana operacja.</span><span class="sxs-lookup"><span data-stu-id="f1d4d-111">Qubit array to the first three qubits of which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f1d4d-112">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f1d4d-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="f1d4d-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="f1d4d-113">Remarks</span></span>

<span data-ttu-id="f1d4d-114">Jest to równoważne z:</span><span class="sxs-lookup"><span data-stu-id="f1d4d-114">This is equivalent to:</span></span>

```qsharp
op(register[0], register[1], register[2]);
```

## <a name="see-also"></a><span data-ttu-id="f1d4d-115">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="f1d4d-115">See Also</span></span>

- [<span data-ttu-id="f1d4d-116">Microsoft. Quantum. Canon. ApplyToFirstThreeQubits</span><span class="sxs-lookup"><span data-stu-id="f1d4d-116">Microsoft.Quantum.Canon.ApplyToFirstThreeQubits</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubits)