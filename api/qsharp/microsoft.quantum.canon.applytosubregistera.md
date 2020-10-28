---
uid: Microsoft.Quantum.Canon.ApplyToSubregisterA
title: ApplyToSubregisterA, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToSubregisterA
qsharp.summary: Applies an operation to a subregister of a register, with qubits specified by an array of their indices. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: e0c546b768320ce43e7b44242d15838194e1089d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717024"
---
# <a name="applytosubregistera-operation"></a><span data-ttu-id="2b791-102">ApplyToSubregisterA, operacja</span><span class="sxs-lookup"><span data-stu-id="2b791-102">ApplyToSubregisterA operation</span></span>

<span data-ttu-id="2b791-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="2b791-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="2b791-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2b791-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2b791-105">Stosuje operację do podrejestru rejestru, z qubitsem określonym przez tablicę ich indeksów.</span><span class="sxs-lookup"><span data-stu-id="2b791-105">Applies an operation to a subregister of a register, with qubits specified by an array of their indices.</span></span>
<span data-ttu-id="2b791-106">Modyfikator `A` wskazuje, że operacja jest sąsiedni.</span><span class="sxs-lookup"><span data-stu-id="2b791-106">The modifier `A` indicates that the operation is adjointable.</span></span>

```qsharp
operation ApplyToSubregisterA (op : (Qubit[] => Unit is Adj), idxs : Int[], target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="2b791-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="2b791-107">Input</span></span>

### <a name="op--qubit--unit-adj"></a><span data-ttu-id="2b791-108">op: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => korekta [jednostki](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2b791-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="2b791-109">Operacja stosowana do podrejestru.</span><span class="sxs-lookup"><span data-stu-id="2b791-109">Operation to apply to subregister.</span></span>


### <a name="idxs--int"></a><span data-ttu-id="2b791-110">idxs: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="2b791-110">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="2b791-111">Tablica indeksów wskazujących, do których qubits zostanie zastosowana operacja.</span><span class="sxs-lookup"><span data-stu-id="2b791-111">Array of indices, indicating to which qubits the operation will be applied.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="2b791-112">target: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="2b791-112">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="2b791-113">Zarejestruj się, na którym działa operacja.</span><span class="sxs-lookup"><span data-stu-id="2b791-113">Register on which the operation acts.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2b791-114">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2b791-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="2b791-115">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="2b791-115">See Also</span></span>

- [<span data-ttu-id="2b791-116">Microsoft. Quantum. Canon. ApplyToSubregister</span><span class="sxs-lookup"><span data-stu-id="2b791-116">Microsoft.Quantum.Canon.ApplyToSubregister</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregister)