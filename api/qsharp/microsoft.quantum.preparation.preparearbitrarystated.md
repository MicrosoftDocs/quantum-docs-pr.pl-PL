---
uid: Microsoft.Quantum.Preparation.PrepareArbitraryStateD
title: PrepareArbitraryStateD, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareArbitraryStateD
qsharp.summary: Given a set of coefficients and a little-endian encoded quantum register, prepares an state on that register described by the given coefficients.
ms.openlocfilehash: cca0ea16dca3f3da8ce76a43f1012ffa0e4a72e0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210611"
---
# <a name="preparearbitrarystated-operation"></a><span data-ttu-id="aa451-102">PrepareArbitraryStateD, operacja</span><span class="sxs-lookup"><span data-stu-id="aa451-102">PrepareArbitraryStateD operation</span></span>

<span data-ttu-id="aa451-103">Przestrzeń nazw: [Microsoft. Quantum. przygotowaniu](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="aa451-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="aa451-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="aa451-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="aa451-105">Uwzględniając zestaw współczynników i zakodowany w formacie Quantum rejestr oparty na little-endian, przygotowuje stan tego rejestru opisany przez podane współczynniki.</span><span class="sxs-lookup"><span data-stu-id="aa451-105">Given a set of coefficients and a little-endian encoded quantum register, prepares an state on that register described by the given coefficients.</span></span>

```qsharp
operation PrepareArbitraryStateD (coefficients : Double[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="aa451-106">Opis</span><span class="sxs-lookup"><span data-stu-id="aa451-106">Description</span></span>

<span data-ttu-id="aa451-107">Ta operacja przygotowuje dowolny stan Quantum $ \ket{\psi} $ z złożonymi współdziałami $r _j e ^ {i t_j} $ ze stanu podstawy obliczeń $n $-qubit $ \ket{0 \cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="aa451-107">This operation prepares an arbitrary quantum state $\ket{\psi}$ with complex coefficients $r_j e^{i t_j}$ from the $n$-qubit computational basis state $\ket{0 \cdots 0}$.</span></span>
<span data-ttu-id="aa451-108">W szczególności działanie tej operacji może być symulowane przez transformację jednostkową $U $, które działa na stanie "wszystkie zero" jako</span><span class="sxs-lookup"><span data-stu-id="aa451-108">In particular, the action of this operation can be simulated by the a unitary transformation $U$ that acts on the all-zeros state as</span></span>

<span data-ttu-id="aa451-109">$ $ \begin{align} U\ket {0... 0} & = \ket{\psi} \\ \\ & = \frac{\ sum_ {j = 0} ^ {2 ^ n-1} r_j e ^ {i t_j} \ket{j}} {\sqrt{\ sum_ {j = 0} ^ {2 ^ n-1} | r_j | ^ 2}}.</span><span class="sxs-lookup"><span data-stu-id="aa451-109">$$ \begin{align} U\ket{0...0} & = \ket{\psi} \\\\ & = \frac{ \sum_{j=0}^{2^n-1} r_j e^{i t_j} \ket{j} }{ \sqrt{\sum_{j=0}^{2^n-1} |r_j|^2} }.</span></span>
<span data-ttu-id="aa451-110">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="aa451-110">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="aa451-111">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="aa451-111">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="aa451-112">współczynniki: [Podwójna precyzja](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="aa451-112">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="aa451-113">Tablica z maksymalnie $2 ^ n $ rzeczywistymi współczynnikiem.</span><span class="sxs-lookup"><span data-stu-id="aa451-113">Array of up to $2^n$ real coefficients.</span></span> <span data-ttu-id="aa451-114">Współczynnik $j $ th indeksuje stan liczbowy $ \ket{j} $ zakodowany w formacie little-endian.</span><span class="sxs-lookup"><span data-stu-id="aa451-114">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="aa451-115">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="aa451-115">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="aa451-116">Qubit rejestruje Stany kodowania w formacie little-endian.</span><span class="sxs-lookup"><span data-stu-id="aa451-116">Qubit register encoding number states in little-endian format.</span></span> <span data-ttu-id="aa451-117">Oczekuje się, że zostanie ona zainicjowana w stanie bazowym obliczeniowym $ \ket{0...0} $.</span><span class="sxs-lookup"><span data-stu-id="aa451-117">This is expected to be initialized in the computational basis state $\ket{0...0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="aa451-118">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="aa451-118">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="aa451-119">Uwagi</span><span class="sxs-lookup"><span data-stu-id="aa451-119">Remarks</span></span>

<span data-ttu-id="aa451-120">Ujemne współczynniki wejścia $r _j < $0 będą traktowane jako wynik dodatni z wartością $ | r_j | $.</span><span class="sxs-lookup"><span data-stu-id="aa451-120">Negative input coefficients $r_j < 0$ will be treated as though positive with value $|r_j|$.</span></span> <span data-ttu-id="aa451-121">`coefficients` zostanie uzupełniona o elementy $ (r_j, t_j) = (0,0, 0,0) $, jeśli określono mniej niż $2 ^ n $.</span><span class="sxs-lookup"><span data-stu-id="aa451-121">`coefficients` will be padded with elements $(r_j, t_j) = (0.0, 0.0)$ if fewer than $2^n$ are specified.</span></span>

## <a name="references"></a><span data-ttu-id="aa451-122">Odwołania</span><span class="sxs-lookup"><span data-stu-id="aa451-122">References</span></span>

- <span data-ttu-id="aa451-123">Synteza obwodów logiki Quantum Vivek V. Shende, Stephen S. Bullock, Igora L. Markov https://arxiv.org/abs/quant-ph/0406176</span><span class="sxs-lookup"><span data-stu-id="aa451-123">Synthesis of Quantum Logic Circuits Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span></span>

## <a name="see-also"></a><span data-ttu-id="aa451-124">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="aa451-124">See Also</span></span>

- [<span data-ttu-id="aa451-125">Microsoft. Quantum. przygotowaniu. ApproximatelyPrepareArbitraryState</span><span class="sxs-lookup"><span data-stu-id="aa451-125">Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryState</span></span>](xref:Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryState)