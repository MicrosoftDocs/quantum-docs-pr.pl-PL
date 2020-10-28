---
uid: Microsoft.Quantum.Diagnostics._assertEqualOnBasisVector
title: Operacja _assertEqualOnBasisVector
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _assertEqualOnBasisVector
qsharp.summary: Checks if the result of applying two operations `givenU` and `expectedU` to a basis state is the same. The basis state is described by `basis` parameter. See <xref:microsoft.quantum.extensions.fliptobasis> function for more details on this description.
ms.openlocfilehash: 01b6d5aede102e47df86ea70d071d81eba1ade6f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713155"
---
# <a name="_assertequalonbasisvector-operation"></a><span data-ttu-id="ec8c3-102">Operacja _assertEqualOnBasisVector</span><span class="sxs-lookup"><span data-stu-id="ec8c3-102">_assertEqualOnBasisVector operation</span></span>

<span data-ttu-id="ec8c3-103">Przestrzeń nazw: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="ec8c3-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="ec8c3-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ec8c3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ec8c3-105">Sprawdza, czy wynik zastosowania dwóch operacji `givenU` i `expectedU` do stanu podstawy jest taki sam.</span><span class="sxs-lookup"><span data-stu-id="ec8c3-105">Checks if the result of applying two operations `givenU` and `expectedU` to a basis state is the same.</span></span> <span data-ttu-id="ec8c3-106">Stan podstawy jest opisany przez `basis` parametr.</span><span class="sxs-lookup"><span data-stu-id="ec8c3-106">The basis state is described by `basis` parameter.</span></span>
<span data-ttu-id="ec8c3-107">Zobacz <xref:microsoft.quantum.extensions.fliptobasis> Funkcja, aby uzyskać więcej informacji na temat tego opisu.</span><span class="sxs-lookup"><span data-stu-id="ec8c3-107">See <xref:microsoft.quantum.extensions.fliptobasis> function for more details on this description.</span></span>

```qsharp
operation _assertEqualOnBasisVector (basis : Int[], givenU : (Qubit[] => Unit), expectedU : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a><span data-ttu-id="ec8c3-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="ec8c3-108">Input</span></span>

### <a name="basis--int"></a><span data-ttu-id="ec8c3-109">Podstawa: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="ec8c3-109">basis : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="ec8c3-110">Stan bazowy określony przez identyfikator stanu podstawy pojedynczego qubit (0 <= ID <= 3) dla każdej z $n $ qubits.</span><span class="sxs-lookup"><span data-stu-id="ec8c3-110">Basis state specified by a single-qubit basis state ID (0 <= id <= 3) for each of $n$ qubits.</span></span>


### <a name="givenu--qubit--unit"></a><span data-ttu-id="ec8c3-111">givenU: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [Jednostka](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="ec8c3-111">givenU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="ec8c3-112">Operacja na $n $ qubits do sprawdzenia.</span><span class="sxs-lookup"><span data-stu-id="ec8c3-112">Operation on $n$ qubits to be checked.</span></span>


### <a name="expectedu--qubit--unit-adj"></a><span data-ttu-id="ec8c3-113">expectedU: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => korekta [jednostki](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ec8c3-113">expectedU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="ec8c3-114">Operacja odwołania na $n $ qubits, że givenU jest porównywana z.</span><span class="sxs-lookup"><span data-stu-id="ec8c3-114">Reference operation on $n$ qubits that givenU is to be compared against.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ec8c3-115">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ec8c3-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

