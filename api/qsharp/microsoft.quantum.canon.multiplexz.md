---
uid: Microsoft.Quantum.Canon.MultiplexZ
title: MultiplexZ, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexZ
qsharp.summary: Applies a Pauli Z rotation conditioned on an array of qubits.
ms.openlocfilehash: f7b1973e18ad396ebe892ad63ae47374a7cafbd5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715778"
---
# <a name="multiplexz-operation"></a><span data-ttu-id="7464d-102">MultiplexZ, operacja</span><span class="sxs-lookup"><span data-stu-id="7464d-102">MultiplexZ operation</span></span>

<span data-ttu-id="7464d-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="7464d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="7464d-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7464d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7464d-105">Stosuje obrót Pauli Z na tablicy qubits.</span><span class="sxs-lookup"><span data-stu-id="7464d-105">Applies a Pauli Z rotation conditioned on an array of qubits.</span></span>

```qsharp
operation MultiplexZ (coefficients : Double[], control : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="7464d-106">Opis</span><span class="sxs-lookup"><span data-stu-id="7464d-106">Description</span></span>

<span data-ttu-id="7464d-107">W ten sposób stosowana jest przemnożona sterowana operacja jednostkowa, która dokonuje rotacji przez kąt $ \ theta_j $ o pojedynczej Pauli operator $Z $, gdy jest on kontrolowany przez $n $-qubit Number $ \ket{j} $.</span><span class="sxs-lookup"><span data-stu-id="7464d-107">This applies the multiply controlled unitary operation that performs rotations by angle $\theta_j$ about single-qubit Pauli operator $Z$ when controlled by the $n$-qubit number state $\ket{j}$.</span></span>
<span data-ttu-id="7464d-108">W szczególności ta operacja może być reprezentowana przez jednostkę</span><span class="sxs-lookup"><span data-stu-id="7464d-108">In particular, this operation can be represented by the unitary</span></span>

<span data-ttu-id="7464d-109">$ $ \begin{align} U = \sum ^ {2 ^ n-1} _ {j = 0} \ket{j}\bra{j} \otimes e ^ {i Z \ theta_j}.</span><span class="sxs-lookup"><span data-stu-id="7464d-109">$$ \begin{align} U = \sum^{2^n-1}_{j=0} \ket{j}\bra{j} \otimes e^{i Z \theta_j}.</span></span>
<span data-ttu-id="7464d-110">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="7464d-110">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="7464d-111">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="7464d-111">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="7464d-112">współczynniki: [Podwójna precyzja](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="7464d-112">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="7464d-113">Tablica do $2 ^ n $ współczynniki $ \ theta_j $.</span><span class="sxs-lookup"><span data-stu-id="7464d-113">Array of up to $2^n$ coefficients $\theta_j$.</span></span> <span data-ttu-id="7464d-114">Współczynnik $j $ th indeksuje stan liczbowy $ \ket{j} $ zakodowany w formacie little-endian.</span><span class="sxs-lookup"><span data-stu-id="7464d-114">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="control--littleendian"></a><span data-ttu-id="7464d-115">Kontrolka: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="7464d-115">control : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="7464d-116">$n $-qubit kontroli rejestru, który koduje liczbę Stany $ \ket{j} $ w formacie little-endian.</span><span class="sxs-lookup"><span data-stu-id="7464d-116">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="7464d-117">obiekt docelowy: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="7464d-117">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="7464d-118">Pojedynczy rejestr qubit, który jest obrócony $e ^ {i P \ theta_j} $.</span><span class="sxs-lookup"><span data-stu-id="7464d-118">Single qubit register that is rotated by $e^{i P \theta_j}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7464d-119">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7464d-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="7464d-120">Uwagi</span><span class="sxs-lookup"><span data-stu-id="7464d-120">Remarks</span></span>

<span data-ttu-id="7464d-121">`coefficients` zostanie uzupełniona o elementy $ \ theta_j = $0,0, jeśli określono mniej niż $2 ^ n $.</span><span class="sxs-lookup"><span data-stu-id="7464d-121">`coefficients` will be padded with elements $\theta_j = 0.0$ if fewer than $2^n$ are specified.</span></span>

## <a name="references"></a><span data-ttu-id="7464d-122">Dokumentacja</span><span class="sxs-lookup"><span data-stu-id="7464d-122">References</span></span>

- <span data-ttu-id="7464d-123">Synteza obwodów logiki Quantum Vivek V. Shende, Stephen S. Bullock, Igora L. Markov https://arxiv.org/abs/quant-ph/0406176</span><span class="sxs-lookup"><span data-stu-id="7464d-123">Synthesis of Quantum Logic Circuits Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span></span>

## <a name="see-also"></a><span data-ttu-id="7464d-124">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="7464d-124">See Also</span></span>

- [<span data-ttu-id="7464d-125">Microsoft. Quantum. Canon. ApproximatelyMultiplexZ</span><span class="sxs-lookup"><span data-stu-id="7464d-125">Microsoft.Quantum.Canon.ApproximatelyMultiplexZ</span></span>](xref:Microsoft.Quantum.Canon.ApproximatelyMultiplexZ)