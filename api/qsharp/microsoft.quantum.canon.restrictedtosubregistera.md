---
uid: Microsoft.Quantum.Canon.RestrictedToSubregisterA
title: RestrictedToSubregisterA, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RestrictedToSubregisterA
qsharp.summary: Restricts an operation to an array of indices of a register, i.e., a subregister. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: d45c43caed35df8fb89d9d38e540faf5a21ea064
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715535"
---
# <a name="restrictedtosubregistera-function"></a><span data-ttu-id="8477c-102">RestrictedToSubregisterA, funkcja</span><span class="sxs-lookup"><span data-stu-id="8477c-102">RestrictedToSubregisterA function</span></span>

<span data-ttu-id="8477c-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="8477c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="8477c-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8477c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8477c-105">Ogranicza operację do tablicy indeksów rejestru, tj. podrejestru.</span><span class="sxs-lookup"><span data-stu-id="8477c-105">Restricts an operation to an array of indices of a register, i.e., a subregister.</span></span>
<span data-ttu-id="8477c-106">Modyfikator `A` wskazuje, że operacja jest sąsiedni.</span><span class="sxs-lookup"><span data-stu-id="8477c-106">The modifier `A` indicates that the operation is adjointable.</span></span>

```qsharp
function RestrictedToSubregisterA (op : (Qubit[] => Unit is Adj), idxs : Int[]) : (Qubit[] => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="8477c-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="8477c-107">Input</span></span>

### <a name="op--qubit--unit-adj"></a><span data-ttu-id="8477c-108">op: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => korekta [jednostki](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8477c-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="8477c-109">Operacja jest ograniczona do podrejestru.</span><span class="sxs-lookup"><span data-stu-id="8477c-109">Operation to be restricted to a subregister.</span></span>


### <a name="idxs--int"></a><span data-ttu-id="8477c-110">idxs: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="8477c-110">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="8477c-111">Tablica indeksów wskazująca, które qubits operacja zostanie ograniczona.</span><span class="sxs-lookup"><span data-stu-id="8477c-111">Array of indices, indicating to which qubits the operation will be restricted.</span></span>



## <a name="output--qubit--unit-adj"></a><span data-ttu-id="8477c-112">Wynik: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => korekta [jednostki](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8477c-112">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>



## <a name="see-also"></a><span data-ttu-id="8477c-113">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="8477c-113">See Also</span></span>

- [<span data-ttu-id="8477c-114">Microsoft. Quantum. Canon. RestrictedToSubregister</span><span class="sxs-lookup"><span data-stu-id="8477c-114">Microsoft.Quantum.Canon.RestrictedToSubregister</span></span>](xref:Microsoft.Quantum.Canon.RestrictedToSubregister)