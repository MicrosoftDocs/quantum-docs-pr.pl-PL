---
uid: Microsoft.Quantum.Diagnostics.AssertQubit
title: AssertQubit, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertQubit
qsharp.summary: Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator.
ms.openlocfilehash: 0e005230427bbd570133712679c51661e7ae6496
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202247"
---
# <a name="assertqubit-operation"></a><span data-ttu-id="d3747-102">AssertQubit, operacja</span><span class="sxs-lookup"><span data-stu-id="d3747-102">AssertQubit operation</span></span>

<span data-ttu-id="d3747-103">Przestrzeń nazw: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="d3747-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="d3747-104">Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="d3747-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="d3747-105">Potwierdza, że qubit `q` znajduje się w oczekiwanej eigenstate operatora Pauli z.</span><span class="sxs-lookup"><span data-stu-id="d3747-105">Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator.</span></span>

```qsharp
operation AssertQubit (expected : Result, q : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="d3747-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="d3747-106">Input</span></span>

### <a name="expected--__invalidresult__"></a><span data-ttu-id="d3747-107">Oczekiwano __: <Result> nieprawidłowe__</span><span class="sxs-lookup"><span data-stu-id="d3747-107">expected : __invalid<Result>__</span></span>

<span data-ttu-id="d3747-108">Który stan qubit powinien znajdować się w: `Zero` lub `One` .</span><span class="sxs-lookup"><span data-stu-id="d3747-108">Which state the qubit is expected to be in: `Zero` or `One`.</span></span>


### <a name="q--qubit"></a><span data-ttu-id="d3747-109">p: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="d3747-109">q : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="d3747-110">Qubit, którego stan jest potwierdzony.</span><span class="sxs-lookup"><span data-stu-id="d3747-110">The qubit whose state is asserted.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d3747-111">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d3747-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="d3747-112">Uwagi</span><span class="sxs-lookup"><span data-stu-id="d3747-112">Remarks</span></span>

<span data-ttu-id="d3747-113"><xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> Umożliwia potwierdzenie dowolnego stanu qubit, a nie tylko $Z $ eigenstates.</span><span class="sxs-lookup"><span data-stu-id="d3747-113"><xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> allows for asserting arbitrary qubit states rather than only $Z$ eigenstates.</span></span>

## <a name="see-also"></a><span data-ttu-id="d3747-114">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="d3747-114">See Also</span></span>

- [<span data-ttu-id="d3747-115">Microsoft. Quantum. Diagnostics. AssertQubitIsInStateWithinTolerance</span><span class="sxs-lookup"><span data-stu-id="d3747-115">Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance)