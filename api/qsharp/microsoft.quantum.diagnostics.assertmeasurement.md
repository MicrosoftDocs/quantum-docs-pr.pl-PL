---
uid: Microsoft.Quantum.Diagnostics.AssertMeasurement
title: AssertMeasurement, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertMeasurement
qsharp.summary: Asserts that measuring the given qubits in the given Pauli basis will always have the given result.
ms.openlocfilehash: 09024cd8cd6e713360dcf7f42f55941590f35883
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713034"
---
# <a name="assertmeasurement-operation"></a><span data-ttu-id="2bb46-102">AssertMeasurement, operacja</span><span class="sxs-lookup"><span data-stu-id="2bb46-102">AssertMeasurement operation</span></span>

<span data-ttu-id="2bb46-103">Przestrzeń nazw: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="2bb46-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="2bb46-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2bb46-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2bb46-105">Potwierdzenia, które mierzą podaną qubits w danej Pauli, będą mieć zawsze określony wynik.</span><span class="sxs-lookup"><span data-stu-id="2bb46-105">Asserts that measuring the given qubits in the given Pauli basis will always have the given result.</span></span>

```qsharp
operation AssertMeasurement (bases : Pauli[], qubits : Qubit[], result : Result, msg : String) : Unit
```


## <a name="input"></a><span data-ttu-id="2bb46-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="2bb46-106">Input</span></span>

### <a name="bases--pauli"></a><span data-ttu-id="2bb46-107">bazy: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="2bb46-107">bases : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="2bb46-108">Efekt pomiaru, który pozwala uzyskać prawdopodobieństwo wystąpienia wartości, wyrażony jako operator qubit Pauli.</span><span class="sxs-lookup"><span data-stu-id="2bb46-108">A measurement effect to assert the probability of, expressed as a multi-qubit Pauli operator.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="2bb46-109">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="2bb46-109">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="2bb46-110">Rejestr, na którym należy wykonać potwierdzenie.</span><span class="sxs-lookup"><span data-stu-id="2bb46-110">A register on which to make the assertion.</span></span>


### <a name="result--__invalidresult__"></a><span data-ttu-id="2bb46-111">wynik: __nieprawidłowe <Result>__</span><span class="sxs-lookup"><span data-stu-id="2bb46-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="2bb46-112">Oczekiwany wynik `Measure(bases, qubits)` .</span><span class="sxs-lookup"><span data-stu-id="2bb46-112">The expected result of `Measure(bases, qubits)`.</span></span>


### <a name="msg--string"></a><span data-ttu-id="2bb46-113">msg: [ciąg](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="2bb46-113">msg : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="2bb46-114">Komunikat, który ma być raportowany, jeśli potwierdzenie nie powiedzie się.</span><span class="sxs-lookup"><span data-stu-id="2bb46-114">A message to be reported if the assertion fails.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2bb46-115">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2bb46-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="2bb46-116">Uwagi</span><span class="sxs-lookup"><span data-stu-id="2bb46-116">Remarks</span></span>

<span data-ttu-id="2bb46-117">Należy zauważyć, że sąsiadujące i kontrolowane wersje tej operacji nie będą sprawdzać warunku.</span><span class="sxs-lookup"><span data-stu-id="2bb46-117">Note that the Adjoint and Controlled versions of this operation will not check the condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="2bb46-118">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="2bb46-118">See Also</span></span>

- [<span data-ttu-id="2bb46-119">Microsoft. Quantum. Diagnostics. AssertMeasurementProbability</span><span class="sxs-lookup"><span data-stu-id="2bb46-119">Microsoft.Quantum.Diagnostics.AssertMeasurementProbability</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability)