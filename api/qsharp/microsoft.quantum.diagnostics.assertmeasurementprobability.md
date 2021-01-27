---
uid: Microsoft.Quantum.Diagnostics.AssertMeasurementProbability
title: AssertMeasurementProbability, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertMeasurementProbability
qsharp.summary: Asserts that measuring the given qubits in the given Pauli basis will have the given result with the given probability, within some tolerance.
ms.openlocfilehash: 2fd89121516ef6994dedb75b214589b4e360ff8b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98830818"
---
# <a name="assertmeasurementprobability-operation"></a><span data-ttu-id="1dc39-102">AssertMeasurementProbability, operacja</span><span class="sxs-lookup"><span data-stu-id="1dc39-102">AssertMeasurementProbability operation</span></span>

<span data-ttu-id="1dc39-103">Przestrzeń nazw: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="1dc39-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="1dc39-104">Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="1dc39-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="1dc39-105">Potwierdzenia, które mierzą podaną qubits w danej Pauli, będą miały wynik z określonym prawdopodobieństwem, w granicach tolerancji.</span><span class="sxs-lookup"><span data-stu-id="1dc39-105">Asserts that measuring the given qubits in the given Pauli basis will have the given result with the given probability, within some tolerance.</span></span>

```qsharp
operation AssertMeasurementProbability (bases : Pauli[], qubits : Qubit[], result : Result, prob : Double, msg : String, tol : Double) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="1dc39-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="1dc39-106">Input</span></span>

### <a name="bases--pauli"></a><span data-ttu-id="1dc39-107">bazy: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="1dc39-107">bases : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="1dc39-108">Efekt pomiaru, który pozwala uzyskać prawdopodobieństwo wystąpienia wartości, wyrażony jako operator qubit Pauli.</span><span class="sxs-lookup"><span data-stu-id="1dc39-108">A measurement effect to assert the probability of, expressed as a multi-qubit Pauli operator.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="1dc39-109">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="1dc39-109">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="1dc39-110">Rejestr, na którym należy wykonać potwierdzenie.</span><span class="sxs-lookup"><span data-stu-id="1dc39-110">A register on which to make the assertion.</span></span>


### <a name="result--__invalidresult__"></a><span data-ttu-id="1dc39-111">wynik: __nieprawidłowe <Result>__</span><span class="sxs-lookup"><span data-stu-id="1dc39-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="1dc39-112">Oczekiwany wynik `Measure(bases, qubits)` .</span><span class="sxs-lookup"><span data-stu-id="1dc39-112">An expected result of `Measure(bases, qubits)`.</span></span>


### <a name="prob--double"></a><span data-ttu-id="1dc39-113">funkcja PRAWDPD: [Podwójna](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="1dc39-113">prob : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="1dc39-114">Prawdopodobieństwo, z którym jest oczekiwany dany wynik.</span><span class="sxs-lookup"><span data-stu-id="1dc39-114">The probability with which the given result is expected.</span></span>


### <a name="msg--string"></a><span data-ttu-id="1dc39-115">msg: [ciąg](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="1dc39-115">msg : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="1dc39-116">Komunikat, który ma być raportowany, jeśli potwierdzenie nie powiedzie się.</span><span class="sxs-lookup"><span data-stu-id="1dc39-116">A message to be reported if the assertion fails.</span></span>


### <a name="tol--double"></a><span data-ttu-id="1dc39-117">stosowanie: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="1dc39-117">tol : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>





## <a name="output--unit"></a><span data-ttu-id="1dc39-118">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1dc39-118">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="1dc39-119">Przykład</span><span class="sxs-lookup"><span data-stu-id="1dc39-119">Example</span></span>

```qsharp
using (register = Qubit()) {
    H(register);
    AssertProb([PauliZ], [register], One, 0.5,
        "Measuring in conjugate basis did not give 50/50 results.", 1e-5);
}
```

## <a name="remarks"></a><span data-ttu-id="1dc39-120">Uwagi</span><span class="sxs-lookup"><span data-stu-id="1dc39-120">Remarks</span></span>

<span data-ttu-id="1dc39-121">Należy zauważyć, że sąsiadujące i kontrolowane wersje tej operacji nie będą sprawdzać warunku.</span><span class="sxs-lookup"><span data-stu-id="1dc39-121">Note that the Adjoint and Controlled versions of this operation will not check the condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="1dc39-122">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="1dc39-122">See Also</span></span>

- [<span data-ttu-id="1dc39-123">Microsoft. Quantum. Diagnostics. AssertMeasurement</span><span class="sxs-lookup"><span data-stu-id="1dc39-123">Microsoft.Quantum.Diagnostics.AssertMeasurement</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertMeasurement)