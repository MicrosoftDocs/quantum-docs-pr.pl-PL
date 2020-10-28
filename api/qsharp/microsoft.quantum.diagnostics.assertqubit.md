---
uid: Microsoft.Quantum.Diagnostics.AssertQubit
title: AssertQubit, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertQubit
qsharp.summary: Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator.
ms.openlocfilehash: fa1f52da5a011cd914a0fda69b78cf5a4fd71e16
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712945"
---
# <a name="assertqubit-operation"></a><span data-ttu-id="90cf7-102">AssertQubit, operacja</span><span class="sxs-lookup"><span data-stu-id="90cf7-102">AssertQubit operation</span></span>

<span data-ttu-id="90cf7-103">Przestrzeń nazw: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="90cf7-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="90cf7-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="90cf7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="90cf7-105">Potwierdza, że qubit `q` znajduje się w oczekiwanej eigenstate operatora Pauli z.</span><span class="sxs-lookup"><span data-stu-id="90cf7-105">Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator.</span></span>

```qsharp
operation AssertQubit (expected : Result, q : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="90cf7-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="90cf7-106">Input</span></span>

### <a name="expected--__invalidresult__"></a><span data-ttu-id="90cf7-107">Oczekiwano __: <Result> nieprawidłowe__</span><span class="sxs-lookup"><span data-stu-id="90cf7-107">expected : __invalid<Result>__</span></span>

<span data-ttu-id="90cf7-108">Który stan qubit powinien znajdować się w: `Zero` lub `One` .</span><span class="sxs-lookup"><span data-stu-id="90cf7-108">Which state the qubit is expected to be in: `Zero` or `One`.</span></span>


### <a name="q--qubit"></a><span data-ttu-id="90cf7-109">p: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="90cf7-109">q : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="90cf7-110">Qubit, którego stan jest potwierdzony.</span><span class="sxs-lookup"><span data-stu-id="90cf7-110">The qubit whose state is asserted.</span></span>



## <a name="output--unit"></a><span data-ttu-id="90cf7-111">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="90cf7-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="90cf7-112">Uwagi</span><span class="sxs-lookup"><span data-stu-id="90cf7-112">Remarks</span></span>

<span data-ttu-id="90cf7-113"><xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> Umożliwia potwierdzenie dowolnego stanu qubit, a nie tylko $Z $ eigenstates.</span><span class="sxs-lookup"><span data-stu-id="90cf7-113"><xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> allows for asserting arbitrary qubit states rather than only $Z$ eigenstates.</span></span>

## <a name="see-also"></a><span data-ttu-id="90cf7-114">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="90cf7-114">See Also</span></span>

- [<span data-ttu-id="90cf7-115">Microsoft. Quantum. Diagnostics. AssertQubitIsInStateWithinTolerance</span><span class="sxs-lookup"><span data-stu-id="90cf7-115">Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance)