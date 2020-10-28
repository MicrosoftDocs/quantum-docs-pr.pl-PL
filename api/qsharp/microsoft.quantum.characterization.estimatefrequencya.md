---
uid: Microsoft.Quantum.Characterization.EstimateFrequencyA
title: EstimateFrequencyA, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateFrequencyA
qsharp.summary: Given a preparation that is adjointable and measurement, estimates the frequency with which that measurement succeeds (returns `Zero`) by performing a given number of trials.
ms.openlocfilehash: 88f0a237975c158bffcc015f79d2134b210ce83b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715064"
---
# <a name="estimatefrequencya-operation"></a><span data-ttu-id="1b420-102">EstimateFrequencyA, operacja</span><span class="sxs-lookup"><span data-stu-id="1b420-102">EstimateFrequencyA operation</span></span>

<span data-ttu-id="1b420-103">Przestrzeń nazw: [Microsoft. Quantum. charakteryzującą](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="1b420-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="1b420-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1b420-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1b420-105">Na podstawie przygotowania, które jest sąsiednie i pomiarowe, szacuje częstotliwość, z jaką ten pomiar zakończy się powodzeniem (zwraca `Zero` ), wykonując daną liczbę prób.</span><span class="sxs-lookup"><span data-stu-id="1b420-105">Given a preparation that is adjointable and measurement, estimates the frequency with which that measurement succeeds (returns `Zero`) by performing a given number of trials.</span></span>

```qsharp
operation EstimateFrequencyA (preparation : (Qubit[] => Unit is Adj), measurement : (Qubit[] => Result), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a><span data-ttu-id="1b420-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="1b420-106">Input</span></span>

### <a name="preparation--qubit--unit-adj"></a><span data-ttu-id="1b420-107">Przygotowanie: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => korekta [jednostki](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1b420-107">preparation : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="1b420-108">Operacja współdziałania $P $, która przygotowuje dany stan $ \rho $ na swój rejestr wejściowy.</span><span class="sxs-lookup"><span data-stu-id="1b420-108">An adjointable operation $P$ that prepares a given state $\rho$ on its input register.</span></span>


### <a name="measurement--qubit--__invalidresult__"></a><span data-ttu-id="1b420-109">Pomiar: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => __nieprawidłowy <Result>__</span><span class="sxs-lookup"><span data-stu-id="1b420-109">measurement : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => __invalid<Result>__</span></span> 

<span data-ttu-id="1b420-110">Operacja $M $ reprezentująca miarę zainteresowania.</span><span class="sxs-lookup"><span data-stu-id="1b420-110">An operation $M$ representing the measurement of interest.</span></span>


### <a name="nqubits--int"></a><span data-ttu-id="1b420-111">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1b420-111">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1b420-112">Liczba qubits, na których przygotowanie i pomiar każdego działania.</span><span class="sxs-lookup"><span data-stu-id="1b420-112">The number of qubits on which the preparation and measurement each act.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="1b420-113">nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1b420-113">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1b420-114">Liczba przypadków, w których pomiar ma być wykonywany w celu oszacowania częstotliwości zainteresowania.</span><span class="sxs-lookup"><span data-stu-id="1b420-114">The number of times that the measurement should be performed in order to estimate the frequency of interest.</span></span>



## <a name="output--double"></a><span data-ttu-id="1b420-115">Dane wyjściowe: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="1b420-115">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="1b420-116">Oszacowanie $ \hat{p} $ częstotliwości, z którą $M (P (\ket{00 \cdots 0} \bra{00 \cdots 0})) $ zwraca `Zero` , uzyskany przy użyciu nieobciążonego dwumianu, szacowania $ \hat{p} = n \_ {\uparrow}/n \_ {\Text{measurements}} $, gdzie $n \_ {\uparrow} $ to liczba `Zero` zaobserwowanych wyników.</span><span class="sxs-lookup"><span data-stu-id="1b420-116">An estimate $\hat{p}$ of the frequency with which $M(P(\ket{00 \cdots 0}\bra{00 \cdots 0}))$ returns `Zero`, obtained using the unbiased binomial estimator $\hat{p} = n\_{\uparrow} / n\_{\text{measurements}}$, where $n\_{\uparrow}$ is the number of `Zero` results observed.</span></span>

## <a name="remarks"></a><span data-ttu-id="1b420-117">Uwagi</span><span class="sxs-lookup"><span data-stu-id="1b420-117">Remarks</span></span>

<span data-ttu-id="1b420-118">W przypadku operacji współdziałania niektóre założenia mogą zostać wykonane, takie jak wywołanie operacji, przygotuje qubits do tego samego stanu, co umożliwi maszynom docelowym wykonywanie niektórych optymalizacji wydajności.</span><span class="sxs-lookup"><span data-stu-id="1b420-118">For adjointable operations, certain assumptions can be made such like calling the operation will prepare the qubits to exactly the same state, which allow target machines to make some performance optimizations.</span></span>