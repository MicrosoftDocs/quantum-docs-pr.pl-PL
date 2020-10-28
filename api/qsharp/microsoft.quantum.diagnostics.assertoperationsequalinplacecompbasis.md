---
uid: Microsoft.Quantum.Diagnostics.AssertOperationsEqualInPlaceCompBasis
title: AssertOperationsEqualInPlaceCompBasis, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertOperationsEqualInPlaceCompBasis
qsharp.summary: Checks if the operation `givenU` is equal to the operation `expectedU` on the given input size  by checking the action of the operations only on the vectors from the computational basis. This is a necessary, but not sufficient, condition for the equality of two unitaries.
ms.openlocfilehash: 3275680f86ca2a178c7f044b97d226fe41c3186c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712964"
---
# <a name="assertoperationsequalinplacecompbasis-operation"></a><span data-ttu-id="52979-102">AssertOperationsEqualInPlaceCompBasis, operacja</span><span class="sxs-lookup"><span data-stu-id="52979-102">AssertOperationsEqualInPlaceCompBasis operation</span></span>

<span data-ttu-id="52979-103">Przestrzeń nazw: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="52979-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="52979-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="52979-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="52979-105">Sprawdza, czy operacja `givenU` jest równa operacji `expectedU` względem danego rozmiaru danych wejściowych przez sprawdzenie działania operacji tylko dla wektorów z podstawy obliczeniowej.</span><span class="sxs-lookup"><span data-stu-id="52979-105">Checks if the operation `givenU` is equal to the operation `expectedU` on the given input size  by checking the action of the operations only on the vectors from the computational basis.</span></span>
<span data-ttu-id="52979-106">Jest to niezbędne, ale nie wystarczające, warunek dla równości dwóch unitaries.</span><span class="sxs-lookup"><span data-stu-id="52979-106">This is a necessary, but not sufficient, condition for the equality of two unitaries.</span></span>

```qsharp
operation AssertOperationsEqualInPlaceCompBasis (nQubits : Int, givenU : (Qubit[] => Unit), expectedU : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a><span data-ttu-id="52979-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="52979-107">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="52979-108">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="52979-108">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="52979-109">Liczba qubits $n $, w których operacje `givenU` i `expectedU` działania.</span><span class="sxs-lookup"><span data-stu-id="52979-109">The number of qubits $n$ that the operations `givenU` and `expectedU` operate on.</span></span>


### <a name="givenu--qubit--unit"></a><span data-ttu-id="52979-110">givenU: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [Jednostka](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="52979-110">givenU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="52979-111">Operacja na $n $ qubits do sprawdzenia.</span><span class="sxs-lookup"><span data-stu-id="52979-111">Operation on $n$ qubits to be checked.</span></span>


### <a name="expectedu--qubit--unit-adj"></a><span data-ttu-id="52979-112">expectedU: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => korekta [jednostki](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="52979-112">expectedU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="52979-113">Operacja odwołania na $n $ qubits, która `givenU` ma zostać porównana z.</span><span class="sxs-lookup"><span data-stu-id="52979-113">Reference operation on $n$ qubits that `givenU` is to be compared against.</span></span>



## <a name="output--unit"></a><span data-ttu-id="52979-114">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="52979-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

