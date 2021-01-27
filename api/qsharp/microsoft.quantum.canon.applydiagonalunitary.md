---
uid: Microsoft.Quantum.Canon.ApplyDiagonalUnitary
title: ApplyDiagonalUnitary, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyDiagonalUnitary
qsharp.summary: Applies an array of complex phases to numeric basis states of a register of qubits.
ms.openlocfilehash: 14ab8d7beddda26594967225934d472d52bac9eb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841885"
---
# <a name="applydiagonalunitary-operation"></a><span data-ttu-id="eca67-102">ApplyDiagonalUnitary, operacja</span><span class="sxs-lookup"><span data-stu-id="eca67-102">ApplyDiagonalUnitary operation</span></span>

<span data-ttu-id="eca67-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="eca67-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="eca67-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="eca67-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="eca67-105">Stosuje tablicę złożonych faz do numerycznych Stanów rejestru qubits.</span><span class="sxs-lookup"><span data-stu-id="eca67-105">Applies an array of complex phases to numeric basis states of a register of qubits.</span></span>

```qsharp
operation ApplyDiagonalUnitary (coefficients : Double[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="eca67-106">Opis</span><span class="sxs-lookup"><span data-stu-id="eca67-106">Description</span></span>

<span data-ttu-id="eca67-107">Ta operacja służy do implementowania ukośnej jednostki, która stosuje złożoną fazę $e ^ {i \ theta_j} $ na $n $-qubit Number State $ \ket{j} $.</span><span class="sxs-lookup"><span data-stu-id="eca67-107">This operation implements a diagonal unitary that applies a complex phase $e^{i \theta_j}$ on the $n$-qubit number state $\ket{j}$.</span></span>
<span data-ttu-id="eca67-108">W szczególności ta operacja może być reprezentowana przez jednostkę</span><span class="sxs-lookup"><span data-stu-id="eca67-108">In particular, this operation can be represented by the unitary</span></span>

<span data-ttu-id="eca67-109">$ $ \begin{align} U = \sum ^ {2 ^ n-1} _ {j = 0} e ^ {i \ theta_j} \ket{j}\bra{j}.</span><span class="sxs-lookup"><span data-stu-id="eca67-109">$$ \begin{align} U = \sum^{2^n-1}_{j=0}e^{i\theta_j}\ket{j}\bra{j}.</span></span>
<span data-ttu-id="eca67-110">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="eca67-110">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="eca67-111">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="eca67-111">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="eca67-112">współczynniki: [Podwójna precyzja](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="eca67-112">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="eca67-113">Tablica do $2 ^ n $ współczynniki $ \ theta_j $.</span><span class="sxs-lookup"><span data-stu-id="eca67-113">Array of up to $2^n$ coefficients $\theta_j$.</span></span> <span data-ttu-id="eca67-114">Współczynnik $j $ th indeksuje stan liczbowy $ \ket{j} $ zakodowany w formacie little-endian.</span><span class="sxs-lookup"><span data-stu-id="eca67-114">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="eca67-115">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="eca67-115">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="eca67-116">$n $-qubit kontroli rejestru, który koduje liczbę Stany $ \ket{j} $ w formacie little-endian.</span><span class="sxs-lookup"><span data-stu-id="eca67-116">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>



## <a name="output--unit"></a><span data-ttu-id="eca67-117">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="eca67-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="eca67-118">Uwagi</span><span class="sxs-lookup"><span data-stu-id="eca67-118">Remarks</span></span>

<span data-ttu-id="eca67-119">`coefficients` zostanie uzupełniona o elementy $ \ theta_j = $0,0, jeśli określono mniej niż $2 ^ n $.</span><span class="sxs-lookup"><span data-stu-id="eca67-119">`coefficients` will be padded with elements $\theta_j = 0.0$ if fewer than $2^n$ are specified.</span></span>

## <a name="references"></a><span data-ttu-id="eca67-120">Odwołania</span><span class="sxs-lookup"><span data-stu-id="eca67-120">References</span></span>

- <span data-ttu-id="eca67-121">Synteza obwodów logiki Quantum Vivek V. Shende, Stephen S. Bullock, Igora L. Markov https://arxiv.org/abs/quant-ph/0406176</span><span class="sxs-lookup"><span data-stu-id="eca67-121">Synthesis of Quantum Logic Circuits Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span></span>

## <a name="see-also"></a><span data-ttu-id="eca67-122">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="eca67-122">See Also</span></span>

- [<span data-ttu-id="eca67-123">Microsoft. Quantum. Canon. ApproximatelyApplyDiagonalUnitary</span><span class="sxs-lookup"><span data-stu-id="eca67-123">Microsoft.Quantum.Canon.ApproximatelyApplyDiagonalUnitary</span></span>](xref:Microsoft.Quantum.Canon.ApproximatelyApplyDiagonalUnitary)