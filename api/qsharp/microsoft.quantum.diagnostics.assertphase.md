---
uid: Microsoft.Quantum.Diagnostics.AssertPhase
title: AssertPhase, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertPhase
qsharp.summary: Asserts that the phase of an equal superposition state has the expected value.
ms.openlocfilehash: 9130d6c735d90abbc51989ef4a68a8eff8b41371
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202264"
---
# <a name="assertphase-operation"></a><span data-ttu-id="e6097-102">AssertPhase, operacja</span><span class="sxs-lookup"><span data-stu-id="e6097-102">AssertPhase operation</span></span>

<span data-ttu-id="e6097-103">Przestrzeń nazw: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="e6097-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="e6097-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e6097-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e6097-105">Potwierdza, że faza równego stanu nadpozycji ma oczekiwaną wartość.</span><span class="sxs-lookup"><span data-stu-id="e6097-105">Asserts that the phase of an equal superposition state has the expected value.</span></span>

```qsharp
operation AssertPhase (expected : Double, qubit : Qubit, tolerance : Double) : Unit
```


## <a name="description"></a><span data-ttu-id="e6097-106">Opis</span><span class="sxs-lookup"><span data-stu-id="e6097-106">Description</span></span>

<span data-ttu-id="e6097-107">Ta operacja potwierdza, że faza $ \phi $ stanu Quantum, która może być wyrażona jako $ \frac{e ^ {i t}} {\sqrt {2} } (e ^ {i\phi} \ KET {0} + e ^ {-i\phi} \ KET {1} ) $ dla niektórych dowolnych rzeczywistych $t $ ma oczekiwaną wartość.</span><span class="sxs-lookup"><span data-stu-id="e6097-107">This operation asserts that the phase $\phi$ of a quantum state that may be expressed as $\frac{e^{i t}}{\sqrt{2}}(e^{i\phi}\ket{0} + e^{-i\phi}\ket{1})$ for some arbitrary real $t$ has the expected value.</span></span>

## <a name="input"></a><span data-ttu-id="e6097-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="e6097-108">Input</span></span>

### <a name="expected--double"></a><span data-ttu-id="e6097-109">Oczekiwano: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e6097-109">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e6097-110">Oczekiwana wartość $ \phi \In (-\pi, \pi] $.</span><span class="sxs-lookup"><span data-stu-id="e6097-110">The expected value of $\phi \in (-\pi,\pi]$.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="e6097-111">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="e6097-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="e6097-112">Qubit przechowujący oczekiwany stan.</span><span class="sxs-lookup"><span data-stu-id="e6097-112">The qubit that stores the expected state.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="e6097-113">Tolerancja: [Podwójna precyzja](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e6097-113">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e6097-114">Absolutna tolerancja różnicy między wartością rzeczywistą i oczekiwaną.</span><span class="sxs-lookup"><span data-stu-id="e6097-114">Absolute tolerance on the difference between actual and expected.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e6097-115">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e6097-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

