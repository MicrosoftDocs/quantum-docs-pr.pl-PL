---
uid: Microsoft.Quantum.Canon.ApplyLowDepthAnd
title: ApplyLowDepthAnd, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyLowDepthAnd
qsharp.summary: Inverts a given target qubit if and only if both control qubits are in the 1 state, with T-depth 1, using measurement to perform the adjoint operation.
ms.openlocfilehash: 092a350e42d8d90942de13530fefd761b5187e1d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717985"
---
# <a name="applylowdepthand-operation"></a><span data-ttu-id="6e6d5-102">ApplyLowDepthAnd, operacja</span><span class="sxs-lookup"><span data-stu-id="6e6d5-102">ApplyLowDepthAnd operation</span></span>

<span data-ttu-id="6e6d5-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="6e6d5-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="6e6d5-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6e6d5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6e6d5-105">Odwraca podaną wartość docelową qubit, jeśli i tylko wtedy, gdy oba kontrolki qubits są w stanie 1, z głębokością T 1, przy użyciu miary do wykonania sąsiedniej operacji.</span><span class="sxs-lookup"><span data-stu-id="6e6d5-105">Inverts a given target qubit if and only if both control qubits are in the 1 state, with T-depth 1, using measurement to perform the adjoint operation.</span></span>

```qsharp
operation ApplyLowDepthAnd (control1 : Qubit, control2 : Qubit, target : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="6e6d5-106">Opis</span><span class="sxs-lookup"><span data-stu-id="6e6d5-106">Description</span></span>

<span data-ttu-id="6e6d5-107">Odwraca, `target` czy i tylko wtedy, gdy obie kontrolki są 1, ale zakłada, że `target` jest w stanie 0.</span><span class="sxs-lookup"><span data-stu-id="6e6d5-107">Inverts `target` if and only if both controls are 1, but assumes that `target` is in state 0.</span></span>  <span data-ttu-id="6e6d5-108">Operacja ma wartość T-Count 4, T-głębokość 1 i wymaga jednego pomocnika qubit i dlatego może być zalecana dla operacji CCNOT, jeśli `target` jest znana jako 0.</span><span class="sxs-lookup"><span data-stu-id="6e6d5-108">The operation has T-count 4, T-depth 1 and requires one helper qubit, and may therefore be preferable to a CCNOT operation, if `target` is known to be 0.</span></span>  <span data-ttu-id="6e6d5-109">Sąsiednia operacja jest oparta na pomiarach i nie wymaga żadnych bram T i nie qubit pomocnika.</span><span class="sxs-lookup"><span data-stu-id="6e6d5-109">The adjoint of this operation is measurement based and requires no T gates, and no helper qubit.</span></span>

## <a name="input"></a><span data-ttu-id="6e6d5-110">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="6e6d5-110">Input</span></span>

### <a name="control1--qubit"></a><span data-ttu-id="6e6d5-111">Control1: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="6e6d5-111">control1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="6e6d5-112">Pierwszy formant qubit</span><span class="sxs-lookup"><span data-stu-id="6e6d5-112">First control qubit</span></span>


### <a name="control2--qubit"></a><span data-ttu-id="6e6d5-113">Control2: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="6e6d5-113">control2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="6e6d5-114">Druga kontrolka qubit</span><span class="sxs-lookup"><span data-stu-id="6e6d5-114">Second control qubit</span></span>


### <a name="target--qubit"></a><span data-ttu-id="6e6d5-115">obiekt docelowy: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="6e6d5-115">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="6e6d5-116">Docelowa qubit pomocnicza; musi być w stanie 0</span><span class="sxs-lookup"><span data-stu-id="6e6d5-116">Target auxiliary qubit; must be in state 0</span></span>



## <a name="output--unit"></a><span data-ttu-id="6e6d5-117">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6e6d5-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="6e6d5-118">Dokumentacja</span><span class="sxs-lookup"><span data-stu-id="6e6d5-118">References</span></span>

- <span data-ttu-id="6e6d5-119">Cody Nowak: "Nowa konstrukcja dla bramy Toffoli odpornej na uszkodzenia", biorev. obr. A 87, 022328, 2013 [ArXiv: 1212.5069](https://arxiv.org/abs/1212.5069) DOI: 10.1103/PhysRevA. 87.022328</span><span class="sxs-lookup"><span data-stu-id="6e6d5-119">Cody Jones: "Novel constructions for the fault-tolerant Toffoli gate", Phys. Rev. A 87, 022328, 2013 [arXiv:1212.5069](https://arxiv.org/abs/1212.5069) doi:10.1103/PhysRevA.87.022328</span></span>
- <span data-ttu-id="6e6d5-120">Piotr Selinger: "" Quantum obwodów "T-głębokości" i "," Bio. Rev. A 87, 042302, 2013 [ArXiv: 1210.0974](https://arxiv.org/abs/1210.0974) DOI: 10.1103/PhysRevA. 87.042302</span><span class="sxs-lookup"><span data-stu-id="6e6d5-120">Peter Selinger: "Quantum circuits of T-depth one", Phys. Rev. A 87, 042302, 2013 [arXiv:1210.0974](https://arxiv.org/abs/1210.0974) doi:10.1103/PhysRevA.87.042302</span></span>