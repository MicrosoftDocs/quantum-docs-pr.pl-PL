---
uid: Microsoft.Quantum.Canon.RestrictedToSubregisterCA
title: RestrictedToSubregisterCA, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RestrictedToSubregisterCA
qsharp.summary: Restricts an operation to an array of indices of a register, i.e., a subregister. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: e81193a85451b72a69a595fa81a9fb07f3038c22
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715526"
---
# <a name="restrictedtosubregisterca-function"></a><span data-ttu-id="82205-102">RestrictedToSubregisterCA, funkcja</span><span class="sxs-lookup"><span data-stu-id="82205-102">RestrictedToSubregisterCA function</span></span>

<span data-ttu-id="82205-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="82205-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="82205-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="82205-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="82205-105">Ogranicza operację do tablicy indeksów rejestru, tj. podrejestru.</span><span class="sxs-lookup"><span data-stu-id="82205-105">Restricts an operation to an array of indices of a register, i.e., a subregister.</span></span>
<span data-ttu-id="82205-106">Modyfikator `CA` wskazuje, że operacja jest sterowana i sąsiadująca.</span><span class="sxs-lookup"><span data-stu-id="82205-106">The modifier `CA` indicates that the operation is controllable and adjointable.</span></span>

```qsharp
function RestrictedToSubregisterCA (op : (Qubit[] => Unit is Adj + Ctl), idxs : Int[]) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="82205-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="82205-107">Input</span></span>

### <a name="op--qubit--unit-adj--ctl"></a><span data-ttu-id="82205-108">op: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => korekta [jednostki](xref:microsoft.quantum.lang-ref.unit) + CTL</span><span class="sxs-lookup"><span data-stu-id="82205-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="82205-109">Operacja jest ograniczona do podrejestru.</span><span class="sxs-lookup"><span data-stu-id="82205-109">Operation to be restricted to a subregister.</span></span>


### <a name="idxs--int"></a><span data-ttu-id="82205-110">idxs: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="82205-110">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="82205-111">Tablica indeksów wskazująca, które qubits operacja zostanie ograniczona.</span><span class="sxs-lookup"><span data-stu-id="82205-111">Array of indices, indicating to which qubits the operation will be restricted.</span></span>



## <a name="output--qubit--unit-adj--ctl"></a><span data-ttu-id="82205-112">Output: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => korekta [jednostki](xref:microsoft.quantum.lang-ref.unit) + CTL</span><span class="sxs-lookup"><span data-stu-id="82205-112">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>



## <a name="see-also"></a><span data-ttu-id="82205-113">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="82205-113">See Also</span></span>

- [<span data-ttu-id="82205-114">Microsoft. Quantum. Canon. RestrictedToSubregister</span><span class="sxs-lookup"><span data-stu-id="82205-114">Microsoft.Quantum.Canon.RestrictedToSubregister</span></span>](xref:Microsoft.Quantum.Canon.RestrictedToSubregister)