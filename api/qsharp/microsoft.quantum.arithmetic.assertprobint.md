---
uid: Microsoft.Quantum.Arithmetic.AssertProbInt
title: AssertProbInt, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertProbInt
qsharp.summary: Asserts that the probability of a specific state of a quantum register has the expected value.
ms.openlocfilehash: a8e4217e18528adc0aa9923f1c0dcfb59e1d2488
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721365"
---
# <a name="assertprobint-operation"></a><span data-ttu-id="cc1cc-102">AssertProbInt, operacja</span><span class="sxs-lookup"><span data-stu-id="cc1cc-102">AssertProbInt operation</span></span>

<span data-ttu-id="cc1cc-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="cc1cc-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="cc1cc-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="cc1cc-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="cc1cc-105">Potwierdza, że prawdopodobieństwo określonego stanu rejestru Quantum ma oczekiwaną wartość.</span><span class="sxs-lookup"><span data-stu-id="cc1cc-105">Asserts that the probability of a specific state of a quantum register has the expected value.</span></span>

```qsharp
operation AssertProbInt (stateIndex : Int, expected : Double, qubits : Microsoft.Quantum.Arithmetic.LittleEndian, tolerance : Double) : Unit
```


## <a name="description"></a><span data-ttu-id="cc1cc-106">Opis</span><span class="sxs-lookup"><span data-stu-id="cc1cc-106">Description</span></span>

<span data-ttu-id="cc1cc-107">Mając $n $-qubit Quantum State $ \ket{\psi} = \sum ^ {2 ^ n-1} _ {j = 0} \ alpha_j \ket{j} $, potwierdza, że prawdopodobieństwo $ | \ alpha_j | ^ 2 $ stanu $ \ket{j} $ indeksowane przez $j $ ma oczekiwaną wartość.</span><span class="sxs-lookup"><span data-stu-id="cc1cc-107">Given an $n$-qubit quantum state $\ket{\psi}=\sum^{2^n-1}_{j=0}\alpha_j \ket{j}$, asserts that the probability $|\alpha_j|^2$ of the state $\ket{j}$ indexed by $j$ has the expected value.</span></span>

## <a name="input"></a><span data-ttu-id="cc1cc-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="cc1cc-108">Input</span></span>

### <a name="stateindex--int"></a><span data-ttu-id="cc1cc-109">stateIndex: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="cc1cc-109">stateIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="cc1cc-110">Indeks $j $ stanu $ \ket{j} $ reprezentowanego przez `LittleEndian` rejestr.</span><span class="sxs-lookup"><span data-stu-id="cc1cc-110">The index $j$ of the state $\ket{j}$ represented by a `LittleEndian` register.</span></span>


### <a name="expected--double"></a><span data-ttu-id="cc1cc-111">Oczekiwano: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="cc1cc-111">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="cc1cc-112">Oczekiwana wartość $ | \ alpha_j | ^ 2 $.</span><span class="sxs-lookup"><span data-stu-id="cc1cc-112">The expected value of $|\alpha_j|^2$.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="cc1cc-113">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="cc1cc-113">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="cc1cc-114">Rejestr qubit, który przechowuje $ \ket{\psi} $ w formacie little-endian.</span><span class="sxs-lookup"><span data-stu-id="cc1cc-114">The qubit register that stores $\ket{\psi}$ in little-endian format.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="cc1cc-115">Tolerancja: [Podwójna precyzja](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="cc1cc-115">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="cc1cc-116">Absolutna tolerancja różnicy między wartością rzeczywistą i oczekiwaną.</span><span class="sxs-lookup"><span data-stu-id="cc1cc-116">Absolute tolerance on the difference between actual and expected.</span></span>



## <a name="output--unit"></a><span data-ttu-id="cc1cc-117">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cc1cc-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

