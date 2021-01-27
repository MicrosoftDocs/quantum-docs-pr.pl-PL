---
uid: Microsoft.Quantum.Preparation.StatePreparationPositiveCoefficients
title: StatePreparationPositiveCoefficients, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: StatePreparationPositiveCoefficients
qsharp.summary: >-
  > [!WARNING]

  > StatePreparationPositiveCoefficients has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateD> instead.


  Returns an operation that prepares the given quantum state.

  The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with positive coefficients $\alpha_j\ge 0$ from the $n$-qubit computational basis state $\ket{0...0}$.

  The action of U on a newly-allocated register is given by $$ \begin{align} U \ket{0\cdots 0} = \ket{\psi} = \frac{\sum_{j=0}^{2^n-1}\alpha_j \ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|\alpha_j|^2}}. \end{align} $$
ms.openlocfilehash: 081541d93bf853fa0de1573038dc00c296432281
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855840"
---
# <a name="statepreparationpositivecoefficients-function"></a><span data-ttu-id="84673-102">StatePreparationPositiveCoefficients, funkcja</span><span class="sxs-lookup"><span data-stu-id="84673-102">StatePreparationPositiveCoefficients function</span></span>

<span data-ttu-id="84673-103">Przestrzeń nazw: [Microsoft. Quantum. przygotowaniu](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="84673-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="84673-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="84673-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="84673-105">StatePreparationPositiveCoefficients jest przestarzała.</span><span class="sxs-lookup"><span data-stu-id="84673-105">StatePreparationPositiveCoefficients has been deprecated.</span></span> <span data-ttu-id="84673-106">Użyj <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateD> zamiast tego.</span><span class="sxs-lookup"><span data-stu-id="84673-106">Please use <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateD> instead.</span></span>

<span data-ttu-id="84673-107">Zwraca operację, która przygotowuje dany stan Quantum.</span><span class="sxs-lookup"><span data-stu-id="84673-107">Returns an operation that prepares the given quantum state.</span></span>

<span data-ttu-id="84673-108">Zwrócona operacja $U $ przygotowuje dowolny stan Quantum $ \ket{\psi} $ z pozytywnymi współczynnikimi $ \ alpha_j \ge $0 ze stanu podstawy obliczeń $n $-qubit $ \ket{0...0} $.</span><span class="sxs-lookup"><span data-stu-id="84673-108">The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with positive coefficients $\alpha_j\ge 0$ from the $n$-qubit computational basis state $\ket{0...0}$.</span></span>

<span data-ttu-id="84673-109">Akcja U w nowo przydzielonym rejestrze jest określona przez $ $ \begin{align} U \ket{0\cdots 0} = \ket{\psi} = \frac{\ sum_ {j = 0} ^ {2 ^ n-1} \ alpha_j \ket{j}}{\sqrt{\ sum_ {j = 0} ^ {2 ^ n-1} | \ alpha_j | ^ 2}}.</span><span class="sxs-lookup"><span data-stu-id="84673-109">The action of U on a newly-allocated register is given by $$ \begin{align} U \ket{0\cdots 0} = \ket{\psi} = \frac{\sum_{j=0}^{2^n-1}\alpha_j \ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|\alpha_j|^2}}.</span></span>
<span data-ttu-id="84673-110">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="84673-110">\end{align} $$</span></span>

```qsharp
function StatePreparationPositiveCoefficients (coefficients : Double[]) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="84673-111">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="84673-111">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="84673-112">współczynniki: [Podwójna precyzja](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="84673-112">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="84673-113">Tablica do $2 ^ n $ współczynniki $ \ alpha_j $.</span><span class="sxs-lookup"><span data-stu-id="84673-113">Array of up to $2^n$ coefficients $\alpha_j$.</span></span> <span data-ttu-id="84673-114">Współczynnik $j $ th indeksuje stan liczbowy $ \ket{j} $ zakodowany w formacie little-endian.</span><span class="sxs-lookup"><span data-stu-id="84673-114">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>



## <a name="output--littleendian--unit--is-adj--ctl"></a><span data-ttu-id="84673-115">Output: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  to przymiotnik + CTL</span><span class="sxs-lookup"><span data-stu-id="84673-115">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="84673-116">Operacja jednostki przygotowania stanu $U $.</span><span class="sxs-lookup"><span data-stu-id="84673-116">A state-preparation unitary operation $U$.</span></span>

## <a name="example"></a><span data-ttu-id="84673-117">Przykład</span><span class="sxs-lookup"><span data-stu-id="84673-117">Example</span></span>

<span data-ttu-id="84673-118">Poniższy fragment kodu przygotowuje stan Quantum $ \ket{\psi} = \ sqrt {1/8} \ KET {0} + \ sqrt {7/8} \ KET {2} $ w rejestrze qubit `qubitsLE` .</span><span class="sxs-lookup"><span data-stu-id="84673-118">The following snippet prepares the quantum state $\ket{\psi}=\sqrt{1/8}\ket{0}+\sqrt{7/8}\ket{2}$ in the qubit register `qubitsLE`.</span></span>

```qsharp
let amplitudes = [Sqrt(0.125), 0.0, Sqrt(0.875), 0.0];
let op = StatePreparationPositiveCoefficients(amplitudes);
using (qubits = Qubit[2]) {
    let qubitsLE = LittleEndian(qubits);
    op(qubitsLE);
}
```

## <a name="remarks"></a><span data-ttu-id="84673-119">Uwagi</span><span class="sxs-lookup"><span data-stu-id="84673-119">Remarks</span></span>

<span data-ttu-id="84673-120">Ujemne współczynniki danych wejściowych $ \ alpha_j < $0 będą traktowane jako wynik dodatni z wartością $ | \ alpha_j | $.</span><span class="sxs-lookup"><span data-stu-id="84673-120">Negative input coefficients $\alpha_j < 0$ will be treated as though positive with value $|\alpha_j|$.</span></span> <span data-ttu-id="84673-121">`coefficients` zostanie uzupełniona o elementy $ \ alpha_j = $0,0, jeśli określono mniej niż $2 ^ n $.</span><span class="sxs-lookup"><span data-stu-id="84673-121">`coefficients` will be padded with elements $\alpha_j = 0.0$ if fewer than $2^n$ are specified.</span></span>