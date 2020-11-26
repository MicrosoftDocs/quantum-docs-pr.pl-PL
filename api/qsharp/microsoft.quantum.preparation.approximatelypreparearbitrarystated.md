---
uid: Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryStateD
title: ApproximatelyPrepareArbitraryStateD, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: ApproximatelyPrepareArbitraryStateD
qsharp.summary: Given a set of coefficients and a little-endian encoded quantum register, prepares an state on that register described by the given coefficients, up to a given approximation tolerance.
ms.openlocfilehash: 822efe08e66c43b7a3128d100e3e58a8c2ce3c2e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193594"
---
# <a name="approximatelypreparearbitrarystated-operation"></a><span data-ttu-id="9dcfc-102">ApproximatelyPrepareArbitraryStateD, operacja</span><span class="sxs-lookup"><span data-stu-id="9dcfc-102">ApproximatelyPrepareArbitraryStateD operation</span></span>

<span data-ttu-id="9dcfc-103">Przestrzeń nazw: [Microsoft. Quantum. przygotowaniu](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="9dcfc-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="9dcfc-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9dcfc-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9dcfc-105">Uwzględniając zestaw współczynników i zakodowany w formacie Quantum rejestr oparty na little-endian, przygotowuje stan tego rejestru opisany przez podane współczynniki, aż do danej przepuszczalnej tolerancji.</span><span class="sxs-lookup"><span data-stu-id="9dcfc-105">Given a set of coefficients and a little-endian encoded quantum register, prepares an state on that register described by the given coefficients, up to a given approximation tolerance.</span></span>

```qsharp
operation ApproximatelyPrepareArbitraryStateD (tolerance : Double, coefficients : Double[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="9dcfc-106">Opis</span><span class="sxs-lookup"><span data-stu-id="9dcfc-106">Description</span></span>

<span data-ttu-id="9dcfc-107">Ta operacja przygotowuje dowolny stan Quantum $ \ket{\psi} $ z złożonymi współdziałami $r _j e ^ {i t_j} $ ze stanu podstawy obliczeń $n $-qubit $ \ket{0 \cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="9dcfc-107">This operation prepares an arbitrary quantum state $\ket{\psi}$ with complex coefficients $r_j e^{i t_j}$ from the $n$-qubit computational basis state $\ket{0 \cdots 0}$.</span></span>
<span data-ttu-id="9dcfc-108">W szczególności Akcja tej operacji może być symulowana przez transformację jednostkową $U $, która działa w stanie "wszystkie zero" jako</span><span class="sxs-lookup"><span data-stu-id="9dcfc-108">In particular, the action of this operation can be simulated by the a unitary transformation $U$ which acts on the all-zeros state as</span></span>

<span data-ttu-id="9dcfc-109">$ $ \begin{align} U\ket {0... 0} & = \ket{\psi} \\ \\ & = \frac{\ sum_ {j = 0} ^ {2 ^ n-1} r_j e ^ {i t_j} \ket{j}} {\sqrt{\ sum_ {j = 0} ^ {2 ^ n-1} | r_j | ^ 2}}.</span><span class="sxs-lookup"><span data-stu-id="9dcfc-109">$$ \begin{align} U\ket{0...0} & = \ket{\psi} \\\\ & = \frac{ \sum_{j=0}^{2^n-1} r_j e^{i t_j} \ket{j} }{ \sqrt{\sum_{j=0}^{2^n-1} |r_j|^2} }.</span></span>
<span data-ttu-id="9dcfc-110">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="9dcfc-110">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="9dcfc-111">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="9dcfc-111">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="9dcfc-112">Tolerancja: [Podwójna precyzja](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="9dcfc-112">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="9dcfc-113">Tolerancja przybliżona, która ma być używana podczas przygotowywania danego stanu.</span><span class="sxs-lookup"><span data-stu-id="9dcfc-113">The approximation tolerance to be used when preparing the given state.</span></span>


### <a name="coefficients--double"></a><span data-ttu-id="9dcfc-114">współczynniki: [Podwójna precyzja](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="9dcfc-114">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="9dcfc-115">Tablica z maksymalnie $2 ^ n $ rzeczywistymi współczynnikiem.</span><span class="sxs-lookup"><span data-stu-id="9dcfc-115">Array of up to $2^n$ real coefficients.</span></span> <span data-ttu-id="9dcfc-116">Współczynnik $j $ th indeksuje stan liczbowy $ \ket{j} $ zakodowany w formacie little-endian.</span><span class="sxs-lookup"><span data-stu-id="9dcfc-116">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="9dcfc-117">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="9dcfc-117">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="9dcfc-118">Qubit rejestruje Stany kodowania w formacie little-endian.</span><span class="sxs-lookup"><span data-stu-id="9dcfc-118">Qubit register encoding number states in little-endian format.</span></span> <span data-ttu-id="9dcfc-119">Oczekuje się, że zostanie ona zainicjowana w stanie bazowym obliczeniowym $ \ket{0...0} $.</span><span class="sxs-lookup"><span data-stu-id="9dcfc-119">This is expected to be initialized in the computational basis state $\ket{0...0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9dcfc-120">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9dcfc-120">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="9dcfc-121">Uwagi</span><span class="sxs-lookup"><span data-stu-id="9dcfc-121">Remarks</span></span>

<span data-ttu-id="9dcfc-122">Ujemne współczynniki wejścia $r _j < $0 będą traktowane jako wynik dodatni z wartością $ | r_j | $.</span><span class="sxs-lookup"><span data-stu-id="9dcfc-122">Negative input coefficients $r_j < 0$ will be treated as though positive with value $|r_j|$.</span></span> <span data-ttu-id="9dcfc-123">`coefficients` zostanie uzupełniona o elementy $ (r_j, t_j) = (0,0, 0,0) $, jeśli określono mniej niż $2 ^ n $.</span><span class="sxs-lookup"><span data-stu-id="9dcfc-123">`coefficients` will be padded with elements $(r_j, t_j) = (0.0, 0.0)$ if fewer than $2^n$ are specified.</span></span>

## <a name="references"></a><span data-ttu-id="9dcfc-124">Odwołania</span><span class="sxs-lookup"><span data-stu-id="9dcfc-124">References</span></span>

- <span data-ttu-id="9dcfc-125">Synteza obwodów logiki Quantum Vivek V. Shende, Stephen S. Bullock, Igora L. Markov https://arxiv.org/abs/quant-ph/0406176</span><span class="sxs-lookup"><span data-stu-id="9dcfc-125">Synthesis of Quantum Logic Circuits Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span></span>