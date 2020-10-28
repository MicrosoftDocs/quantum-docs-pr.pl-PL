---
uid: Microsoft.Quantum.Canon.ApproximatelyMultiplexZ
title: ApproximatelyMultiplexZ, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApproximatelyMultiplexZ
qsharp.summary: Applies a Pauli Z rotation conditioned on an array of qubits, truncating small rotation angles according to a given tolerance.
ms.openlocfilehash: ac5195b8b3afaad4d41fe50d45652644e2397e1b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716795"
---
# <a name="approximatelymultiplexz-operation"></a><span data-ttu-id="036c3-102">ApproximatelyMultiplexZ, operacja</span><span class="sxs-lookup"><span data-stu-id="036c3-102">ApproximatelyMultiplexZ operation</span></span>

<span data-ttu-id="036c3-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="036c3-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="036c3-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="036c3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="036c3-105">Stosuje obrót Pauli Z na tablicy qubits, obcinanie małych kątów obrotu zgodnie z podaną tolerancją.</span><span class="sxs-lookup"><span data-stu-id="036c3-105">Applies a Pauli Z rotation conditioned on an array of qubits, truncating small rotation angles according to a given tolerance.</span></span>

```qsharp
operation ApproximatelyMultiplexZ (tolerance : Double, coefficients : Double[], control : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="036c3-106">Opis</span><span class="sxs-lookup"><span data-stu-id="036c3-106">Description</span></span>

<span data-ttu-id="036c3-107">W ten sposób stosowana jest przemnożona sterowana operacja jednostkowa, która dokonuje rotacji przez kąt $ \ theta_j $ o pojedynczej Pauli operator $Z $, gdy jest on kontrolowany przez $n $-qubit Number $ \ket{j} $.</span><span class="sxs-lookup"><span data-stu-id="036c3-107">This applies the multiply controlled unitary operation that performs rotations by angle $\theta_j$ about single-qubit Pauli operator $Z$ when controlled by the $n$-qubit number state $\ket{j}$.</span></span>
<span data-ttu-id="036c3-108">W szczególności ta operacja może być reprezentowana przez jednostkę</span><span class="sxs-lookup"><span data-stu-id="036c3-108">In particular, this operation can be represented by the unitary</span></span>

<span data-ttu-id="036c3-109">$ $ \begin{align} U = \sum ^ {2 ^ n-1} _ {j = 0} \ket{j}\bra{j} \otimes e ^ {i Z \ theta_j}.</span><span class="sxs-lookup"><span data-stu-id="036c3-109">$$ \begin{align} U = \sum^{2^n-1}_{j=0} \ket{j}\bra{j} \otimes e^{i Z \theta_j}.</span></span>
<span data-ttu-id="036c3-110">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="036c3-110">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="036c3-111">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="036c3-111">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="036c3-112">Tolerancja: [Podwójna precyzja](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="036c3-112">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="036c3-113">Tolerancja poniżej, które małe współczynniki są obcinane.</span><span class="sxs-lookup"><span data-stu-id="036c3-113">A tolerance below which small coefficients are truncated.</span></span>


### <a name="coefficients--double"></a><span data-ttu-id="036c3-114">współczynniki: [Podwójna precyzja](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="036c3-114">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="036c3-115">Tablica do $2 ^ n $ współczynniki $ \ theta_j $.</span><span class="sxs-lookup"><span data-stu-id="036c3-115">Array of up to $2^n$ coefficients $\theta_j$.</span></span> <span data-ttu-id="036c3-116">Współczynnik $j $ th indeksuje stan liczbowy $ \ket{j} $ zakodowany w formacie little-endian.</span><span class="sxs-lookup"><span data-stu-id="036c3-116">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="control--littleendian"></a><span data-ttu-id="036c3-117">Kontrolka: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="036c3-117">control : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="036c3-118">$n $-qubit kontroli rejestru, który koduje liczbę Stany $ \ket{j} $ w formacie little-endian.</span><span class="sxs-lookup"><span data-stu-id="036c3-118">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="036c3-119">obiekt docelowy: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="036c3-119">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="036c3-120">Pojedynczy rejestr qubit, który jest obrócony $e ^ {i P \ theta_j} $.</span><span class="sxs-lookup"><span data-stu-id="036c3-120">Single qubit register that is rotated by $e^{i P \theta_j}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="036c3-121">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="036c3-121">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="036c3-122">Uwagi</span><span class="sxs-lookup"><span data-stu-id="036c3-122">Remarks</span></span>

<span data-ttu-id="036c3-123">`coefficients` zostanie uzupełniona o elementy $ \ theta_j = $0,0, jeśli określono mniej niż $2 ^ n $.</span><span class="sxs-lookup"><span data-stu-id="036c3-123">`coefficients` will be padded with elements $\theta_j = 0.0$ if fewer than $2^n$ are specified.</span></span>

## <a name="references"></a><span data-ttu-id="036c3-124">Dokumentacja</span><span class="sxs-lookup"><span data-stu-id="036c3-124">References</span></span>

- <span data-ttu-id="036c3-125">Synteza obwodów logiki Quantum Vivek V. Shende, Stephen S. Bullock, Igora L. Markov https://arxiv.org/abs/quant-ph/0406176</span><span class="sxs-lookup"><span data-stu-id="036c3-125">Synthesis of Quantum Logic Circuits Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span></span>

## <a name="see-also"></a><span data-ttu-id="036c3-126">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="036c3-126">See Also</span></span>

- [<span data-ttu-id="036c3-127">Microsoft. Quantum. Canon. MultiplexZ</span><span class="sxs-lookup"><span data-stu-id="036c3-127">Microsoft.Quantum.Canon.MultiplexZ</span></span>](xref:Microsoft.Quantum.Canon.MultiplexZ)