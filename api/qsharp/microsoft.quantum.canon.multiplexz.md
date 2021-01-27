---
uid: Microsoft.Quantum.Canon.MultiplexZ
title: MultiplexZ, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexZ
qsharp.summary: Applies a Pauli Z rotation conditioned on an array of qubits.
ms.openlocfilehash: dccfe86104263e23794bce33279e8748f11f5a54
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852423"
---
# <a name="multiplexz-operation"></a><span data-ttu-id="78732-102">MultiplexZ, operacja</span><span class="sxs-lookup"><span data-stu-id="78732-102">MultiplexZ operation</span></span>

<span data-ttu-id="78732-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="78732-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="78732-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="78732-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="78732-105">Stosuje obrót Pauli Z na tablicy qubits.</span><span class="sxs-lookup"><span data-stu-id="78732-105">Applies a Pauli Z rotation conditioned on an array of qubits.</span></span>

```qsharp
operation MultiplexZ (coefficients : Double[], control : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="78732-106">Opis</span><span class="sxs-lookup"><span data-stu-id="78732-106">Description</span></span>

<span data-ttu-id="78732-107">W ten sposób stosowana jest przemnożona sterowana operacja jednostkowa, która dokonuje rotacji przez kąt $ \ theta_j $ o pojedynczej Pauli operator $Z $, gdy jest on kontrolowany przez $n $-qubit Number $ \ket{j} $.</span><span class="sxs-lookup"><span data-stu-id="78732-107">This applies the multiply controlled unitary operation that performs rotations by angle $\theta_j$ about single-qubit Pauli operator $Z$ when controlled by the $n$-qubit number state $\ket{j}$.</span></span>
<span data-ttu-id="78732-108">W szczególności ta operacja może być reprezentowana przez jednostkę</span><span class="sxs-lookup"><span data-stu-id="78732-108">In particular, this operation can be represented by the unitary</span></span>

<span data-ttu-id="78732-109">$ $ \begin{align} U = \sum ^ {2 ^ n-1} _ {j = 0} \ket{j}\bra{j} \otimes e ^ {i Z \ theta_j}.</span><span class="sxs-lookup"><span data-stu-id="78732-109">$$ \begin{align} U = \sum^{2^n-1}_{j=0} \ket{j}\bra{j} \otimes e^{i Z \theta_j}.</span></span>
<span data-ttu-id="78732-110">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="78732-110">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="78732-111">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="78732-111">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="78732-112">współczynniki: [Podwójna precyzja](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="78732-112">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="78732-113">Tablica do $2 ^ n $ współczynniki $ \ theta_j $.</span><span class="sxs-lookup"><span data-stu-id="78732-113">Array of up to $2^n$ coefficients $\theta_j$.</span></span> <span data-ttu-id="78732-114">Współczynnik $j $ th indeksuje stan liczbowy $ \ket{j} $ zakodowany w formacie little-endian.</span><span class="sxs-lookup"><span data-stu-id="78732-114">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="control--littleendian"></a><span data-ttu-id="78732-115">Kontrolka: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="78732-115">control : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="78732-116">$n $-qubit kontroli rejestru, który koduje liczbę Stany $ \ket{j} $ w formacie little-endian.</span><span class="sxs-lookup"><span data-stu-id="78732-116">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="78732-117">obiekt docelowy: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="78732-117">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="78732-118">Pojedynczy rejestr qubit, który jest obrócony $e ^ {i P \ theta_j} $.</span><span class="sxs-lookup"><span data-stu-id="78732-118">Single qubit register that is rotated by $e^{i P \theta_j}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="78732-119">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="78732-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="78732-120">Uwagi</span><span class="sxs-lookup"><span data-stu-id="78732-120">Remarks</span></span>

<span data-ttu-id="78732-121">`coefficients` zostanie uzupełniona o elementy $ \ theta_j = $0,0, jeśli określono mniej niż $2 ^ n $.</span><span class="sxs-lookup"><span data-stu-id="78732-121">`coefficients` will be padded with elements $\theta_j = 0.0$ if fewer than $2^n$ are specified.</span></span>

## <a name="references"></a><span data-ttu-id="78732-122">Odwołania</span><span class="sxs-lookup"><span data-stu-id="78732-122">References</span></span>

- <span data-ttu-id="78732-123">Synteza obwodów logiki Quantum Vivek V. Shende, Stephen S. Bullock, Igora L. Markov https://arxiv.org/abs/quant-ph/0406176</span><span class="sxs-lookup"><span data-stu-id="78732-123">Synthesis of Quantum Logic Circuits Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span></span>

## <a name="see-also"></a><span data-ttu-id="78732-124">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="78732-124">See Also</span></span>

- [<span data-ttu-id="78732-125">Microsoft. Quantum. Canon. ApproximatelyMultiplexZ</span><span class="sxs-lookup"><span data-stu-id="78732-125">Microsoft.Quantum.Canon.ApproximatelyMultiplexZ</span></span>](xref:Microsoft.Quantum.Canon.ApproximatelyMultiplexZ)