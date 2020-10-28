---
uid: Microsoft.Quantum.Canon.ApproximatelyApplyDiagonalUnitary
title: ApproximatelyApplyDiagonalUnitary, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApproximatelyApplyDiagonalUnitary
qsharp.summary: Applies an array of complex phases to numeric basis states of a register of qubits, truncating small rotation angles according to a given tolerance.
ms.openlocfilehash: 9d9b1ced320b142aef2a2cd8f3335f855d37048f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716823"
---
# <a name="approximatelyapplydiagonalunitary-operation"></a><span data-ttu-id="242ee-102">ApproximatelyApplyDiagonalUnitary, operacja</span><span class="sxs-lookup"><span data-stu-id="242ee-102">ApproximatelyApplyDiagonalUnitary operation</span></span>

<span data-ttu-id="242ee-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="242ee-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="242ee-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="242ee-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="242ee-105">Stosuje tablicę złożonych faz do numerycznych Stanów rejestru qubits, obcinanie małych kątów obrotu zgodnie z podaną tolerancją.</span><span class="sxs-lookup"><span data-stu-id="242ee-105">Applies an array of complex phases to numeric basis states of a register of qubits, truncating small rotation angles according to a given tolerance.</span></span>

```qsharp
operation ApproximatelyApplyDiagonalUnitary (tolerance : Double, coefficients : Double[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="242ee-106">Opis</span><span class="sxs-lookup"><span data-stu-id="242ee-106">Description</span></span>

<span data-ttu-id="242ee-107">Ta operacja służy do implementowania ukośnej jednostki, która stosuje złożoną fazę $e ^ {i \ theta_j} $ na $n $-qubit Number State $ \ket{j} $.</span><span class="sxs-lookup"><span data-stu-id="242ee-107">This operation implements a diagonal unitary that applies a complex phase $e^{i \theta_j}$ on the $n$-qubit number state $\ket{j}$.</span></span>
<span data-ttu-id="242ee-108">W szczególności ta operacja może być reprezentowana przez jednostkę</span><span class="sxs-lookup"><span data-stu-id="242ee-108">In particular, this operation can be represented by the unitary</span></span>

<span data-ttu-id="242ee-109">$ $ \begin{align} U = \sum ^ {2 ^ n-1} _ {j = 0} e ^ {i \ theta_j} \ket{j}\bra{j}.</span><span class="sxs-lookup"><span data-stu-id="242ee-109">$$ \begin{align} U = \sum^{2^n-1}_{j=0}e^{i\theta_j}\ket{j}\bra{j}.</span></span>
<span data-ttu-id="242ee-110">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="242ee-110">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="242ee-111">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="242ee-111">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="242ee-112">Tolerancja: [Podwójna precyzja](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="242ee-112">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="242ee-113">Tolerancja poniżej, które małe współczynniki są obcinane.</span><span class="sxs-lookup"><span data-stu-id="242ee-113">A tolerance below which small coefficients are truncated.</span></span>


### <a name="coefficients--double"></a><span data-ttu-id="242ee-114">współczynniki: [Podwójna precyzja](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="242ee-114">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="242ee-115">Tablica do $2 ^ n $ współczynniki $ \ theta_j $.</span><span class="sxs-lookup"><span data-stu-id="242ee-115">Array of up to $2^n$ coefficients $\theta_j$.</span></span> <span data-ttu-id="242ee-116">Współczynnik $j $ th indeksuje stan liczbowy $ \ket{j} $ zakodowany w formacie little-endian.</span><span class="sxs-lookup"><span data-stu-id="242ee-116">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="242ee-117">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="242ee-117">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="242ee-118">$n $-qubit kontroli rejestru, który koduje liczbę Stany $ \ket{j} $ w formacie little-endian.</span><span class="sxs-lookup"><span data-stu-id="242ee-118">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>



## <a name="output--unit"></a><span data-ttu-id="242ee-119">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="242ee-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="242ee-120">Uwagi</span><span class="sxs-lookup"><span data-stu-id="242ee-120">Remarks</span></span>

<span data-ttu-id="242ee-121">`coefficients` zostanie uzupełniona o elementy $ \ theta_j = $0,0, jeśli określono mniej niż $2 ^ n $.</span><span class="sxs-lookup"><span data-stu-id="242ee-121">`coefficients` will be padded with elements $\theta_j = 0.0$ if fewer than $2^n$ are specified.</span></span>

## <a name="references"></a><span data-ttu-id="242ee-122">Dokumentacja</span><span class="sxs-lookup"><span data-stu-id="242ee-122">References</span></span>

- <span data-ttu-id="242ee-123">Synteza obwodów logiki Quantum Vivek V. Shende, Stephen S. Bullock, Igora L. Markov https://arxiv.org/abs/quant-ph/0406176</span><span class="sxs-lookup"><span data-stu-id="242ee-123">Synthesis of Quantum Logic Circuits Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span></span>

## <a name="see-also"></a><span data-ttu-id="242ee-124">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="242ee-124">See Also</span></span>

- [<span data-ttu-id="242ee-125">Microsoft. Quantum. Canon. ApplyDiagonalUnitary</span><span class="sxs-lookup"><span data-stu-id="242ee-125">Microsoft.Quantum.Canon.ApplyDiagonalUnitary</span></span>](xref:Microsoft.Quantum.Canon.ApplyDiagonalUnitary)