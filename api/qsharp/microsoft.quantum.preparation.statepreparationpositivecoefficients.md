---
uid: Microsoft.Quantum.Preparation.StatePreparationPositiveCoefficients
title: StatePreparationPositiveCoefficients, funkcja
ms.date: 11/25/2020 12:00:00 AM
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
ms.openlocfilehash: 8f1fd7d77531996faf566adb78f452929d6cbd50
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193254"
---
# <a name="statepreparationpositivecoefficients-function"></a><span data-ttu-id="8afca-102">StatePreparationPositiveCoefficients, funkcja</span><span class="sxs-lookup"><span data-stu-id="8afca-102">StatePreparationPositiveCoefficients function</span></span>

<span data-ttu-id="8afca-103">Przestrzeń nazw: [Microsoft. Quantum. przygotowaniu](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="8afca-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="8afca-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8afca-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="8afca-105">StatePreparationPositiveCoefficients jest przestarzała.</span><span class="sxs-lookup"><span data-stu-id="8afca-105">StatePreparationPositiveCoefficients has been deprecated.</span></span> <span data-ttu-id="8afca-106">Użyj <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateD> zamiast tego.</span><span class="sxs-lookup"><span data-stu-id="8afca-106">Please use <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateD> instead.</span></span>

<span data-ttu-id="8afca-107">Zwraca operację, która przygotowuje dany stan Quantum.</span><span class="sxs-lookup"><span data-stu-id="8afca-107">Returns an operation that prepares the given quantum state.</span></span>

<span data-ttu-id="8afca-108">Zwrócona operacja $U $ przygotowuje dowolny stan Quantum $ \ket{\psi} $ z pozytywnymi współczynnikimi $ \ alpha_j \ge $0 ze stanu podstawy obliczeń $n $-qubit $ \ket{0...0} $.</span><span class="sxs-lookup"><span data-stu-id="8afca-108">The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with positive coefficients $\alpha_j\ge 0$ from the $n$-qubit computational basis state $\ket{0...0}$.</span></span>

<span data-ttu-id="8afca-109">Akcja U w nowo przydzielonym rejestrze jest określona przez $ $ \begin{align} U \ket{0\cdots 0} = \ket{\psi} = \frac{\ sum_ {j = 0} ^ {2 ^ n-1} \ alpha_j \ket{j}}{\sqrt{\ sum_ {j = 0} ^ {2 ^ n-1} | \ alpha_j | ^ 2}}.</span><span class="sxs-lookup"><span data-stu-id="8afca-109">The action of U on a newly-allocated register is given by $$ \begin{align} U \ket{0\cdots 0} = \ket{\psi} = \frac{\sum_{j=0}^{2^n-1}\alpha_j \ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|\alpha_j|^2}}.</span></span>
<span data-ttu-id="8afca-110">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="8afca-110">\end{align} $$</span></span>

```qsharp
function StatePreparationPositiveCoefficients (coefficients : Double[]) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="8afca-111">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="8afca-111">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="8afca-112">współczynniki: [Podwójna precyzja](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="8afca-112">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="8afca-113">Tablica do $2 ^ n $ współczynniki $ \ alpha_j $.</span><span class="sxs-lookup"><span data-stu-id="8afca-113">Array of up to $2^n$ coefficients $\alpha_j$.</span></span> <span data-ttu-id="8afca-114">Współczynnik $j $ th indeksuje stan liczbowy $ \ket{j} $ zakodowany w formacie little-endian.</span><span class="sxs-lookup"><span data-stu-id="8afca-114">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>



## <a name="output--littleendian--unit--is-adj--ctl"></a><span data-ttu-id="8afca-115">Output: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  to przymiotnik + CTL</span><span class="sxs-lookup"><span data-stu-id="8afca-115">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="8afca-116">Operacja jednostki przygotowania stanu $U $.</span><span class="sxs-lookup"><span data-stu-id="8afca-116">A state-preparation unitary operation $U$.</span></span>

## <a name="remarks"></a><span data-ttu-id="8afca-117">Uwagi</span><span class="sxs-lookup"><span data-stu-id="8afca-117">Remarks</span></span>

<span data-ttu-id="8afca-118">Ujemne współczynniki danych wejściowych $ \ alpha_j < $0 będą traktowane jako wynik dodatni z wartością $ | \ alpha_j | $.</span><span class="sxs-lookup"><span data-stu-id="8afca-118">Negative input coefficients $\alpha_j < 0$ will be treated as though positive with value $|\alpha_j|$.</span></span> <span data-ttu-id="8afca-119">`coefficients` zostanie uzupełniona o elementy $ \ alpha_j = $0,0, jeśli określono mniej niż $2 ^ n $.</span><span class="sxs-lookup"><span data-stu-id="8afca-119">`coefficients` will be padded with elements $\alpha_j = 0.0$ if fewer than $2^n$ are specified.</span></span>