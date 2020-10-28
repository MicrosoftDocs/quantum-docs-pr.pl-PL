---
uid: Microsoft.Quantum.Canon.RestrictedToSubregisterC
title: RestrictedToSubregisterC, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RestrictedToSubregisterC
qsharp.summary: Restricts an operation to an array of indices of a register, i.e., a subregister. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: 2ca32cf8c85f33f498a30f71833b3dd69db6da6e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715512"
---
# <a name="restrictedtosubregisterc-function"></a><span data-ttu-id="f449c-102">RestrictedToSubregisterC, funkcja</span><span class="sxs-lookup"><span data-stu-id="f449c-102">RestrictedToSubregisterC function</span></span>

<span data-ttu-id="f449c-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f449c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f449c-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f449c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f449c-105">Ogranicza operację do tablicy indeksów rejestru, tj. podrejestru.</span><span class="sxs-lookup"><span data-stu-id="f449c-105">Restricts an operation to an array of indices of a register, i.e., a subregister.</span></span>
<span data-ttu-id="f449c-106">Modyfikator `C` wskazuje, że operacja jest sterowana.</span><span class="sxs-lookup"><span data-stu-id="f449c-106">The modifier `C` indicates that the operation is controllable.</span></span>

```qsharp
function RestrictedToSubregisterC (op : (Qubit[] => Unit is Ctl), idxs : Int[]) : (Qubit[] => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="f449c-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="f449c-107">Input</span></span>

### <a name="op--qubit--unit-ctl"></a><span data-ttu-id="f449c-108">op: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednostki](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="f449c-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="f449c-109">Operacja jest ograniczona do podrejestru.</span><span class="sxs-lookup"><span data-stu-id="f449c-109">Operation to be restricted to a subregister.</span></span>


### <a name="idxs--int"></a><span data-ttu-id="f449c-110">idxs: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="f449c-110">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="f449c-111">Tablica indeksów wskazująca, które qubits operacja zostanie ograniczona.</span><span class="sxs-lookup"><span data-stu-id="f449c-111">Array of indices, indicating to which qubits the operation will be restricted.</span></span>



## <a name="output--qubit--unit-ctl"></a><span data-ttu-id="f449c-112">Output: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednostki](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="f449c-112">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>



## <a name="see-also"></a><span data-ttu-id="f449c-113">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="f449c-113">See Also</span></span>

- [<span data-ttu-id="f449c-114">Microsoft. Quantum. Canon. RestrictedToSubregister</span><span class="sxs-lookup"><span data-stu-id="f449c-114">Microsoft.Quantum.Canon.RestrictedToSubregister</span></span>](xref:Microsoft.Quantum.Canon.RestrictedToSubregister)