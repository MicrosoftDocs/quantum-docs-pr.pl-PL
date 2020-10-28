---
uid: Microsoft.Quantum.Canon.RestrictedToSubregister
title: RestrictedToSubregister, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RestrictedToSubregister
qsharp.summary: Restricts an operation to an array of indices of a register, i.e., a subregister.
ms.openlocfilehash: a8b599035de6fede10bdaf8cef17f2124a59f064
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715540"
---
# <a name="restrictedtosubregister-function"></a><span data-ttu-id="1f6a7-102">RestrictedToSubregister, funkcja</span><span class="sxs-lookup"><span data-stu-id="1f6a7-102">RestrictedToSubregister function</span></span>

<span data-ttu-id="1f6a7-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="1f6a7-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="1f6a7-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1f6a7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1f6a7-105">Ogranicza operację do tablicy indeksów rejestru, tj. podrejestru.</span><span class="sxs-lookup"><span data-stu-id="1f6a7-105">Restricts an operation to an array of indices of a register, i.e., a subregister.</span></span>

```qsharp
function RestrictedToSubregister (op : (Qubit[] => Unit), idxs : Int[]) : (Qubit[] => Unit)
```


## <a name="input"></a><span data-ttu-id="1f6a7-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="1f6a7-106">Input</span></span>

### <a name="op--qubit--unit"></a><span data-ttu-id="1f6a7-107">op: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [Jednostka](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="1f6a7-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="1f6a7-108">Operacja jest ograniczona do podrejestru.</span><span class="sxs-lookup"><span data-stu-id="1f6a7-108">Operation to be restricted to a subregister.</span></span>


### <a name="idxs--int"></a><span data-ttu-id="1f6a7-109">idxs: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="1f6a7-109">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="1f6a7-110">Tablica indeksów wskazująca, które qubits operacja zostanie ograniczona.</span><span class="sxs-lookup"><span data-stu-id="1f6a7-110">Array of indices, indicating to which qubits the operation will be restricted.</span></span>



## <a name="output--qubit--unit"></a><span data-ttu-id="1f6a7-111">Output: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [Jednostka](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="1f6a7-111">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 



## <a name="see-also"></a><span data-ttu-id="1f6a7-112">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="1f6a7-112">See Also</span></span>

- [<span data-ttu-id="1f6a7-113">Microsoft. Quantum. Canon. RestrictedToSubregisterA</span><span class="sxs-lookup"><span data-stu-id="1f6a7-113">Microsoft.Quantum.Canon.RestrictedToSubregisterA</span></span>](xref:Microsoft.Quantum.Canon.RestrictedToSubregisterA)
- [<span data-ttu-id="1f6a7-114">Microsoft. Quantum. Canon. RestrictedToSubregisterC</span><span class="sxs-lookup"><span data-stu-id="1f6a7-114">Microsoft.Quantum.Canon.RestrictedToSubregisterC</span></span>](xref:Microsoft.Quantum.Canon.RestrictedToSubregisterC)
- [<span data-ttu-id="1f6a7-115">Microsoft. Quantum. Canon. RestrictedToSubregisterCA</span><span class="sxs-lookup"><span data-stu-id="1f6a7-115">Microsoft.Quantum.Canon.RestrictedToSubregisterCA</span></span>](xref:Microsoft.Quantum.Canon.RestrictedToSubregisterCA)