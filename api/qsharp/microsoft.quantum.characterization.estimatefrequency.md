---
uid: Microsoft.Quantum.Characterization.EstimateFrequency
title: EstimateFrequency, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateFrequency
qsharp.summary: Given a preparation and measurement, estimates the frequency with which that measurement succeeds (returns `Zero`) by performing a given number of trials.
ms.openlocfilehash: 83589637a7bfa328812207271844411f57d42097
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715087"
---
# <a name="estimatefrequency-operation"></a><span data-ttu-id="53d6d-102">EstimateFrequency, operacja</span><span class="sxs-lookup"><span data-stu-id="53d6d-102">EstimateFrequency operation</span></span>

<span data-ttu-id="53d6d-103">Przestrzeń nazw: [Microsoft. Quantum. charakteryzującą](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="53d6d-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="53d6d-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="53d6d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="53d6d-105">Mając na celu przygotowanie i pomiar, szacuje częstotliwość, z jaką pomiar zakończy się powodzeniem (zwraca `Zero` ), wykonując daną liczbę prób.</span><span class="sxs-lookup"><span data-stu-id="53d6d-105">Given a preparation and measurement, estimates the frequency with which that measurement succeeds (returns `Zero`) by performing a given number of trials.</span></span>

```qsharp
operation EstimateFrequency (preparation : (Qubit[] => Unit), measurement : (Qubit[] => Result), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a><span data-ttu-id="53d6d-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="53d6d-106">Input</span></span>

### <a name="preparation--qubit--unit"></a><span data-ttu-id="53d6d-107">Przygotowanie: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [Jednostka](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="53d6d-107">preparation : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="53d6d-108">Operacja $P $, która przygotowuje dane stanu $ \rho $ w rejestrze wejściowym.</span><span class="sxs-lookup"><span data-stu-id="53d6d-108">An operation $P$ that prepares a given state $\rho$ on its input register.</span></span>


### <a name="measurement--qubit--__invalidresult__"></a><span data-ttu-id="53d6d-109">Pomiar: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => __nieprawidłowy <Result>__</span><span class="sxs-lookup"><span data-stu-id="53d6d-109">measurement : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => __invalid<Result>__</span></span> 

<span data-ttu-id="53d6d-110">Operacja $M $ reprezentująca miarę zainteresowania.</span><span class="sxs-lookup"><span data-stu-id="53d6d-110">An operation $M$ representing the measurement of interest.</span></span>


### <a name="nqubits--int"></a><span data-ttu-id="53d6d-111">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="53d6d-111">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="53d6d-112">Liczba qubits, na których przygotowanie i pomiar każdego działania.</span><span class="sxs-lookup"><span data-stu-id="53d6d-112">The number of qubits on which the preparation and measurement each act.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="53d6d-113">nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="53d6d-113">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="53d6d-114">Liczba przypadków, w których pomiar ma być wykonywany w celu oszacowania częstotliwości zainteresowania.</span><span class="sxs-lookup"><span data-stu-id="53d6d-114">The number of times that the measurement should be performed in order to estimate the frequency of interest.</span></span>



## <a name="output--double"></a><span data-ttu-id="53d6d-115">Dane wyjściowe: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="53d6d-115">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="53d6d-116">Oszacowanie $ \hat{p} $ częstotliwości, z którą $M (P (\ket{00 \cdots 0} \bra{00 \cdots 0})) $ zwraca `Zero` , uzyskany przy użyciu nieobciążonego dwumianu, szacowania $ \hat{p} = n \_ {\uparrow}/n \_ {\Text{measurements}} $, gdzie $n \_ {\uparrow} $ to liczba `Zero` zaobserwowanych wyników.</span><span class="sxs-lookup"><span data-stu-id="53d6d-116">An estimate $\hat{p}$ of the frequency with which $M(P(\ket{00 \cdots 0}\bra{00 \cdots 0}))$ returns `Zero`, obtained using the unbiased binomial estimator $\hat{p} = n\_{\uparrow} / n\_{\text{measurements}}$, where $n\_{\uparrow}$ is the number of `Zero` results observed.</span></span>

<span data-ttu-id="53d6d-117">Jest to szczególnie ważne w przypadku maszyn docelowych, które respektują ograniczenia fizyczne, tak że nie można mierzyć prawdopodobieństwa.</span><span class="sxs-lookup"><span data-stu-id="53d6d-117">This is particularly important on target machines which respect physical limitations, such that probabilities cannot be measured.</span></span>