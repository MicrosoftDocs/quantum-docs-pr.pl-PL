---
uid: Microsoft.Quantum.Canon.ApplyAnd
title: ApplyAnd, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyAnd
qsharp.summary: Inverts a given target qubit if and only if both control qubits are in the 1 state, using measurement to perform the adjoint operation.
ms.openlocfilehash: b749013584c89273375da002ac36b3575085b7f2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219298"
---
# <a name="applyand-operation"></a><span data-ttu-id="b52a8-102">ApplyAnd, operacja</span><span class="sxs-lookup"><span data-stu-id="b52a8-102">ApplyAnd operation</span></span>

<span data-ttu-id="b52a8-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b52a8-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b52a8-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b52a8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b52a8-105">Odwraca daną wartość docelową qubit, jeśli i tylko wtedy, gdy oba kontrolki qubits znajdują się w stanie 1, przy użyciu miary do wykonania sąsiedniej operacji.</span><span class="sxs-lookup"><span data-stu-id="b52a8-105">Inverts a given target qubit if and only if both control qubits are in the 1 state, using measurement to perform the adjoint operation.</span></span>

```qsharp
operation ApplyAnd (control1 : Qubit, control2 : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="b52a8-106">Opis</span><span class="sxs-lookup"><span data-stu-id="b52a8-106">Description</span></span>

<span data-ttu-id="b52a8-107">Odwraca, `target` czy i tylko wtedy, gdy obie kontrolki są 1, ale zakłada, że `target` jest w stanie 0.</span><span class="sxs-lookup"><span data-stu-id="b52a8-107">Inverts `target` if and only if both controls are 1, but assumes that `target` is in state 0.</span></span>  <span data-ttu-id="b52a8-108">Operacja ma wartość T-Count 4, T-Głębokość 2 i nie wymaga pomocnika qubit. w związku z tym może być preferowana operacja CCNOT, jeśli `target` jest ona znana jako 0.</span><span class="sxs-lookup"><span data-stu-id="b52a8-108">The operation has T-count 4, T-depth 2 and requires no helper qubit, and may therefore be preferable to a CCNOT operation, if `target` is known to be 0.</span></span>  <span data-ttu-id="b52a8-109">Sąsiadująco z tą operacją jest oparte na pomiarach i nie wymaga żadnych bram T.</span><span class="sxs-lookup"><span data-stu-id="b52a8-109">The adjoint of this operation is measurement based and requires no T gates.</span></span>

<span data-ttu-id="b52a8-110">Kontrolowana aplikacja tej operacji nie wymaga pomocnika qubit, `2^c` `Rz` bram i nie jest zoptymalizowana pod kątem głębokości, gdzie `c` jest liczbą ogólnych formantów qubits, łącznie z dwoma kontrolkami z `ApplyAnd` operacji.</span><span class="sxs-lookup"><span data-stu-id="b52a8-110">The controlled application of this operation requires no helper qubit, `2^c` `Rz` gates and is not optimized for depth, where `c` is the number of overall control qubits including the two controls from the `ApplyAnd` operation.</span></span>  <span data-ttu-id="b52a8-111">Aplikacja z możliwością `2^c - 1` `Rz` współdziałania wymaga bram (o kącie o podwójnym rozmiarze niesąsiadującej operacji), nie qubit pomocnika i nie jest zoptymalizowana pod kątem głębokości.</span><span class="sxs-lookup"><span data-stu-id="b52a8-111">The adjoint controlled application requires `2^c - 1` `Rz` gates (with an angle twice the size of the non-adjoint operation), no helper qubit and is not optimized for depth.</span></span>

## <a name="input"></a><span data-ttu-id="b52a8-112">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="b52a8-112">Input</span></span>

### <a name="control1--qubit"></a><span data-ttu-id="b52a8-113">Control1: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="b52a8-113">control1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="b52a8-114">Pierwszy formant qubit</span><span class="sxs-lookup"><span data-stu-id="b52a8-114">First control qubit</span></span>


### <a name="control2--qubit"></a><span data-ttu-id="b52a8-115">Control2: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="b52a8-115">control2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="b52a8-116">Druga kontrolka qubit</span><span class="sxs-lookup"><span data-stu-id="b52a8-116">Second control qubit</span></span>


### <a name="target--qubit"></a><span data-ttu-id="b52a8-117">obiekt docelowy: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="b52a8-117">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="b52a8-118">Docelowa qubit pomocnicza; musi być w stanie 0</span><span class="sxs-lookup"><span data-stu-id="b52a8-118">Target auxiliary qubit; must be in state 0</span></span>



## <a name="output--unit"></a><span data-ttu-id="b52a8-119">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b52a8-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="b52a8-120">Odwołania</span><span class="sxs-lookup"><span data-stu-id="b52a8-120">References</span></span>

- <span data-ttu-id="b52a8-121">Cody Nowak: "Nowa konstrukcja dla bramy Toffoli odpornej na uszkodzenia", biorev. obr. A 87, 022328, 2013 [ArXiv: 1212.5069](https://arxiv.org/abs/1212.5069) DOI: 10.1103/PhysRevA. 87.022328</span><span class="sxs-lookup"><span data-stu-id="b52a8-121">Cody Jones: "Novel constructions for the fault-tolerant Toffoli gate", Phys. Rev. A 87, 022328, 2013 [arXiv:1212.5069](https://arxiv.org/abs/1212.5069) doi:10.1103/PhysRevA.87.022328</span></span>
- <span data-ttu-id="b52a8-122">Craig Gidney: "Halving kosztów dodawania jednostek Quantum 2, strona 74, 2018 [ArXiv: 1709.06648](https://arxiv.org/abs/1709.06648) DOI: 10.1103/PhysRevA. 85.044302</span><span class="sxs-lookup"><span data-stu-id="b52a8-122">Craig Gidney: "Halving the cost of quantum addition", Quantum 2, page 74, 2018 [arXiv:1709.06648](https://arxiv.org/abs/1709.06648) doi:10.1103/PhysRevA.85.044302</span></span>
- <span data-ttu-id="b52a8-123">Mathias Soeken: "usługi Quantum Oracle obwodów i wzorzec dla Boże Narodzenie", [artykuł w blogu z 19 grudnia 2019](https://msoeken.github.io/blog_qac.html) (Uwaga: wyjaśnienie dotyczące wielu kontrolowanej konstrukcji)</span><span class="sxs-lookup"><span data-stu-id="b52a8-123">Mathias Soeken: "Quantum Oracle Circuits and the Christmas Tree Pattern", [Blog article from December 19, 2019](https://msoeken.github.io/blog_qac.html) (note: explains the multiple controlled construction)</span></span>