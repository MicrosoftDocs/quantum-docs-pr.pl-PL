---
uid: Microsoft.Quantum.AmplitudeAmplification.StandardAmplitudeAmplification
title: StandardAmplitudeAmplification, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: StandardAmplitudeAmplification
qsharp.summary: Standard Amplitude Amplification algorithm
ms.openlocfilehash: 23a2b3dbe5ea404059994167f69e11458c0c22ea
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191180"
---
# <a name="standardamplitudeamplification-function"></a><span data-ttu-id="e5acd-102">StandardAmplitudeAmplification, funkcja</span><span class="sxs-lookup"><span data-stu-id="e5acd-102">StandardAmplitudeAmplification function</span></span>

<span data-ttu-id="e5acd-103">Przestrzeń nazw: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="e5acd-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="e5acd-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e5acd-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e5acd-105">Algorytm wzmocnienia amplitudy standardowej</span><span class="sxs-lookup"><span data-stu-id="e5acd-105">Standard Amplitude Amplification algorithm</span></span>

```qsharp
function StandardAmplitudeAmplification (nIterations : Int, stateOracle : Microsoft.Quantum.Oracles.StateOracle, idxFlagQubit : Int) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="e5acd-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="e5acd-106">Input</span></span>

### <a name="niterations--int"></a><span data-ttu-id="e5acd-107">nIterations: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e5acd-107">nIterations : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e5acd-108">Liczba iteracji $n $ wzmocnienia amplitudy</span><span class="sxs-lookup"><span data-stu-id="e5acd-108">Number of iterations $n$ of amplitude amplification</span></span>


### <a name="stateoracle--stateoracle"></a><span data-ttu-id="e5acd-109">stateOracle: [stateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="e5acd-109">stateOracle : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>

<span data-ttu-id="e5acd-110">Jednostkowa firma Oracle $A $, która przygotowuje stan początkowy</span><span class="sxs-lookup"><span data-stu-id="e5acd-110">Unitary oracle $A$ that prepares start state</span></span>


### <a name="idxflagqubit--int"></a><span data-ttu-id="e5acd-111">idxFlagQubit: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e5acd-111">idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e5acd-112">Indeks do flagi qubit</span><span class="sxs-lookup"><span data-stu-id="e5acd-112">Index to flag qubit</span></span>



## <a name="output--qubit--unit--is-adj--ctl"></a><span data-ttu-id="e5acd-113">Output: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [Jednostka](xref:microsoft.quantum.lang-ref.unit) > jest korektą i listą CTL</span><span class="sxs-lookup"><span data-stu-id="e5acd-113">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="e5acd-114">Operacja implementująca algorytm Quantum dla standardowego wzmocnienia amplitudy</span><span class="sxs-lookup"><span data-stu-id="e5acd-114">An operation that implements the standard amplitude amplification quantum algorithm</span></span>

## <a name="remarks"></a><span data-ttu-id="e5acd-115">Uwagi</span><span class="sxs-lookup"><span data-stu-id="e5acd-115">Remarks</span></span>

<span data-ttu-id="e5acd-116">Jest to standardowy algorytm wzmocnienia amplitudy uzyskany przez wybór faz odbicia obliczanych przez `AmpAmpPhasesStandard` założenie, że \Begin{align} A\ket {0} \_ {f} \ket {0} \_ s = \lambda\ket {1} \_ f\ket {\ Text {Target}} \_ s + \sqrt{1-| \lambda | ^ 2} \ket {0} \_ F\cdots, \end{align} ta operacja przygotowuje stan \begin{align} \operatorname{AmpAmpByOracle}\ket {0} \_ {f} \ket {0} \_ s = \sin ((2n + 1) \sin ^ {-1} (\lambda)) \ket {1} \_ f\ket {\ Text {Target}} \_ s + \cdots\ket {0} \_ f \end{align} w większości przypadków `flagQubit` i `auxiliaryRegister` jest inicjowany w stanie $ \ket {0} \_ f\ket {0} \_ a $.</span><span class="sxs-lookup"><span data-stu-id="e5acd-116">This is the standard amplitude amplification algorithm obtained by a choice of reflection phases computed by `AmpAmpPhasesStandard` Assuming that \begin{align} A\ket{0}\_{f}\ket{0}\_s= \lambda\ket{1}\_f\ket{\text{target}}\_s + \sqrt{1-|\lambda|^2}\ket{0}\_f\cdots, \end{align} this operation prepares the state \begin{align} \operatorname{AmpAmpByOracle}\ket{0}\_{f}\ket{0}\_s= \sin((2n+1)\sin^{-1}(\lambda))\ket{1}\_f\ket{\text{target}}\_s + \cdots\ket{0}\_f \end{align} In most cases, `flagQubit` and `auxiliaryRegister` is initialized in the state $\ket{0}\_f\ket{0}\_a$.</span></span>

## <a name="references"></a><span data-ttu-id="e5acd-117">Odwołania</span><span class="sxs-lookup"><span data-stu-id="e5acd-117">References</span></span>

- [<span data-ttu-id="e5acd-118">*G. Brassard, P. Hoyer, M. Mosca, A. Tapp*</span><span class="sxs-lookup"><span data-stu-id="e5acd-118"> *G. Brassard, P. Hoyer, M. Mosca, A. Tapp* </span></span>](https://arxiv.org/abs/quant-ph/0005055)