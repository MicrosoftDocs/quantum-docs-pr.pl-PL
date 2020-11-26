---
uid: Microsoft.Quantum.Diagnostics.AssertMeasurement
title: AssertMeasurement, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertMeasurement
qsharp.summary: Asserts that measuring the given qubits in the given Pauli basis will always have the given result.
ms.openlocfilehash: 3fbe000202abbd8a206b0c83dfa35f4546ea91cf
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202451"
---
# <a name="assertmeasurement-operation"></a><span data-ttu-id="a5a70-102">AssertMeasurement, operacja</span><span class="sxs-lookup"><span data-stu-id="a5a70-102">AssertMeasurement operation</span></span>

<span data-ttu-id="a5a70-103">Przestrzeń nazw: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="a5a70-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="a5a70-104">Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="a5a70-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="a5a70-105">Potwierdzenia, które mierzą podaną qubits w danej Pauli, będą mieć zawsze określony wynik.</span><span class="sxs-lookup"><span data-stu-id="a5a70-105">Asserts that measuring the given qubits in the given Pauli basis will always have the given result.</span></span>

```qsharp
operation AssertMeasurement (bases : Pauli[], qubits : Qubit[], result : Result, msg : String) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="a5a70-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="a5a70-106">Input</span></span>

### <a name="bases--pauli"></a><span data-ttu-id="a5a70-107">bazy: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="a5a70-107">bases : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="a5a70-108">Efekt pomiaru, który pozwala uzyskać prawdopodobieństwo wystąpienia wartości, wyrażony jako operator qubit Pauli.</span><span class="sxs-lookup"><span data-stu-id="a5a70-108">A measurement effect to assert the probability of, expressed as a multi-qubit Pauli operator.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="a5a70-109">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="a5a70-109">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="a5a70-110">Rejestr, na którym należy wykonać potwierdzenie.</span><span class="sxs-lookup"><span data-stu-id="a5a70-110">A register on which to make the assertion.</span></span>


### <a name="result--__invalidresult__"></a><span data-ttu-id="a5a70-111">wynik: __nieprawidłowe <Result>__</span><span class="sxs-lookup"><span data-stu-id="a5a70-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="a5a70-112">Oczekiwany wynik `Measure(bases, qubits)` .</span><span class="sxs-lookup"><span data-stu-id="a5a70-112">The expected result of `Measure(bases, qubits)`.</span></span>


### <a name="msg--string"></a><span data-ttu-id="a5a70-113">msg: [ciąg](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="a5a70-113">msg : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="a5a70-114">Komunikat, który ma być raportowany, jeśli potwierdzenie nie powiedzie się.</span><span class="sxs-lookup"><span data-stu-id="a5a70-114">A message to be reported if the assertion fails.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a5a70-115">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a5a70-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="a5a70-116">Uwagi</span><span class="sxs-lookup"><span data-stu-id="a5a70-116">Remarks</span></span>

<span data-ttu-id="a5a70-117">Należy zauważyć, że sąsiadujące i kontrolowane wersje tej operacji nie będą sprawdzać warunku.</span><span class="sxs-lookup"><span data-stu-id="a5a70-117">Note that the Adjoint and Controlled versions of this operation will not check the condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="a5a70-118">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="a5a70-118">See Also</span></span>

- [<span data-ttu-id="a5a70-119">Microsoft. Quantum. Diagnostics. AssertMeasurementProbability</span><span class="sxs-lookup"><span data-stu-id="a5a70-119">Microsoft.Quantum.Diagnostics.AssertMeasurementProbability</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability)