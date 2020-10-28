---
uid: Microsoft.Quantum.Diagnostics.AssertMeasurementProbability
title: AssertMeasurementProbability, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertMeasurementProbability
qsharp.summary: Asserts that measuring the given qubits in the given Pauli basis will have the given result with the given probability, within some tolerance.
ms.openlocfilehash: ff0419706d825442492f82e564f1cce86f1b112f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712978"
---
# <a name="assertmeasurementprobability-operation"></a><span data-ttu-id="9b3e4-102">AssertMeasurementProbability, operacja</span><span class="sxs-lookup"><span data-stu-id="9b3e4-102">AssertMeasurementProbability operation</span></span>

<span data-ttu-id="9b3e4-103">Przestrzeń nazw: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="9b3e4-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="9b3e4-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9b3e4-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9b3e4-105">Potwierdzenia, które mierzą podaną qubits w danej Pauli, będą miały wynik z określonym prawdopodobieństwem, w granicach tolerancji.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-105">Asserts that measuring the given qubits in the given Pauli basis will have the given result with the given probability, within some tolerance.</span></span>

```qsharp
operation AssertMeasurementProbability (bases : Pauli[], qubits : Qubit[], result : Result, prob : Double, msg : String, tol : Double) : Unit
```


## <a name="input"></a><span data-ttu-id="9b3e4-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="9b3e4-106">Input</span></span>

### <a name="bases--pauli"></a><span data-ttu-id="9b3e4-107">bazy: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="9b3e4-107">bases : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="9b3e4-108">Efekt pomiaru, który pozwala uzyskać prawdopodobieństwo wystąpienia wartości, wyrażony jako operator qubit Pauli.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-108">A measurement effect to assert the probability of, expressed as a multi-qubit Pauli operator.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="9b3e4-109">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="9b3e4-109">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="9b3e4-110">Rejestr, na którym należy wykonać potwierdzenie.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-110">A register on which to make the assertion.</span></span>


### <a name="result--__invalidresult__"></a><span data-ttu-id="9b3e4-111">wynik: __nieprawidłowe <Result>__</span><span class="sxs-lookup"><span data-stu-id="9b3e4-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="9b3e4-112">Oczekiwany wynik `Measure(bases, qubits)` .</span><span class="sxs-lookup"><span data-stu-id="9b3e4-112">An expected result of `Measure(bases, qubits)`.</span></span>


### <a name="prob--double"></a><span data-ttu-id="9b3e4-113">funkcja PRAWDPD: [Podwójna](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="9b3e4-113">prob : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="9b3e4-114">Prawdopodobieństwo, z którym jest oczekiwany dany wynik.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-114">The probability with which the given result is expected.</span></span>


### <a name="msg--string"></a><span data-ttu-id="9b3e4-115">msg: [ciąg](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="9b3e4-115">msg : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="9b3e4-116">Komunikat, który ma być raportowany, jeśli potwierdzenie nie powiedzie się.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-116">A message to be reported if the assertion fails.</span></span>


### <a name="tol--double"></a><span data-ttu-id="9b3e4-117">stosowanie: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="9b3e4-117">tol : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>





## <a name="output--unit"></a><span data-ttu-id="9b3e4-118">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9b3e4-118">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="9b3e4-119">Uwagi</span><span class="sxs-lookup"><span data-stu-id="9b3e4-119">Remarks</span></span>

<span data-ttu-id="9b3e4-120">Należy zauważyć, że sąsiadujące i kontrolowane wersje tej operacji nie będą sprawdzać warunku.</span><span class="sxs-lookup"><span data-stu-id="9b3e4-120">Note that the Adjoint and Controlled versions of this operation will not check the condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="9b3e4-121">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="9b3e4-121">See Also</span></span>

- [<span data-ttu-id="9b3e4-122">Microsoft. Quantum. Diagnostics. AssertMeasurement</span><span class="sxs-lookup"><span data-stu-id="9b3e4-122">Microsoft.Quantum.Diagnostics.AssertMeasurement</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertMeasurement)