---
uid: Microsoft.Quantum.Preparation.PrepareArbitraryState
title: PrepareArbitraryState, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareArbitraryState
qsharp.summary: >-
  > [!WARNING]

  > PrepareArbitraryState has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateCP> instead.


  Given a set of coefficients and a little-endian encoded quantum register, prepares an state on that register described by the given coefficients.
ms.openlocfilehash: 18a1e86f8e110a8f48d7dd50961e1f1f471ffc4e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96190704"
---
# <a name="preparearbitrarystate-operation"></a><span data-ttu-id="8542b-102">PrepareArbitraryState, operacja</span><span class="sxs-lookup"><span data-stu-id="8542b-102">PrepareArbitraryState operation</span></span>

<span data-ttu-id="8542b-103">Przestrzeń nazw: [Microsoft. Quantum. przygotowaniu](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="8542b-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="8542b-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8542b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="8542b-105">PrepareArbitraryState jest przestarzała.</span><span class="sxs-lookup"><span data-stu-id="8542b-105">PrepareArbitraryState has been deprecated.</span></span> <span data-ttu-id="8542b-106">Użyj <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateCP> zamiast tego.</span><span class="sxs-lookup"><span data-stu-id="8542b-106">Please use <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateCP> instead.</span></span>

<span data-ttu-id="8542b-107">Uwzględniając zestaw współczynników i zakodowany w formacie Quantum rejestr oparty na little-endian, przygotowuje stan tego rejestru opisany przez podane współczynniki.</span><span class="sxs-lookup"><span data-stu-id="8542b-107">Given a set of coefficients and a little-endian encoded quantum register, prepares an state on that register described by the given coefficients.</span></span>

```qsharp
operation PrepareArbitraryState (coefficients : Microsoft.Quantum.Math.ComplexPolar[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="8542b-108">Opis</span><span class="sxs-lookup"><span data-stu-id="8542b-108">Description</span></span>

<span data-ttu-id="8542b-109">Ta operacja przygotowuje dowolny stan Quantum $ \ket{\psi} $ z złożonymi współdziałami $r _j e ^ {i t_j} $ ze stanu podstawy obliczeń $n $-qubit $ \ket{0 \cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="8542b-109">This operation prepares an arbitrary quantum state $\ket{\psi}$ with complex coefficients $r_j e^{i t_j}$ from the $n$-qubit computational basis state $\ket{0 \cdots 0}$.</span></span>
<span data-ttu-id="8542b-110">W szczególności Akcja tej operacji może być symulowana przez transformację jednostkową $U $, która działa w stanie "wszystkie zero" jako</span><span class="sxs-lookup"><span data-stu-id="8542b-110">In particular, the action of this operation can be simulated by the a unitary transformation $U$ which acts on the all-zeros state as</span></span>

<span data-ttu-id="8542b-111">$ $ \begin{align} U\ket {0... 0} & = \ket{\psi} \\ \\ & = \frac{\ sum_ {j = 0} ^ {2 ^ n-1} r_j e ^ {i t_j} \ket{j}} {\sqrt{\ sum_ {j = 0} ^ {2 ^ n-1} | r_j | ^ 2}}.</span><span class="sxs-lookup"><span data-stu-id="8542b-111">$$ \begin{align} U\ket{0...0} & = \ket{\psi} \\\\ & = \frac{ \sum_{j=0}^{2^n-1} r_j e^{i t_j} \ket{j} }{ \sqrt{\sum_{j=0}^{2^n-1} |r_j|^2} }.</span></span>
<span data-ttu-id="8542b-112">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="8542b-112">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="8542b-113">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="8542b-113">Input</span></span>

### <a name="coefficients--complexpolar"></a><span data-ttu-id="8542b-114">współczynniki: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span><span class="sxs-lookup"><span data-stu-id="8542b-114">coefficients : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span></span>

<span data-ttu-id="8542b-115">Tablica do $2 ^ n $ złożone współczynniki reprezentowane przez ich wartości bezwzględne i fazy $ (r_j, t_j) $.</span><span class="sxs-lookup"><span data-stu-id="8542b-115">Array of up to $2^n$ complex coefficients represented by their absolute value and phase $(r_j, t_j)$.</span></span> <span data-ttu-id="8542b-116">Współczynnik $j $ th indeksuje stan liczbowy $ \ket{j} $ zakodowany w formacie little-endian.</span><span class="sxs-lookup"><span data-stu-id="8542b-116">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="8542b-117">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="8542b-117">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="8542b-118">Qubit rejestruje Stany kodowania w formacie little-endian.</span><span class="sxs-lookup"><span data-stu-id="8542b-118">Qubit register encoding number states in little-endian format.</span></span> <span data-ttu-id="8542b-119">Oczekuje się, że zostanie ona zainicjowana w stanie bazowym obliczeniowym $ \ket{0...0} $.</span><span class="sxs-lookup"><span data-stu-id="8542b-119">This is expected to be initialized in the computational basis state $\ket{0...0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8542b-120">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8542b-120">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="8542b-121">Uwagi</span><span class="sxs-lookup"><span data-stu-id="8542b-121">Remarks</span></span>

<span data-ttu-id="8542b-122">Ujemne współczynniki wejścia $r _j < $0 będą traktowane jako wynik dodatni z wartością $ | r_j | $.</span><span class="sxs-lookup"><span data-stu-id="8542b-122">Negative input coefficients $r_j < 0$ will be treated as though positive with value $|r_j|$.</span></span> <span data-ttu-id="8542b-123">`coefficients` zostanie uzupełniona o elementy $ (r_j, t_j) = (0,0, 0,0) $, jeśli określono mniej niż $2 ^ n $.</span><span class="sxs-lookup"><span data-stu-id="8542b-123">`coefficients` will be padded with elements $(r_j, t_j) = (0.0, 0.0)$ if fewer than $2^n$ are specified.</span></span>

## <a name="references"></a><span data-ttu-id="8542b-124">Odwołania</span><span class="sxs-lookup"><span data-stu-id="8542b-124">References</span></span>

- <span data-ttu-id="8542b-125">Synteza obwodów logiki Quantum Vivek V. Shende, Stephen S. Bullock, Igora L. Markov https://arxiv.org/abs/quant-ph/0406176</span><span class="sxs-lookup"><span data-stu-id="8542b-125">Synthesis of Quantum Logic Circuits Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span></span>

## <a name="see-also"></a><span data-ttu-id="8542b-126">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="8542b-126">See Also</span></span>

- [<span data-ttu-id="8542b-127">Microsoft. Quantum. przygotowaniu. ApproximatelyPrepareArbitraryState</span><span class="sxs-lookup"><span data-stu-id="8542b-127">Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryState</span></span>](xref:Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryState)