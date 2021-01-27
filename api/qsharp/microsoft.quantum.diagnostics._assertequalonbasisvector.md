---
uid: Microsoft.Quantum.Diagnostics._assertEqualOnBasisVector
title: Operacja _assertEqualOnBasisVector
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _assertEqualOnBasisVector
qsharp.summary: Checks if the result of applying two operations `givenU` and `expectedU` to a basis state is the same. The basis state is described by `basis` parameter. See <xref:microsoft.quantum.extensions.fliptobasis> function for more details on this description.
ms.openlocfilehash: 041fecfa27ae5bd17fa8fdc89ce964f985f6124b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853581"
---
# <a name="_assertequalonbasisvector-operation"></a><span data-ttu-id="5bb11-102">Operacja _assertEqualOnBasisVector</span><span class="sxs-lookup"><span data-stu-id="5bb11-102">_assertEqualOnBasisVector operation</span></span>

<span data-ttu-id="5bb11-103">Przestrzeń nazw: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="5bb11-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="5bb11-104">Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="5bb11-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="5bb11-105">Sprawdza, czy wynik zastosowania dwóch operacji `givenU` i `expectedU` do stanu podstawy jest taki sam.</span><span class="sxs-lookup"><span data-stu-id="5bb11-105">Checks if the result of applying two operations `givenU` and `expectedU` to a basis state is the same.</span></span> <span data-ttu-id="5bb11-106">Stan podstawy jest opisany przez `basis` parametr.</span><span class="sxs-lookup"><span data-stu-id="5bb11-106">The basis state is described by `basis` parameter.</span></span>
<span data-ttu-id="5bb11-107">Zobacz <xref:microsoft.quantum.extensions.fliptobasis> Funkcja, aby uzyskać więcej informacji na temat tego opisu.</span><span class="sxs-lookup"><span data-stu-id="5bb11-107">See <xref:microsoft.quantum.extensions.fliptobasis> function for more details on this description.</span></span>

```qsharp
operation _assertEqualOnBasisVector (basis : Int[], givenU : (Qubit[] => Unit), expectedU : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a><span data-ttu-id="5bb11-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="5bb11-108">Input</span></span>

### <a name="basis--int"></a><span data-ttu-id="5bb11-109">Podstawa: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="5bb11-109">basis : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="5bb11-110">Stan bazowy określony przez identyfikator stanu podstawy pojedynczego qubit (0 <= ID <= 3) dla każdej z $n $ qubits.</span><span class="sxs-lookup"><span data-stu-id="5bb11-110">Basis state specified by a single-qubit basis state ID (0 <= id <= 3) for each of $n$ qubits.</span></span>


### <a name="givenu--qubit--unit"></a><span data-ttu-id="5bb11-111">givenU: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [Jednostka](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="5bb11-111">givenU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="5bb11-112">Operacja na $n $ qubits do sprawdzenia.</span><span class="sxs-lookup"><span data-stu-id="5bb11-112">Operation on $n$ qubits to be checked.</span></span>


### <a name="expectedu--qubit--unit--is-adj"></a><span data-ttu-id="5bb11-113">expectedU: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [Jednostka](xref:microsoft.quantum.lang-ref.unit) > jest korektą</span><span class="sxs-lookup"><span data-stu-id="5bb11-113">expectedU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="5bb11-114">Operacja odwołania na $n $ qubits, że givenU jest porównywana z.</span><span class="sxs-lookup"><span data-stu-id="5bb11-114">Reference operation on $n$ qubits that givenU is to be compared against.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5bb11-115">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5bb11-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

