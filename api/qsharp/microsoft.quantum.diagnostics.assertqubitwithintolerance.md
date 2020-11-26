---
uid: Microsoft.Quantum.Diagnostics.AssertQubitWithinTolerance
title: AssertQubitWithinTolerance, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertQubitWithinTolerance
qsharp.summary: Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator up to a given tolerance.
ms.openlocfilehash: 56b7f93f33ae18146c1fb13d404fc1d119eee72e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202196"
---
# <a name="assertqubitwithintolerance-operation"></a><span data-ttu-id="46655-102">AssertQubitWithinTolerance, operacja</span><span class="sxs-lookup"><span data-stu-id="46655-102">AssertQubitWithinTolerance operation</span></span>

<span data-ttu-id="46655-103">Przestrzeń nazw: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="46655-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="46655-104">Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="46655-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="46655-105">Potwierdza, że qubit `q` znajduje się w oczekiwanej eigenstate operatora Pauli z do danej tolerancji.</span><span class="sxs-lookup"><span data-stu-id="46655-105">Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator up to a given tolerance.</span></span>

```qsharp
operation AssertQubitWithinTolerance (expected : Result, q : Qubit, tolerance : Double) : Unit
```


## <a name="input"></a><span data-ttu-id="46655-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="46655-106">Input</span></span>

### <a name="expected--__invalidresult__"></a><span data-ttu-id="46655-107">Oczekiwano __: <Result> nieprawidłowe__</span><span class="sxs-lookup"><span data-stu-id="46655-107">expected : __invalid<Result>__</span></span>

<span data-ttu-id="46655-108">Który stan qubit powinien znajdować się w: `Zero` lub `One` .</span><span class="sxs-lookup"><span data-stu-id="46655-108">Which state the qubit is expected to be in: `Zero` or `One`.</span></span>


### <a name="q--qubit"></a><span data-ttu-id="46655-109">p: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="46655-109">q : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="46655-110">Qubit, którego stan jest potwierdzony.</span><span class="sxs-lookup"><span data-stu-id="46655-110">The qubit whose state is asserted.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="46655-111">Tolerancja: [Podwójna precyzja](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="46655-111">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="46655-112">Tolerancja prawdopodobieństwa pomiaru qubit zwraca oczekiwany wynik.</span><span class="sxs-lookup"><span data-stu-id="46655-112">Tolerance on the probability of a measurement of the qubit returning the expected result.</span></span>



## <a name="output--unit"></a><span data-ttu-id="46655-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="46655-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="46655-114">Uwagi</span><span class="sxs-lookup"><span data-stu-id="46655-114">Remarks</span></span>

<span data-ttu-id="46655-115"><xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> Umożliwia potwierdzenie dowolnego stanu qubit, a nie tylko $Z $ eigenstates.</span><span class="sxs-lookup"><span data-stu-id="46655-115"><xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> allows for asserting arbitrary qubit states rather than only $Z$ eigenstates.</span></span>

## <a name="see-also"></a><span data-ttu-id="46655-116">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="46655-116">See Also</span></span>

- [<span data-ttu-id="46655-117">Microsoft. Quantum. Diagnostics. AssertQubitIsInStateWithinTolerance</span><span class="sxs-lookup"><span data-stu-id="46655-117">Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance)