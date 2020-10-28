---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.EstimateTermExpectation
title: EstimateTermExpectation, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: EstimateTermExpectation
qsharp.summary: Computes the energy associated to a given Jordan-Wigner Hamiltonian term
ms.openlocfilehash: ef689c55f966e63a2ab8bcdccf99d9cb5e6d3a4d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713729"
---
# <a name="estimatetermexpectation-operation"></a><span data-ttu-id="0b6ee-102">EstimateTermExpectation, operacja</span><span class="sxs-lookup"><span data-stu-id="0b6ee-102">EstimateTermExpectation operation</span></span>

<span data-ttu-id="0b6ee-103">Przestrzeń nazw: [Microsoft. Quantum. Chemia. JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span><span class="sxs-lookup"><span data-stu-id="0b6ee-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span></span>

<span data-ttu-id="0b6ee-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0b6ee-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0b6ee-105">Oblicza energię skojarzoną z danym Jordan-Wigner termin hamiltonian</span><span class="sxs-lookup"><span data-stu-id="0b6ee-105">Computes the energy associated to a given Jordan-Wigner Hamiltonian term</span></span>

```qsharp
operation EstimateTermExpectation (inputStateUnitary : (Qubit[] => Unit is Adj), ops : Pauli[][], coeffs : Double[], nQubits : Int, nSamples : Int) : Double
```


## <a name="description"></a><span data-ttu-id="0b6ee-106">Opis</span><span class="sxs-lookup"><span data-stu-id="0b6ee-106">Description</span></span>

<span data-ttu-id="0b6ee-107">Ta operacja szacuje wartość oczekiwaną skojarzoną z każdym operatorem pomiaru i mnoży ją przez odpowiedni współczynnik przy użyciu próbkowania.</span><span class="sxs-lookup"><span data-stu-id="0b6ee-107">This operation estimates the expectation value associated to each measurement operator and multiplies it by the corresponding coefficient, using sampling.</span></span>
<span data-ttu-id="0b6ee-108">Wyniki są agregowane do zmiennej zawierającej energię Jordan-Wignerego okresu.</span><span class="sxs-lookup"><span data-stu-id="0b6ee-108">The results are aggregated into a variable containing the energy of the Jordan-Wigner term.</span></span>

## <a name="input"></a><span data-ttu-id="0b6ee-109">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="0b6ee-109">Input</span></span>

### <a name="inputstateunitary--qubit--unit-adj"></a><span data-ttu-id="0b6ee-110">inputStateUnitary: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => korekta [jednostki](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0b6ee-110">inputStateUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="0b6ee-111">Jednostka użyta do przygotowania stanu.</span><span class="sxs-lookup"><span data-stu-id="0b6ee-111">The unitary used for state preparation.</span></span>


### <a name="ops--pauli"></a><span data-ttu-id="0b6ee-112">Ops: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="0b6ee-112">ops : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="0b6ee-113">Operatory pomiarów Jordan-Wigner warunku.</span><span class="sxs-lookup"><span data-stu-id="0b6ee-113">The measurement operators of the Jordan-Wigner term.</span></span>


### <a name="coeffs--double"></a><span data-ttu-id="0b6ee-114">coeffs: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="0b6ee-114">coeffs : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="0b6ee-115">Współczynniki Jordan-Wigner warunku.</span><span class="sxs-lookup"><span data-stu-id="0b6ee-115">The coefficients of the Jordan-Wigner term.</span></span>


### <a name="nqubits--int"></a><span data-ttu-id="0b6ee-116">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0b6ee-116">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0b6ee-117">Liczba qubits wymaganych do symulowania systemu cząsteczkowego.</span><span class="sxs-lookup"><span data-stu-id="0b6ee-117">The number of qubits required to simulate the molecular system.</span></span>


### <a name="nsamples--int"></a><span data-ttu-id="0b6ee-118">nSamples: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0b6ee-118">nSamples : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0b6ee-119">Liczba próbek do użycia podczas szacowania terminu.</span><span class="sxs-lookup"><span data-stu-id="0b6ee-119">The number of samples to use for the estimation of the term expectation.</span></span>



## <a name="output--double"></a><span data-ttu-id="0b6ee-120">Dane wyjściowe: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="0b6ee-120">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="0b6ee-121">Energia skojarzona z terminem Jordan-Wigner.</span><span class="sxs-lookup"><span data-stu-id="0b6ee-121">The energy associated to the Jordan-Wigner term.</span></span>