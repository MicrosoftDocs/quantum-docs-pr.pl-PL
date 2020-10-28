---
uid: Microsoft.Quantum.Canon.MultiplexPauli
title: MultiplexPauli, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexPauli
qsharp.summary: Applies a Pauli rotation conditioned on an array of qubits.
ms.openlocfilehash: 0714e796c1e5ad097814bcf507f49f59a844e9ff
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715787"
---
# <a name="multiplexpauli-operation"></a><span data-ttu-id="c116d-102">MultiplexPauli, operacja</span><span class="sxs-lookup"><span data-stu-id="c116d-102">MultiplexPauli operation</span></span>

<span data-ttu-id="c116d-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c116d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c116d-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c116d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c116d-105">Stosuje obrót Pauli na tablicy qubits.</span><span class="sxs-lookup"><span data-stu-id="c116d-105">Applies a Pauli rotation conditioned on an array of qubits.</span></span>

```qsharp
operation MultiplexPauli (coefficients : Double[], pauli : Pauli, control : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="c116d-106">Opis</span><span class="sxs-lookup"><span data-stu-id="c116d-106">Description</span></span>

<span data-ttu-id="c116d-107">W ten sposób stosowana jest przemnożona sterowana operacja jednostkowa, która dokonuje rotacji przez kąt $ \ theta_j $ o pojedynczej qubit $P operator Pauli $, gdy jest on kontrolowany przez $n $-qubit Number $ \ket{j} $.</span><span class="sxs-lookup"><span data-stu-id="c116d-107">This applies a multiply controlled unitary operation that performs rotations by angle $\theta_j$ about single-qubit Pauli operator $P$ when controlled by the $n$-qubit number state $\ket{j}$.</span></span>
<span data-ttu-id="c116d-108">W szczególności Akcja tej operacji jest reprezentowana przez jednostkę</span><span class="sxs-lookup"><span data-stu-id="c116d-108">In particular, the action of this operation is represented by the unitary</span></span>

<span data-ttu-id="c116d-109">$ $ \begin{align} U = \sum ^ {2 ^ n-1} _ {j = 0} \ket{j}\bra{j} \otimes e ^ {i P \ theta_j}.</span><span class="sxs-lookup"><span data-stu-id="c116d-109">$$ \begin{align} U = \sum^{2^n - 1}_{j=0} \ket{j}\bra{j} \otimes e^{i P \theta_j}.</span></span>
<span data-ttu-id="c116d-110">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="c116d-110">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="c116d-111">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="c116d-111">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="c116d-112">współczynniki: [Podwójna precyzja](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="c116d-112">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="c116d-113">Tablica do $2 ^ n $ współczynniki $ \ theta_j $.</span><span class="sxs-lookup"><span data-stu-id="c116d-113">Array of up to $2^n$ coefficients $\theta_j$.</span></span> <span data-ttu-id="c116d-114">Współczynnik $j $ th indeksuje stan liczbowy $ \ket{j} $ zakodowany w formacie little-endian.</span><span class="sxs-lookup"><span data-stu-id="c116d-114">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="pauli--pauli"></a><span data-ttu-id="c116d-115">Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="c116d-115">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="c116d-116">Operator Pauli $P $, który określa oś obrotu.</span><span class="sxs-lookup"><span data-stu-id="c116d-116">Pauli operator $P$ that determines axis of rotation.</span></span>


### <a name="control--littleendian"></a><span data-ttu-id="c116d-117">Kontrolka: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="c116d-117">control : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="c116d-118">$n $-qubit kontroli rejestru, który koduje liczbę Stany $ \ket{j} $ w formacie little-endian.</span><span class="sxs-lookup"><span data-stu-id="c116d-118">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="c116d-119">obiekt docelowy: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="c116d-119">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="c116d-120">Pojedynczy rejestr qubit, który jest obrócony $e ^ {i P \ theta_j} $.</span><span class="sxs-lookup"><span data-stu-id="c116d-120">Single qubit register that is rotated by $e^{i P \theta_j}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c116d-121">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c116d-121">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="c116d-122">Uwagi</span><span class="sxs-lookup"><span data-stu-id="c116d-122">Remarks</span></span>

<span data-ttu-id="c116d-123">`coefficients` zostanie uzupełniona o elementy $ \ theta_j = $0,0, jeśli określono mniej niż $2 ^ n $.</span><span class="sxs-lookup"><span data-stu-id="c116d-123">`coefficients` will be padded with elements $\theta_j = 0.0$ if fewer than $2^n$ are specified.</span></span>

## <a name="see-also"></a><span data-ttu-id="c116d-124">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="c116d-124">See Also</span></span>

- [<span data-ttu-id="c116d-125">Microsoft. Quantum. Canon. ApproximatelyMultiplexPauli</span><span class="sxs-lookup"><span data-stu-id="c116d-125">Microsoft.Quantum.Canon.ApproximatelyMultiplexPauli</span></span>](xref:Microsoft.Quantum.Canon.ApproximatelyMultiplexPauli)