---
uid: Microsoft.Quantum.Canon.ApplyToSubregisterC
title: ApplyToSubregisterC, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToSubregisterC
qsharp.summary: Applies an operation to a subregister of a register, with qubits specified by an array of their indices. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: 52564e64d8cc9cdbeb2626ed8694168b8ed48c22
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850461"
---
# <a name="applytosubregisterc-operation"></a><span data-ttu-id="8f8a1-102">ApplyToSubregisterC, operacja</span><span class="sxs-lookup"><span data-stu-id="8f8a1-102">ApplyToSubregisterC operation</span></span>

<span data-ttu-id="8f8a1-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="8f8a1-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="8f8a1-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8f8a1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8f8a1-105">Stosuje operację do podrejestru rejestru, z qubitsem określonym przez tablicę ich indeksów.</span><span class="sxs-lookup"><span data-stu-id="8f8a1-105">Applies an operation to a subregister of a register, with qubits specified by an array of their indices.</span></span>
<span data-ttu-id="8f8a1-106">Modyfikator `C` wskazuje, że operacja jest sterowana.</span><span class="sxs-lookup"><span data-stu-id="8f8a1-106">The modifier `C` indicates that the operation is controllable.</span></span>

```qsharp
operation ApplyToSubregisterC (op : (Qubit[] => Unit is Ctl), idxs : Int[], target : Qubit[]) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="8f8a1-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="8f8a1-107">Input</span></span>

### <a name="op--qubit--unit--is-ctl"></a><span data-ttu-id="8f8a1-108">op: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [Jednostka](xref:microsoft.quantum.lang-ref.unit) > jest listą CTL</span><span class="sxs-lookup"><span data-stu-id="8f8a1-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="8f8a1-109">Operacja stosowana do podrejestru.</span><span class="sxs-lookup"><span data-stu-id="8f8a1-109">Operation to apply to subregister.</span></span>


### <a name="idxs--int"></a><span data-ttu-id="8f8a1-110">idxs: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="8f8a1-110">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="8f8a1-111">Tablica indeksów wskazujących, do których qubits zostanie zastosowana operacja.</span><span class="sxs-lookup"><span data-stu-id="8f8a1-111">Array of indices, indicating to which qubits the operation will be applied.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="8f8a1-112">target: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="8f8a1-112">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="8f8a1-113">Zarejestruj się, na którym działa operacja.</span><span class="sxs-lookup"><span data-stu-id="8f8a1-113">Register on which the operation acts.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8f8a1-114">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8f8a1-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="8f8a1-115">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="8f8a1-115">See Also</span></span>

- [<span data-ttu-id="8f8a1-116">Microsoft. Quantum. Canon. ApplyToSubregister</span><span class="sxs-lookup"><span data-stu-id="8f8a1-116">Microsoft.Quantum.Canon.ApplyToSubregister</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregister)