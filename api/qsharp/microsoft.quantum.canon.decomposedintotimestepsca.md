---
uid: Microsoft.Quantum.Canon.DecomposedIntoTimeStepsCA
title: DecomposedIntoTimeStepsCA, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DecomposedIntoTimeStepsCA
qsharp.summary: Returns an operation implementing the Trotter–Suzuki integrator for a given operation.
ms.openlocfilehash: cfd563c1c6350255364de1e227442624acc98c22
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716338"
---
# <a name="decomposedintotimestepsca-function"></a><span data-ttu-id="7a7c7-102">DecomposedIntoTimeStepsCA, funkcja</span><span class="sxs-lookup"><span data-stu-id="7a7c7-102">DecomposedIntoTimeStepsCA function</span></span>

<span data-ttu-id="7a7c7-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="7a7c7-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="7a7c7-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7a7c7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7a7c7-105">Zwraca operację implementującą Integrator Trotter – Suzuki dla danej operacji.</span><span class="sxs-lookup"><span data-stu-id="7a7c7-105">Returns an operation implementing the Trotter–Suzuki integrator for a given operation.</span></span>

```qsharp
function DecomposedIntoTimeStepsCA<'T> ((nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), trotterOrder : Int) : ((Double, 'T) => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="7a7c7-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="7a7c7-106">Input</span></span>

### <a name="nsteps--int"></a><span data-ttu-id="7a7c7-107">nSteps: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7a7c7-107">nSteps : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7a7c7-108">Liczba operacji do rozdzielenia na etapy czasu.</span><span class="sxs-lookup"><span data-stu-id="7a7c7-108">The number of operations to be decomposed into time steps.</span></span>


### <a name="op--intdoublet--unit-adj--ctl"></a><span data-ttu-id="7a7c7-109">op: ([int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double), t) => skorygowanie [jednostki](xref:microsoft.quantum.lang-ref.unit) + CTL</span><span class="sxs-lookup"><span data-stu-id="7a7c7-109">op : ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="7a7c7-110">Operacja akceptująca dane wejściowe indeksu (typ `Int` ) i czas wejścia (typ `Double` ) dla dekompozycji.</span><span class="sxs-lookup"><span data-stu-id="7a7c7-110">An operation which accepts an index input (type `Int`) and a time input (type `Double`) for decomposition.</span></span>


### <a name="trotterorder--int"></a><span data-ttu-id="7a7c7-111">trotterOrder: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7a7c7-111">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7a7c7-112">Wybiera kolejność użycia integratora Trotter – Suzuki.</span><span class="sxs-lookup"><span data-stu-id="7a7c7-112">Selects the order of the Trotter–Suzuki integrator to be used.</span></span>
<span data-ttu-id="7a7c7-113">Kolejność 1, a nawet Orders 2, 4, 6,... są obecnie obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="7a7c7-113">Order 1 and even orders 2, 4, 6,... are currently supported.</span></span>



## <a name="output--doublet--unit-adj--ctl"></a><span data-ttu-id="7a7c7-114">Output: ([Double](xref:microsoft.quantum.lang-ref.double), t) => skorygowanie [jednostki](xref:microsoft.quantum.lang-ref.unit) + CTL</span><span class="sxs-lookup"><span data-stu-id="7a7c7-114">Output : ([Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="7a7c7-115">Zwraca jednostkę implementującą Integrator Trotter – Suzuki, gdzie pierwszy parametr `Double` jest rozmiarem kroku integracji, a drugi parametr jest celem działania.</span><span class="sxs-lookup"><span data-stu-id="7a7c7-115">Returns a unitary implementing the Trotter–Suzuki integrator, where the first parameter `Double` is the integration step size, and the second parameter is the target acted upon.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="7a7c7-116">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="7a7c7-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7a7c7-117">'C</span><span class="sxs-lookup"><span data-stu-id="7a7c7-117">'T</span></span>

<span data-ttu-id="7a7c7-118">Typ, na którym należy wykonać każdy krok czasu. zwykle `Qubit[]` lub `Qubit` .</span><span class="sxs-lookup"><span data-stu-id="7a7c7-118">The type which each time step should act upon; typically, either `Qubit[]` or `Qubit`.</span></span>

## <a name="remarks"></a><span data-ttu-id="7a7c7-119">Uwagi</span><span class="sxs-lookup"><span data-stu-id="7a7c7-119">Remarks</span></span>

<span data-ttu-id="7a7c7-120">Gdy jest wywoływana z `order` równa `1` , ta funkcja zwraca operację, która może być symulowana przez Trottere — Integrator Suzuki $ $ \begin{align} S_1 (\lambda) = \ prod_ {j = 1} ^ {m} e ^ {H_j \lambda}, \end{align} $ $, w którym zastosowano notację [Quant-pH/0508139](https://arxiv.org/abs/quant-ph/0508139) i niech $ \lambda $ to czas ewolucji (reprezentowany przez pierwsze wejście operacji zwróconej), i mieć \{ wartość $ H_j \} _ {j = 1} ^ {m} $ to zestaw (skośny hermitian), które są zintegrowane, które `op(j, lambda, _)` są symulowane przez operatora jednostki $e ^ {H_j \lambda} $.</span><span class="sxs-lookup"><span data-stu-id="7a7c7-120">When called with `order` equal to `1`, this function returns an operation that can be simulated by the lowest-order Trotter–Suzuki integrator $$ \begin{align} S_1(\lambda) = \prod_{j = 1}^{m} e^{H_j \lambda}, \end{align} $$ where we have followed the notation of [quant-ph/0508139](https://arxiv.org/abs/quant-ph/0508139) and let $\lambda$ be the evolution time (represented by the first input of the returned operation), and have let $\{H_j\}_{j = 1}^{m}$ be the set of (skew-Hermitian) dynamical generators being integrated such that `op(j, lambda, _)` is simulated by the unitary operator $e^{H_j \lambda}$.</span></span>

<span data-ttu-id="7a7c7-121">Analogicznie, `order` element `2` zwraca w drugim porządku symetryczne Trotter — Suzuki Integrator $ $ \begin{align} S_2 (\lambda) = \ prod_ {j = 1} ^ {m} e ^ {H_k \lambda/2} \ prod_ {j ' = m} ^ {1} e ^ {H_ {j '} \lambda/2}.</span><span class="sxs-lookup"><span data-stu-id="7a7c7-121">Similarly, an `order` of `2` returns the second-order symmetric Trotter–Suzuki integrator $$ \begin{align} S_2(\lambda) = \prod_{j = 1}^{m} e^{H_k \lambda / 2} \prod_{j' = m}^{1} e^{H_{j'} \lambda / 2}.</span></span>
<span data-ttu-id="7a7c7-122">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="7a7c7-122">\end{align} $$</span></span>

<span data-ttu-id="7a7c7-123">Wyższe wartości równe `order` są implementowane przy użyciu cyklicznej konstrukcji [Quant-pH/0508139](https://arxiv.org/abs/quant-ph/0508139).</span><span class="sxs-lookup"><span data-stu-id="7a7c7-123">Higher even values of `order` are implemented using the recursive construction of [quant-ph/0508139](https://arxiv.org/abs/quant-ph/0508139).</span></span>

## <a name="references"></a><span data-ttu-id="7a7c7-124">Dokumentacja</span><span class="sxs-lookup"><span data-stu-id="7a7c7-124">References</span></span>

- [<span data-ttu-id="7a7c7-125">*D. W. owoce jagodowe, G. Ahokas, R. Cleve, B. C. Sanders*</span><span class="sxs-lookup"><span data-stu-id="7a7c7-125"> *D. W. Berry, G. Ahokas, R. Cleve, B. C. Sanders* </span></span>](https://arxiv.org/abs/quant-ph/0508139)