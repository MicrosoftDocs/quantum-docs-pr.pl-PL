---
uid: Microsoft.Quantum.Diagnostics._assertEqualOnBasisVector
title: Operacja _assertEqualOnBasisVector
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _assertEqualOnBasisVector
qsharp.summary: Checks if the result of applying two operations `givenU` and `expectedU` to a basis state is the same. The basis state is described by `basis` parameter. See <xref:microsoft.quantum.extensions.fliptobasis> function for more details on this description.
ms.openlocfilehash: d8f2195f75de49918032053dc8d1fa4fb4eba840
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96213773"
---
# <a name="_assertequalonbasisvector-operation"></a><span data-ttu-id="6ffc5-102">Operacja _assertEqualOnBasisVector</span><span class="sxs-lookup"><span data-stu-id="6ffc5-102">_assertEqualOnBasisVector operation</span></span>

<span data-ttu-id="6ffc5-103">Przestrzeń nazw: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="6ffc5-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="6ffc5-104">Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="6ffc5-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="6ffc5-105">Sprawdza, czy wynik zastosowania dwóch operacji `givenU` i `expectedU` do stanu podstawy jest taki sam.</span><span class="sxs-lookup"><span data-stu-id="6ffc5-105">Checks if the result of applying two operations `givenU` and `expectedU` to a basis state is the same.</span></span> <span data-ttu-id="6ffc5-106">Stan podstawy jest opisany przez `basis` parametr.</span><span class="sxs-lookup"><span data-stu-id="6ffc5-106">The basis state is described by `basis` parameter.</span></span>
<span data-ttu-id="6ffc5-107">Zobacz <xref:microsoft.quantum.extensions.fliptobasis> Funkcja, aby uzyskać więcej informacji na temat tego opisu.</span><span class="sxs-lookup"><span data-stu-id="6ffc5-107">See <xref:microsoft.quantum.extensions.fliptobasis> function for more details on this description.</span></span>

```qsharp
operation _assertEqualOnBasisVector (basis : Int[], givenU : (Qubit[] => Unit), expectedU : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a><span data-ttu-id="6ffc5-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="6ffc5-108">Input</span></span>

### <a name="basis--int"></a><span data-ttu-id="6ffc5-109">Podstawa: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="6ffc5-109">basis : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="6ffc5-110">Stan bazowy określony przez identyfikator stanu podstawy pojedynczego qubit (0 <= ID <= 3) dla każdej z $n $ qubits.</span><span class="sxs-lookup"><span data-stu-id="6ffc5-110">Basis state specified by a single-qubit basis state ID (0 <= id <= 3) for each of $n$ qubits.</span></span>


### <a name="givenu--qubit--unit"></a><span data-ttu-id="6ffc5-111">givenU: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [Jednostka](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="6ffc5-111">givenU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="6ffc5-112">Operacja na $n $ qubits do sprawdzenia.</span><span class="sxs-lookup"><span data-stu-id="6ffc5-112">Operation on $n$ qubits to be checked.</span></span>


### <a name="expectedu--qubit--unit--is-adj"></a><span data-ttu-id="6ffc5-113">expectedU: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [Jednostka](xref:microsoft.quantum.lang-ref.unit) > jest korektą</span><span class="sxs-lookup"><span data-stu-id="6ffc5-113">expectedU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="6ffc5-114">Operacja odwołania na $n $ qubits, że givenU jest porównywana z.</span><span class="sxs-lookup"><span data-stu-id="6ffc5-114">Reference operation on $n$ qubits that givenU is to be compared against.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6ffc5-115">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6ffc5-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

