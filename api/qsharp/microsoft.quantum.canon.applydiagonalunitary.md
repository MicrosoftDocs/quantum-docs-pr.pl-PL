---
uid: Microsoft.Quantum.Canon.ApplyDiagonalUnitary
title: ApplyDiagonalUnitary, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyDiagonalUnitary
qsharp.summary: Applies an array of complex phases to numeric basis states of a register of qubits.
ms.openlocfilehash: 6ecacf6e4fe2c505036de208c8aeb5350e479e3c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718284"
---
# <a name="applydiagonalunitary-operation"></a><span data-ttu-id="d321e-102">ApplyDiagonalUnitary, operacja</span><span class="sxs-lookup"><span data-stu-id="d321e-102">ApplyDiagonalUnitary operation</span></span>

<span data-ttu-id="d321e-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d321e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d321e-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d321e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d321e-105">Stosuje tablicę złożonych faz do numerycznych Stanów rejestru qubits.</span><span class="sxs-lookup"><span data-stu-id="d321e-105">Applies an array of complex phases to numeric basis states of a register of qubits.</span></span>

```qsharp
operation ApplyDiagonalUnitary (coefficients : Double[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="d321e-106">Opis</span><span class="sxs-lookup"><span data-stu-id="d321e-106">Description</span></span>

<span data-ttu-id="d321e-107">Ta operacja służy do implementowania ukośnej jednostki, która stosuje złożoną fazę $e ^ {i \ theta_j} $ na $n $-qubit Number State $ \ket{j} $.</span><span class="sxs-lookup"><span data-stu-id="d321e-107">This operation implements a diagonal unitary that applies a complex phase $e^{i \theta_j}$ on the $n$-qubit number state $\ket{j}$.</span></span>
<span data-ttu-id="d321e-108">W szczególności ta operacja może być reprezentowana przez jednostkę</span><span class="sxs-lookup"><span data-stu-id="d321e-108">In particular, this operation can be represented by the unitary</span></span>

<span data-ttu-id="d321e-109">$ $ \begin{align} U = \sum ^ {2 ^ n-1} _ {j = 0} e ^ {i \ theta_j} \ket{j}\bra{j}.</span><span class="sxs-lookup"><span data-stu-id="d321e-109">$$ \begin{align} U = \sum^{2^n-1}_{j=0}e^{i\theta_j}\ket{j}\bra{j}.</span></span>
<span data-ttu-id="d321e-110">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="d321e-110">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="d321e-111">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="d321e-111">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="d321e-112">współczynniki: [Podwójna precyzja](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="d321e-112">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="d321e-113">Tablica do $2 ^ n $ współczynniki $ \ theta_j $.</span><span class="sxs-lookup"><span data-stu-id="d321e-113">Array of up to $2^n$ coefficients $\theta_j$.</span></span> <span data-ttu-id="d321e-114">Współczynnik $j $ th indeksuje stan liczbowy $ \ket{j} $ zakodowany w formacie little-endian.</span><span class="sxs-lookup"><span data-stu-id="d321e-114">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="d321e-115">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="d321e-115">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="d321e-116">$n $-qubit kontroli rejestru, który koduje liczbę Stany $ \ket{j} $ w formacie little-endian.</span><span class="sxs-lookup"><span data-stu-id="d321e-116">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d321e-117">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d321e-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="d321e-118">Uwagi</span><span class="sxs-lookup"><span data-stu-id="d321e-118">Remarks</span></span>

<span data-ttu-id="d321e-119">`coefficients` zostanie uzupełniona o elementy $ \ theta_j = $0,0, jeśli określono mniej niż $2 ^ n $.</span><span class="sxs-lookup"><span data-stu-id="d321e-119">`coefficients` will be padded with elements $\theta_j = 0.0$ if fewer than $2^n$ are specified.</span></span>

## <a name="references"></a><span data-ttu-id="d321e-120">Dokumentacja</span><span class="sxs-lookup"><span data-stu-id="d321e-120">References</span></span>

- <span data-ttu-id="d321e-121">Synteza obwodów logiki Quantum Vivek V. Shende, Stephen S. Bullock, Igora L. Markov https://arxiv.org/abs/quant-ph/0406176</span><span class="sxs-lookup"><span data-stu-id="d321e-121">Synthesis of Quantum Logic Circuits Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span></span>

## <a name="see-also"></a><span data-ttu-id="d321e-122">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="d321e-122">See Also</span></span>

- [<span data-ttu-id="d321e-123">Microsoft. Quantum. Canon. ApproximatelyApplyDiagonalUnitary</span><span class="sxs-lookup"><span data-stu-id="d321e-123">Microsoft.Quantum.Canon.ApproximatelyApplyDiagonalUnitary</span></span>](xref:Microsoft.Quantum.Canon.ApproximatelyApplyDiagonalUnitary)