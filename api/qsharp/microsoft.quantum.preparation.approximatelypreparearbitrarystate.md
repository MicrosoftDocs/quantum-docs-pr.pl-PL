---
uid: Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryState
title: ApproximatelyPrepareArbitraryState, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: ApproximatelyPrepareArbitraryState
qsharp.summary: Given a set of coefficients and a little-endian encoded quantum register, prepares an state on that register described by the given coefficients, up to a given approximation tolerance.
ms.openlocfilehash: 2561b098c5faf2d24bb9ab348fb052025808e441
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724084"
---
# <a name="approximatelypreparearbitrarystate-operation"></a><span data-ttu-id="00336-102">ApproximatelyPrepareArbitraryState, operacja</span><span class="sxs-lookup"><span data-stu-id="00336-102">ApproximatelyPrepareArbitraryState operation</span></span>

<span data-ttu-id="00336-103">Przestrzeń nazw: [Microsoft. Quantum. przygotowaniu](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="00336-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="00336-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="00336-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="00336-105">Uwzględniając zestaw współczynników i zakodowany w formacie Quantum rejestr oparty na little-endian, przygotowuje stan tego rejestru opisany przez podane współczynniki, aż do danej przepuszczalnej tolerancji.</span><span class="sxs-lookup"><span data-stu-id="00336-105">Given a set of coefficients and a little-endian encoded quantum register, prepares an state on that register described by the given coefficients, up to a given approximation tolerance.</span></span>

```qsharp
operation ApproximatelyPrepareArbitraryState (tolerance : Double, coefficients : Microsoft.Quantum.Math.ComplexPolar[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="00336-106">Opis</span><span class="sxs-lookup"><span data-stu-id="00336-106">Description</span></span>

<span data-ttu-id="00336-107">Ta operacja przygotowuje dowolny stan Quantum $ \ket{\psi} $ z złożonymi współdziałami $r _j e ^ {i t_j} $ ze stanu podstawy obliczeń $n $-qubit $ \ket{0 \cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="00336-107">This operation prepares an arbitrary quantum state $\ket{\psi}$ with complex coefficients $r_j e^{i t_j}$ from the $n$-qubit computational basis state $\ket{0 \cdots 0}$.</span></span>
<span data-ttu-id="00336-108">W szczególności Akcja tej operacji może być symulowana przez transformację jednostkową $U $, która działa w stanie "wszystkie zero" jako</span><span class="sxs-lookup"><span data-stu-id="00336-108">In particular, the action of this operation can be simulated by the a unitary transformation $U$ which acts on the all-zeros state as</span></span>

<span data-ttu-id="00336-109">$ $ \begin{align} U\ket {0... 0} & = \ket{\psi} \\ \\ & = \frac{\ sum_ {j = 0} ^ {2 ^ n-1} r_j e ^ {i t_j} \ket{j}} {\sqrt{\ sum_ {j = 0} ^ {2 ^ n-1} | r_j | ^ 2}}.</span><span class="sxs-lookup"><span data-stu-id="00336-109">$$ \begin{align} U\ket{0...0} & = \ket{\psi} \\\\ & = \frac{ \sum_{j=0}^{2^n-1} r_j e^{i t_j} \ket{j} }{ \sqrt{\sum_{j=0}^{2^n-1} |r_j|^2} }.</span></span>
<span data-ttu-id="00336-110">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="00336-110">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="00336-111">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="00336-111">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="00336-112">Tolerancja: [Podwójna precyzja](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="00336-112">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="00336-113">Tolerancja przybliżona, która ma być używana podczas przygotowywania danego stanu.</span><span class="sxs-lookup"><span data-stu-id="00336-113">The approximation tolerance to be used when preparing the given state.</span></span>


### <a name="coefficients--complexpolar"></a><span data-ttu-id="00336-114">współczynniki: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span><span class="sxs-lookup"><span data-stu-id="00336-114">coefficients : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span></span>

<span data-ttu-id="00336-115">Tablica do $2 ^ n $ złożone współczynniki reprezentowane przez ich wartości bezwzględne i fazy $ (r_j, t_j) $.</span><span class="sxs-lookup"><span data-stu-id="00336-115">Array of up to $2^n$ complex coefficients represented by their absolute value and phase $(r_j, t_j)$.</span></span> <span data-ttu-id="00336-116">Współczynnik $j $ th indeksuje stan liczbowy $ \ket{j} $ zakodowany w formacie little-endian.</span><span class="sxs-lookup"><span data-stu-id="00336-116">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="00336-117">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="00336-117">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="00336-118">Qubit rejestruje Stany kodowania w formacie little-endian.</span><span class="sxs-lookup"><span data-stu-id="00336-118">Qubit register encoding number states in little-endian format.</span></span> <span data-ttu-id="00336-119">Oczekuje się, że zostanie ona zainicjowana w stanie bazowym obliczeniowym $ \ket{0...0} $.</span><span class="sxs-lookup"><span data-stu-id="00336-119">This is expected to be initialized in the computational basis state $\ket{0...0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="00336-120">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="00336-120">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="00336-121">Uwagi</span><span class="sxs-lookup"><span data-stu-id="00336-121">Remarks</span></span>

<span data-ttu-id="00336-122">Ujemne współczynniki wejścia $r _j < $0 będą traktowane jako wynik dodatni z wartością $ | r_j | $.</span><span class="sxs-lookup"><span data-stu-id="00336-122">Negative input coefficients $r_j < 0$ will be treated as though positive with value $|r_j|$.</span></span> <span data-ttu-id="00336-123">`coefficients` zostanie uzupełniona o elementy $ (r_j, t_j) = (0,0, 0,0) $, jeśli określono mniej niż $2 ^ n $.</span><span class="sxs-lookup"><span data-stu-id="00336-123">`coefficients` will be padded with elements $(r_j, t_j) = (0.0, 0.0)$ if fewer than $2^n$ are specified.</span></span>

## <a name="references"></a><span data-ttu-id="00336-124">Dokumentacja</span><span class="sxs-lookup"><span data-stu-id="00336-124">References</span></span>

- <span data-ttu-id="00336-125">Synteza obwodów logiki Quantum Vivek V. Shende, Stephen S. Bullock, Igora L. Markov https://arxiv.org/abs/quant-ph/0406176</span><span class="sxs-lookup"><span data-stu-id="00336-125">Synthesis of Quantum Logic Circuits Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span></span>

## <a name="see-also"></a><span data-ttu-id="00336-126">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="00336-126">See Also</span></span>

- [<span data-ttu-id="00336-127">Microsoft. Quantum. przygotowaniu. ApproximatelyPrepareArbitraryState</span><span class="sxs-lookup"><span data-stu-id="00336-127">Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryState</span></span>](xref:Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryState)