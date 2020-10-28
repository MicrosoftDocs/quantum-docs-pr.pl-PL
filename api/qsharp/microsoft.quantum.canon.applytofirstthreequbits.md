---
uid: Microsoft.Quantum.Canon.ApplyToFirstThreeQubits
title: ApplyToFirstThreeQubits, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstThreeQubits
qsharp.summary: Applies an operation to the first three qubits in the register.
ms.openlocfilehash: 61330f9e9b1f6b9f3965c9240505814b295aaefe
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717383"
---
# <a name="applytofirstthreequbits-operation"></a><span data-ttu-id="18160-102">ApplyToFirstThreeQubits, operacja</span><span class="sxs-lookup"><span data-stu-id="18160-102">ApplyToFirstThreeQubits operation</span></span>

<span data-ttu-id="18160-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="18160-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="18160-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="18160-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="18160-105">Stosuje operację do pierwszych trzech qubits w rejestrze.</span><span class="sxs-lookup"><span data-stu-id="18160-105">Applies an operation to the first three qubits in the register.</span></span>

```qsharp
operation ApplyToFirstThreeQubits (op : ((Qubit, Qubit, Qubit) => Unit), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="18160-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="18160-106">Input</span></span>

### <a name="op--qubitqubitqubit--unit"></a><span data-ttu-id="18160-107">op: ([qubit](xref:microsoft.quantum.lang-ref.qubit),[qubit](xref:microsoft.quantum.lang-ref.qubit),[qubit](xref:microsoft.quantum.lang-ref.qubit)) = [Jednostka](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="18160-107">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="18160-108">Operacja, która ma zostać zastosowana do pierwszych trzech qubits</span><span class="sxs-lookup"><span data-stu-id="18160-108">An operation to be applied to the first three qubits</span></span>


### <a name="register--qubit"></a><span data-ttu-id="18160-109">Rejestr: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="18160-109">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="18160-110">Qubit tablicę do pierwszych trzech qubits, do których zostanie zastosowana operacja.</span><span class="sxs-lookup"><span data-stu-id="18160-110">Qubit array to the first three qubits of which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="18160-111">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="18160-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="18160-112">Uwagi</span><span class="sxs-lookup"><span data-stu-id="18160-112">Remarks</span></span>

<span data-ttu-id="18160-113">Jest to równoważne z:</span><span class="sxs-lookup"><span data-stu-id="18160-113">This is equivalent to:</span></span>

```qsharp
op(register[0], register[1], register[2]);
```

## <a name="see-also"></a><span data-ttu-id="18160-114">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="18160-114">See Also</span></span>

- [<span data-ttu-id="18160-115">Microsoft. Quantum. Canon. ApplyToFirstThreeQubitsC</span><span class="sxs-lookup"><span data-stu-id="18160-115">Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsC)
- [<span data-ttu-id="18160-116">Microsoft. Quantum. Canon. ApplyToFirstThreeQubitsA</span><span class="sxs-lookup"><span data-stu-id="18160-116">Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsA)
- [<span data-ttu-id="18160-117">Microsoft. Quantum. Canon. ApplyToFirstThreeQubitsCA</span><span class="sxs-lookup"><span data-stu-id="18160-117">Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsCA)