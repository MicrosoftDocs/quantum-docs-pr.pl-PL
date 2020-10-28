---
uid: Microsoft.Quantum.Characterization.EstimateOverlapBetweenStates
title: EstimateOverlapBetweenStates, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateOverlapBetweenStates
qsharp.summary: Given two operations which each prepare copies of a state, estimates the squared overlap between the states prepared by each operation.
ms.openlocfilehash: 58a367c7ff7d13ac5c1eb1588fb8dac66414776c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714994"
---
# <a name="estimateoverlapbetweenstates-operation"></a><span data-ttu-id="ff36b-102">EstimateOverlapBetweenStates, operacja</span><span class="sxs-lookup"><span data-stu-id="ff36b-102">EstimateOverlapBetweenStates operation</span></span>

<span data-ttu-id="ff36b-103">Przestrzeń nazw: [Microsoft. Quantum. charakteryzującą](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="ff36b-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="ff36b-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ff36b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ff36b-105">W przypadku dwóch operacji, które każda przygotowuje kopie stanu, szacuje kwadratowe nakładanie się między Stanami przygotowanymi przez poszczególne operacje.</span><span class="sxs-lookup"><span data-stu-id="ff36b-105">Given two operations which each prepare copies of a state, estimates the squared overlap between the states prepared by each operation.</span></span>

```qsharp
operation EstimateOverlapBetweenStates (preparation1 : (Qubit[] => Unit is Adj), preparation2 : (Qubit[] => Unit is Adj), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a><span data-ttu-id="ff36b-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="ff36b-106">Input</span></span>

### <a name="preparation1--qubit--unit-adj"></a><span data-ttu-id="ff36b-107">preparation1: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => korekta [jednostki](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ff36b-107">preparation1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="ff36b-108">Pierwszy z dwóch operacji przygotowania stanu do porównania.</span><span class="sxs-lookup"><span data-stu-id="ff36b-108">The first of the two state preparation operations to be compared.</span></span>


### <a name="preparation2--qubit--unit-adj"></a><span data-ttu-id="ff36b-109">preparation2: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => korekta [jednostki](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ff36b-109">preparation2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="ff36b-110">Druga z dwóch operacji przygotowania stanu do porównania.</span><span class="sxs-lookup"><span data-stu-id="ff36b-110">The second of the two state preparation operations to be compared.</span></span>


### <a name="nqubits--int"></a><span data-ttu-id="ff36b-111">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ff36b-111">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ff36b-112">Liczba qubits, na których `commonPreparation` , `preparation1` i `preparation2` wszystkie działania.</span><span class="sxs-lookup"><span data-stu-id="ff36b-112">The number of qubits on which `commonPreparation`, `preparation1`, and `preparation2` all act.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="ff36b-113">nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ff36b-113">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ff36b-114">Liczba pomiarów do użycia podczas szacowania nakładania się.</span><span class="sxs-lookup"><span data-stu-id="ff36b-114">The number of measurements to use in estimating the overlap.</span></span>



## <a name="output--double"></a><span data-ttu-id="ff36b-115">Dane wyjściowe: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ff36b-115">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="remarks"></a><span data-ttu-id="ff36b-116">Uwagi</span><span class="sxs-lookup"><span data-stu-id="ff36b-116">Remarks</span></span>

<span data-ttu-id="ff36b-117">Ta operacja używa testu wymiany do znajdowania $ $ \begin{align} \left | \braket{00\cdots 0 | V ^ {\dagger} U | 00 \ cdots 0} \right | ^ 2 \end{align} $ $, gdzie $U $ jest reprezentacją jednostkową akcji `preparation1` i gdzie $V $ odpowiada `preparation2` .</span><span class="sxs-lookup"><span data-stu-id="ff36b-117">This operation uses the SWAP test to find $$ \begin{align} \left| \braket{00\cdots 0 | V^{\dagger} U | 00\cdots 0} \right|^2 \end{align} $$ where $U$ is the unitary representation of the action of `preparation1`, and where $V$ corresponds to `preparation2`.</span></span>

## <a name="see-also"></a><span data-ttu-id="ff36b-118">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="ff36b-118">See Also</span></span>

- [<span data-ttu-id="ff36b-119">Microsoft. Quantum. charakteryzującą. EstimateRealOverlapBetweenStates</span><span class="sxs-lookup"><span data-stu-id="ff36b-119">Microsoft.Quantum.Characterization.EstimateRealOverlapBetweenStates</span></span>](xref:Microsoft.Quantum.Characterization.EstimateRealOverlapBetweenStates)
- [<span data-ttu-id="ff36b-120">Microsoft. Quantum. charakteryzującą. EstimateImagOverlapBetweenStates</span><span class="sxs-lookup"><span data-stu-id="ff36b-120">Microsoft.Quantum.Characterization.EstimateImagOverlapBetweenStates</span></span>](xref:Microsoft.Quantum.Characterization.EstimateImagOverlapBetweenStates)