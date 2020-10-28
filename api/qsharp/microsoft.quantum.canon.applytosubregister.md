---
uid: Microsoft.Quantum.Canon.ApplyToSubregister
title: ApplyToSubregister, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToSubregister
qsharp.summary: Applies an operation to a subregister of a register, with qubits specified by an array of their indices.
ms.openlocfilehash: c9181b8962d36b20f7a9140eb7aaef11aee7faa0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717033"
---
# <a name="applytosubregister-operation"></a><span data-ttu-id="9b5ac-102">ApplyToSubregister, operacja</span><span class="sxs-lookup"><span data-stu-id="9b5ac-102">ApplyToSubregister operation</span></span>

<span data-ttu-id="9b5ac-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9b5ac-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9b5ac-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9b5ac-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9b5ac-105">Stosuje operację do podrejestru rejestru, z qubitsem określonym przez tablicę ich indeksów.</span><span class="sxs-lookup"><span data-stu-id="9b5ac-105">Applies an operation to a subregister of a register, with qubits specified by an array of their indices.</span></span>

```qsharp
operation ApplyToSubregister (op : (Qubit[] => Unit), idxs : Int[], target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="9b5ac-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="9b5ac-106">Input</span></span>

### <a name="op--qubit--unit"></a><span data-ttu-id="9b5ac-107">op: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [Jednostka](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="9b5ac-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="9b5ac-108">Operacja stosowana do podrejestru.</span><span class="sxs-lookup"><span data-stu-id="9b5ac-108">Operation to apply to subregister.</span></span>


### <a name="idxs--int"></a><span data-ttu-id="9b5ac-109">idxs: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="9b5ac-109">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="9b5ac-110">Tablica indeksów wskazujących, do których qubits zostanie zastosowana operacja.</span><span class="sxs-lookup"><span data-stu-id="9b5ac-110">Array of indices, indicating to which qubits the operation will be applied.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="9b5ac-111">target: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="9b5ac-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="9b5ac-112">Zarejestruj się, na którym działa operacja.</span><span class="sxs-lookup"><span data-stu-id="9b5ac-112">Register on which the operation acts.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9b5ac-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9b5ac-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="9b5ac-114">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="9b5ac-114">See Also</span></span>

- [<span data-ttu-id="9b5ac-115">Microsoft. Quantum. Canon. ApplyToSubregisterA</span><span class="sxs-lookup"><span data-stu-id="9b5ac-115">Microsoft.Quantum.Canon.ApplyToSubregisterA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregisterA)
- [<span data-ttu-id="9b5ac-116">Microsoft. Quantum. Canon. ApplyToSubregisterC</span><span class="sxs-lookup"><span data-stu-id="9b5ac-116">Microsoft.Quantum.Canon.ApplyToSubregisterC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregisterC)
- [<span data-ttu-id="9b5ac-117">Microsoft. Quantum. Canon. ApplyToSubregisterCA</span><span class="sxs-lookup"><span data-stu-id="9b5ac-117">Microsoft.Quantum.Canon.ApplyToSubregisterCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregisterCA)