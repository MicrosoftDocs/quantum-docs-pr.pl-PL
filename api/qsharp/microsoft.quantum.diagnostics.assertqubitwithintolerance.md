---
uid: Microsoft.Quantum.Diagnostics.AssertQubitWithinTolerance
title: AssertQubitWithinTolerance, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertQubitWithinTolerance
qsharp.summary: Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator up to a given tolerance.
ms.openlocfilehash: 3fe4aa739c5e15199401aecb76ef551e52f6dcff
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712880"
---
# <a name="assertqubitwithintolerance-operation"></a><span data-ttu-id="9ab11-102">AssertQubitWithinTolerance, operacja</span><span class="sxs-lookup"><span data-stu-id="9ab11-102">AssertQubitWithinTolerance operation</span></span>

<span data-ttu-id="9ab11-103">Przestrzeń nazw: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="9ab11-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="9ab11-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9ab11-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9ab11-105">Potwierdza, że qubit `q` znajduje się w oczekiwanej eigenstate operatora Pauli z do danej tolerancji.</span><span class="sxs-lookup"><span data-stu-id="9ab11-105">Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator up to a given tolerance.</span></span>

```qsharp
operation AssertQubitWithinTolerance (expected : Result, q : Qubit, tolerance : Double) : Unit
```


## <a name="input"></a><span data-ttu-id="9ab11-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="9ab11-106">Input</span></span>

### <a name="expected--__invalidresult__"></a><span data-ttu-id="9ab11-107">Oczekiwano __: <Result> nieprawidłowe__</span><span class="sxs-lookup"><span data-stu-id="9ab11-107">expected : __invalid<Result>__</span></span>

<span data-ttu-id="9ab11-108">Który stan qubit powinien znajdować się w: `Zero` lub `One` .</span><span class="sxs-lookup"><span data-stu-id="9ab11-108">Which state the qubit is expected to be in: `Zero` or `One`.</span></span>


### <a name="q--qubit"></a><span data-ttu-id="9ab11-109">p: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="9ab11-109">q : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="9ab11-110">Qubit, którego stan jest potwierdzony.</span><span class="sxs-lookup"><span data-stu-id="9ab11-110">The qubit whose state is asserted.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="9ab11-111">Tolerancja: [Podwójna precyzja](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="9ab11-111">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="9ab11-112">Tolerancja prawdopodobieństwa pomiaru qubit zwraca oczekiwany wynik.</span><span class="sxs-lookup"><span data-stu-id="9ab11-112">Tolerance on the probability of a measurement of the qubit returning the expected result.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9ab11-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9ab11-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="9ab11-114">Uwagi</span><span class="sxs-lookup"><span data-stu-id="9ab11-114">Remarks</span></span>

<span data-ttu-id="9ab11-115"><xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> Umożliwia potwierdzenie dowolnego stanu qubit, a nie tylko $Z $ eigenstates.</span><span class="sxs-lookup"><span data-stu-id="9ab11-115"><xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> allows for asserting arbitrary qubit states rather than only $Z$ eigenstates.</span></span>

## <a name="see-also"></a><span data-ttu-id="9ab11-116">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="9ab11-116">See Also</span></span>

- [<span data-ttu-id="9ab11-117">Microsoft. Quantum. Diagnostics. AssertQubitIsInStateWithinTolerance</span><span class="sxs-lookup"><span data-stu-id="9ab11-117">Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance)