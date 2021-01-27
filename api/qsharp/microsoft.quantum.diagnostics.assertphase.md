---
uid: Microsoft.Quantum.Diagnostics.AssertPhase
title: AssertPhase, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertPhase
qsharp.summary: Asserts that the phase of an equal superposition state has the expected value.
ms.openlocfilehash: 59fa0f2f68b4de271b972aef776ee5097fd5c201
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98830077"
---
# <a name="assertphase-operation"></a><span data-ttu-id="ad234-102">AssertPhase, operacja</span><span class="sxs-lookup"><span data-stu-id="ad234-102">AssertPhase operation</span></span>

<span data-ttu-id="ad234-103">Przestrzeń nazw: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="ad234-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="ad234-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ad234-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ad234-105">Potwierdza, że faza równego stanu nadpozycji ma oczekiwaną wartość.</span><span class="sxs-lookup"><span data-stu-id="ad234-105">Asserts that the phase of an equal superposition state has the expected value.</span></span>

```qsharp
operation AssertPhase (expected : Double, qubit : Qubit, tolerance : Double) : Unit
```


## <a name="description"></a><span data-ttu-id="ad234-106">Opis</span><span class="sxs-lookup"><span data-stu-id="ad234-106">Description</span></span>

<span data-ttu-id="ad234-107">Ta operacja potwierdza, że faza $ \phi $ stanu Quantum, która może być wyrażona jako $ \frac{e ^ {i t}} {\sqrt {2} } (e ^ {i\phi} \ KET {0} + e ^ {-i\phi} \ KET {1} ) $ dla niektórych dowolnych rzeczywistych $t $ ma oczekiwaną wartość.</span><span class="sxs-lookup"><span data-stu-id="ad234-107">This operation asserts that the phase $\phi$ of a quantum state that may be expressed as $\frac{e^{i t}}{\sqrt{2}}(e^{i\phi}\ket{0} + e^{-i\phi}\ket{1})$ for some arbitrary real $t$ has the expected value.</span></span>

## <a name="input"></a><span data-ttu-id="ad234-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="ad234-108">Input</span></span>

### <a name="expected--double"></a><span data-ttu-id="ad234-109">Oczekiwano: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ad234-109">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ad234-110">Oczekiwana wartość $ \phi \In (-\pi, \pi] $.</span><span class="sxs-lookup"><span data-stu-id="ad234-110">The expected value of $\phi \in (-\pi,\pi]$.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="ad234-111">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="ad234-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="ad234-112">Qubit przechowujący oczekiwany stan.</span><span class="sxs-lookup"><span data-stu-id="ad234-112">The qubit that stores the expected state.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="ad234-113">Tolerancja: [Podwójna precyzja](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ad234-113">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ad234-114">Absolutna tolerancja różnicy między wartością rzeczywistą i oczekiwaną.</span><span class="sxs-lookup"><span data-stu-id="ad234-114">Absolute tolerance on the difference between actual and expected.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ad234-115">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ad234-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="ad234-116">Przykład</span><span class="sxs-lookup"><span data-stu-id="ad234-116">Example</span></span>

<span data-ttu-id="ad234-117">Następujące potwierdzenie powiodło się: `qubit` znajduje się w stanie $ \ket{\psi} = e ^ {i 0,5} \ sqrt {1/2} \ KET {0} + e ^ {i 0,5} \ sqrt {1/2} \ KET {1} $;</span><span class="sxs-lookup"><span data-stu-id="ad234-117">The following assert succeeds: `qubit` is in state $\ket{\psi}=e^{i 0.5}\sqrt{1/2}\ket{0}+e^{i 0.5}\sqrt{1/2}\ket{1}$;</span></span>

- `AssertPhase(0.0,qubit,10e-10);`

<span data-ttu-id="ad234-118">`qubit` jest w stanie $ \ket{\psi} = e ^ {i 0,5} \ sqrt {1/2} \ KET {0} + e ^ {-i 0,5} \ sqrt {1/2} \ KET {1} $;</span><span class="sxs-lookup"><span data-stu-id="ad234-118">`qubit` is in state $\ket{\psi}=e^{i 0.5}\sqrt{1/2}\ket{0}+e^{-i 0.5}\sqrt{1/2}\ket{1}$;</span></span>

- `AssertPhase(0.5,qubit,10e-10);`

<span data-ttu-id="ad234-119">`qubit` jest w stanie $ \ket{\psi} = e ^ {-i 2.2} \ sqrt {1/2} \ KET {0} + e ^ {i 0,2} \ sqrt {1/2} \ KET {1} $;</span><span class="sxs-lookup"><span data-stu-id="ad234-119">`qubit` is in state $\ket{\psi}=e^{-i 2.2}\sqrt{1/2}\ket{0}+e^{i 0.2}\sqrt{1/2}\ket{1}$;</span></span>

- `AssertPhase(-1.2,qubit,10e-10);`