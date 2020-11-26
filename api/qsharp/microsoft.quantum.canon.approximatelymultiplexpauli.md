---
uid: Microsoft.Quantum.Canon.ApproximatelyMultiplexPauli
title: ApproximatelyMultiplexPauli, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApproximatelyMultiplexPauli
qsharp.summary: Applies a Pauli rotation conditioned on an array of qubits, truncating small rotation angles according to a given tolerance.
ms.openlocfilehash: 8024df4608f14408bfcd46139e72454ff44b116f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207755"
---
# <a name="approximatelymultiplexpauli-operation"></a><span data-ttu-id="cb137-102">ApproximatelyMultiplexPauli, operacja</span><span class="sxs-lookup"><span data-stu-id="cb137-102">ApproximatelyMultiplexPauli operation</span></span>

<span data-ttu-id="cb137-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="cb137-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="cb137-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cb137-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="cb137-105">Stosuje obrót Pauli na podstawie tablicy qubits, obcinanie małych kątów obrotu zgodnie z podaną tolerancją.</span><span class="sxs-lookup"><span data-stu-id="cb137-105">Applies a Pauli rotation conditioned on an array of qubits, truncating small rotation angles according to a given tolerance.</span></span>

```qsharp
operation ApproximatelyMultiplexPauli (tolerance : Double, coefficients : Double[], pauli : Pauli, control : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="cb137-106">Opis</span><span class="sxs-lookup"><span data-stu-id="cb137-106">Description</span></span>

<span data-ttu-id="cb137-107">W ten sposób stosowana jest przemnożona sterowana operacja jednostkowa, która dokonuje rotacji przez kąt $ \ theta_j $ o pojedynczej qubit $P operator Pauli $, gdy jest on kontrolowany przez $n $-qubit Number $ \ket{j} $.</span><span class="sxs-lookup"><span data-stu-id="cb137-107">This applies a multiply controlled unitary operation that performs rotations by angle $\theta_j$ about single-qubit Pauli operator $P$ when controlled by the $n$-qubit number state $\ket{j}$.</span></span>
<span data-ttu-id="cb137-108">W szczególności Akcja tej operacji jest reprezentowana przez jednostkę</span><span class="sxs-lookup"><span data-stu-id="cb137-108">In particular, the action of this operation is represented by the unitary</span></span>

<span data-ttu-id="cb137-109">$ $ \begin{align} U = \sum ^ {2 ^ n-1} _ {j = 0} \ket{j}\bra{j} \otimes e ^ {i P \ theta_j}.</span><span class="sxs-lookup"><span data-stu-id="cb137-109">$$ \begin{align} U = \sum^{2^n - 1}_{j=0} \ket{j}\bra{j} \otimes e^{i P \theta_j}.</span></span>
<span data-ttu-id="cb137-110">\end{align}</span><span class="sxs-lookup"><span data-stu-id="cb137-110">\end{align}</span></span>

##

## <a name="input"></a><span data-ttu-id="cb137-111">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="cb137-111">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="cb137-112">Tolerancja: [Podwójna precyzja](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="cb137-112">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="cb137-113">Tolerancja poniżej, które małe współczynniki są obcinane.</span><span class="sxs-lookup"><span data-stu-id="cb137-113">A tolerance below which small coefficients are truncated.</span></span>


### <a name="coefficients--double"></a><span data-ttu-id="cb137-114">współczynniki: [Podwójna precyzja](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="cb137-114">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="cb137-115">Tablica do $2 ^ n $ współczynniki $ \ theta_j $.</span><span class="sxs-lookup"><span data-stu-id="cb137-115">Array of up to $2^n$ coefficients $\theta_j$.</span></span> <span data-ttu-id="cb137-116">Współczynnik $j $ th indeksuje stan liczbowy $ \ket{j} $ zakodowany w formacie little-endian.</span><span class="sxs-lookup"><span data-stu-id="cb137-116">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="pauli--pauli"></a><span data-ttu-id="cb137-117">Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="cb137-117">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="cb137-118">Operator Pauli $P $, który określa oś obrotu.</span><span class="sxs-lookup"><span data-stu-id="cb137-118">Pauli operator $P$ that determines axis of rotation.</span></span>


### <a name="control--littleendian"></a><span data-ttu-id="cb137-119">Kontrolka: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="cb137-119">control : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="cb137-120">$n $-qubit kontroli rejestru, który koduje liczbę Stany $ \ket{j} $ w formacie little-endian.</span><span class="sxs-lookup"><span data-stu-id="cb137-120">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="cb137-121">obiekt docelowy: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="cb137-121">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="cb137-122">Pojedynczy rejestr qubit, który jest obrócony $e ^ {i P \ theta_j} $.</span><span class="sxs-lookup"><span data-stu-id="cb137-122">Single qubit register that is rotated by $e^{i P \theta_j}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="cb137-123">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cb137-123">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="cb137-124">Uwagi</span><span class="sxs-lookup"><span data-stu-id="cb137-124">Remarks</span></span>

<span data-ttu-id="cb137-125">`coefficients` zostanie uzupełniona o elementy $ \ theta_j = $0,0, jeśli określono mniej niż $2 ^ n $.</span><span class="sxs-lookup"><span data-stu-id="cb137-125">`coefficients` will be padded with elements $\theta_j = 0.0$ if fewer than $2^n$ are specified.</span></span>

## <a name="see-also"></a><span data-ttu-id="cb137-126">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="cb137-126">See Also</span></span>

- [<span data-ttu-id="cb137-127">Microsoft. Quantum. Canon. MultiplexPauli</span><span class="sxs-lookup"><span data-stu-id="cb137-127">Microsoft.Quantum.Canon.MultiplexPauli</span></span>](xref:Microsoft.Quantum.Canon.MultiplexPauli)