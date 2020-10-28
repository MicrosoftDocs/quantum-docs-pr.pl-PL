---
uid: Microsoft.Quantum.Canon.ApplyToSubregisterC
title: ApplyToSubregisterC, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToSubregisterC
qsharp.summary: Applies an operation to a subregister of a register, with qubits specified by an array of their indices. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: ba5be1e7e822197eb76aac029be8617a70d51ddb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717005"
---
# <a name="applytosubregisterc-operation"></a><span data-ttu-id="2a581-102">ApplyToSubregisterC, operacja</span><span class="sxs-lookup"><span data-stu-id="2a581-102">ApplyToSubregisterC operation</span></span>

<span data-ttu-id="2a581-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="2a581-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="2a581-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2a581-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2a581-105">Stosuje operację do podrejestru rejestru, z qubitsem określonym przez tablicę ich indeksów.</span><span class="sxs-lookup"><span data-stu-id="2a581-105">Applies an operation to a subregister of a register, with qubits specified by an array of their indices.</span></span>
<span data-ttu-id="2a581-106">Modyfikator `C` wskazuje, że operacja jest sterowana.</span><span class="sxs-lookup"><span data-stu-id="2a581-106">The modifier `C` indicates that the operation is controllable.</span></span>

```qsharp
operation ApplyToSubregisterC (op : (Qubit[] => Unit is Ctl), idxs : Int[], target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="2a581-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="2a581-107">Input</span></span>

### <a name="op--qubit--unit-ctl"></a><span data-ttu-id="2a581-108">op: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednostki](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="2a581-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="2a581-109">Operacja stosowana do podrejestru.</span><span class="sxs-lookup"><span data-stu-id="2a581-109">Operation to apply to subregister.</span></span>


### <a name="idxs--int"></a><span data-ttu-id="2a581-110">idxs: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="2a581-110">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="2a581-111">Tablica indeksów wskazujących, do których qubits zostanie zastosowana operacja.</span><span class="sxs-lookup"><span data-stu-id="2a581-111">Array of indices, indicating to which qubits the operation will be applied.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="2a581-112">target: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="2a581-112">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="2a581-113">Zarejestruj się, na którym działa operacja.</span><span class="sxs-lookup"><span data-stu-id="2a581-113">Register on which the operation acts.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2a581-114">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2a581-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="2a581-115">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="2a581-115">See Also</span></span>

- [<span data-ttu-id="2a581-116">Microsoft. Quantum. Canon. ApplyToSubregister</span><span class="sxs-lookup"><span data-stu-id="2a581-116">Microsoft.Quantum.Canon.ApplyToSubregister</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregister)