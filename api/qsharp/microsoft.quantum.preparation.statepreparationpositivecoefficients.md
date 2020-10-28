---
uid: Microsoft.Quantum.Preparation.StatePreparationPositiveCoefficients
title: StatePreparationPositiveCoefficients, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: StatePreparationPositiveCoefficients
qsharp.summary: >-
  Returns an operation that prepares the given quantum state.

  The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with positive coefficients $\alpha_j\ge 0$ from the $n$-qubit computational basis state $\ket{0...0}$.

  The action of U on a newly-allocated register is given by $$ \begin{align} U \ket{0\cdots 0} = \ket{\psi} = \frac{\sum_{j=0}^{2^n-1}\alpha_j \ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|\alpha_j|^2}}. \end{align} $$
ms.openlocfilehash: 39d961c71d231e7b51290f81c20c8c6b48c7e0b1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722894"
---
# <a name="statepreparationpositivecoefficients-function"></a><span data-ttu-id="c3bcd-102">StatePreparationPositiveCoefficients, funkcja</span><span class="sxs-lookup"><span data-stu-id="c3bcd-102">StatePreparationPositiveCoefficients function</span></span>

<span data-ttu-id="c3bcd-103">Przestrzeń nazw: [Microsoft. Quantum. przygotowaniu](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="c3bcd-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="c3bcd-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c3bcd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c3bcd-105">Zwraca operację, która przygotowuje dany stan Quantum.</span><span class="sxs-lookup"><span data-stu-id="c3bcd-105">Returns an operation that prepares the given quantum state.</span></span>

<span data-ttu-id="c3bcd-106">Zwrócona operacja $U $ przygotowuje dowolny stan Quantum $ \ket{\psi} $ z pozytywnymi współczynnikimi $ \ alpha_j \ge $0 ze stanu podstawy obliczeń $n $-qubit $ \ket{0...0} $.</span><span class="sxs-lookup"><span data-stu-id="c3bcd-106">The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with positive coefficients $\alpha_j\ge 0$ from the $n$-qubit computational basis state $\ket{0...0}$.</span></span>

<span data-ttu-id="c3bcd-107">Akcja U w nowo przydzielonym rejestrze jest określona przez $ $ \begin{align} U \ket{0\cdots 0} = \ket{\psi} = \frac{\ sum_ {j = 0} ^ {2 ^ n-1} \ alpha_j \ket{j}}{\sqrt{\ sum_ {j = 0} ^ {2 ^ n-1} | \ alpha_j | ^ 2}}.</span><span class="sxs-lookup"><span data-stu-id="c3bcd-107">The action of U on a newly-allocated register is given by $$ \begin{align} U \ket{0\cdots 0} = \ket{\psi} = \frac{\sum_{j=0}^{2^n-1}\alpha_j \ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|\alpha_j|^2}}.</span></span>
<span data-ttu-id="c3bcd-108">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="c3bcd-108">\end{align} $$</span></span>

```qsharp
function StatePreparationPositiveCoefficients (coefficients : Double[]) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="c3bcd-109">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="c3bcd-109">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="c3bcd-110">współczynniki: [Podwójna precyzja](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="c3bcd-110">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="c3bcd-111">Tablica do $2 ^ n $ współczynniki $ \ alpha_j $.</span><span class="sxs-lookup"><span data-stu-id="c3bcd-111">Array of up to $2^n$ coefficients $\alpha_j$.</span></span> <span data-ttu-id="c3bcd-112">Współczynnik $j $ th indeksuje stan liczbowy $ \ket{j} $ zakodowany w formacie little-endian.</span><span class="sxs-lookup"><span data-stu-id="c3bcd-112">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>



## <a name="output--littleendian--unit-adj--ctl"></a><span data-ttu-id="c3bcd-113">Dane wyjściowe: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) korekta + CTL</span><span class="sxs-lookup"><span data-stu-id="c3bcd-113">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="c3bcd-114">Operacja jednostki przygotowania stanu $U $.</span><span class="sxs-lookup"><span data-stu-id="c3bcd-114">A state-preparation unitary operation $U$.</span></span>

## <a name="remarks"></a><span data-ttu-id="c3bcd-115">Uwagi</span><span class="sxs-lookup"><span data-stu-id="c3bcd-115">Remarks</span></span>

<span data-ttu-id="c3bcd-116">Ujemne współczynniki danych wejściowych $ \ alpha_j < $0 będą traktowane jako wynik dodatni z wartością $ | \ alpha_j | $.</span><span class="sxs-lookup"><span data-stu-id="c3bcd-116">Negative input coefficients $\alpha_j < 0$ will be treated as though positive with value $|\alpha_j|$.</span></span> <span data-ttu-id="c3bcd-117">`coefficients` zostanie uzupełniona o elementy $ \ alpha_j = $0,0, jeśli określono mniej niż $2 ^ n $.</span><span class="sxs-lookup"><span data-stu-id="c3bcd-117">`coefficients` will be padded with elements $\alpha_j = 0.0$ if fewer than $2^n$ are specified.</span></span>