---
uid: Microsoft.Quantum.Characterization.EstimateImagOverlapBetweenStates
title: EstimateImagOverlapBetweenStates, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateImagOverlapBetweenStates
qsharp.summary: Given two operations which each prepare copies of a state, estimates the imaginary part of the overlap between the states prepared by each operation.
ms.openlocfilehash: 8b73115c3243c594897ac4b309ec52d5e9863d26
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715045"
---
# <a name="estimateimagoverlapbetweenstates-operation"></a><span data-ttu-id="4a0e8-102">EstimateImagOverlapBetweenStates, operacja</span><span class="sxs-lookup"><span data-stu-id="4a0e8-102">EstimateImagOverlapBetweenStates operation</span></span>

<span data-ttu-id="4a0e8-103">Przestrzeń nazw: [Microsoft. Quantum. charakteryzującą](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="4a0e8-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="4a0e8-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4a0e8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4a0e8-105">Dwie operacje, które każda przygotowuje kopie stanu, oceniają część urojoną nakładania się między Stanami przygotowanymi przez poszczególne operacje.</span><span class="sxs-lookup"><span data-stu-id="4a0e8-105">Given two operations which each prepare copies of a state, estimates the imaginary part of the overlap between the states prepared by each operation.</span></span>

```qsharp
operation EstimateImagOverlapBetweenStates (commonPreparation : (Qubit[] => Unit is Adj), preparation1 : (Qubit[] => Unit is Adj + Ctl), preparation2 : (Qubit[] => Unit is Adj + Ctl), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a><span data-ttu-id="4a0e8-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="4a0e8-106">Input</span></span>

### <a name="commonpreparation--qubit--unit-adj"></a><span data-ttu-id="4a0e8-107">commonPreparation: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => korekta [jednostki](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4a0e8-107">commonPreparation : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="4a0e8-108">Operacja, która przygotowuje stały stan wejściowy.</span><span class="sxs-lookup"><span data-stu-id="4a0e8-108">An operation that prepares a fixed input state.</span></span>


### <a name="preparation1--qubit--unit-adj--ctl"></a><span data-ttu-id="4a0e8-109">preparation1: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => skorygowanie [jednostki](xref:microsoft.quantum.lang-ref.unit) + CTL</span><span class="sxs-lookup"><span data-stu-id="4a0e8-109">preparation1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="4a0e8-110">Pierwszy z dwóch operacji przygotowania stanu do porównania.</span><span class="sxs-lookup"><span data-stu-id="4a0e8-110">The first of the two state preparation operations to be compared.</span></span>


### <a name="preparation2--qubit--unit-adj--ctl"></a><span data-ttu-id="4a0e8-111">preparation2: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => skorygowanie [jednostki](xref:microsoft.quantum.lang-ref.unit) + CTL</span><span class="sxs-lookup"><span data-stu-id="4a0e8-111">preparation2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="4a0e8-112">Druga z dwóch operacji przygotowania stanu do porównania.</span><span class="sxs-lookup"><span data-stu-id="4a0e8-112">The second of the two state preparation operations to be compared.</span></span>


### <a name="nqubits--int"></a><span data-ttu-id="4a0e8-113">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4a0e8-113">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4a0e8-114">Liczba qubits, na których `commonPreparation` , `preparation1` i `preparation2` wszystkie działania.</span><span class="sxs-lookup"><span data-stu-id="4a0e8-114">The number of qubits on which `commonPreparation`, `preparation1`, and `preparation2` all act.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="4a0e8-115">nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4a0e8-115">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4a0e8-116">Liczba pomiarów do użycia podczas szacowania nakładania się.</span><span class="sxs-lookup"><span data-stu-id="4a0e8-116">The number of measurements to use in estimating the overlap.</span></span>



## <a name="output--double"></a><span data-ttu-id="4a0e8-117">Dane wyjściowe: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="4a0e8-117">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="remarks"></a><span data-ttu-id="4a0e8-118">Uwagi</span><span class="sxs-lookup"><span data-stu-id="4a0e8-118">Remarks</span></span>

<span data-ttu-id="4a0e8-119">Ta operacja używa testu Hadamard, aby znaleźć część urojoną $ $ \begin{align} \braket{\psi | V ^ {\dagger} U | \psi} \end{align} $ $, gdzie $ \ket{\psi} $ jest stanem przygotowanym przez `commonPreparation` , $U $ jest reprezentacją jednostkową akcji `preparation1` i gdzie $V $ odpowiada `preparation2` .</span><span class="sxs-lookup"><span data-stu-id="4a0e8-119">This operation uses the Hadamard test to find the imaginary part of $$ \begin{align} \braket{\psi | V^{\dagger} U | \psi} \end{align} $$ where $\ket{\psi}$ is the state prepared by `commonPreparation`, $U$ is the unitary representation of the action of `preparation1`, and where $V$ corresponds to `preparation2`.</span></span>

## <a name="references"></a><span data-ttu-id="4a0e8-120">Dokumentacja</span><span class="sxs-lookup"><span data-stu-id="4a0e8-120">References</span></span>

- <span data-ttu-id="4a0e8-121">Aharonov *et al.* [Quant-pH/0511096](https://arxiv.org/abs/quant-ph/0511096).</span><span class="sxs-lookup"><span data-stu-id="4a0e8-121">Aharonov *et al.* [quant-ph/0511096](https://arxiv.org/abs/quant-ph/0511096).</span></span>

## <a name="see-also"></a><span data-ttu-id="4a0e8-122">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="4a0e8-122">See Also</span></span>

- [<span data-ttu-id="4a0e8-123">Microsoft. Quantum. charakteryzującą. EstimateRealOverlapBetweenStates</span><span class="sxs-lookup"><span data-stu-id="4a0e8-123">Microsoft.Quantum.Characterization.EstimateRealOverlapBetweenStates</span></span>](xref:Microsoft.Quantum.Characterization.EstimateRealOverlapBetweenStates)
- [<span data-ttu-id="4a0e8-124">Microsoft. Quantum. charakteryzującą. EstimateOverlapBetweenStates</span><span class="sxs-lookup"><span data-stu-id="4a0e8-124">Microsoft.Quantum.Characterization.EstimateOverlapBetweenStates</span></span>](xref:Microsoft.Quantum.Characterization.EstimateOverlapBetweenStates)