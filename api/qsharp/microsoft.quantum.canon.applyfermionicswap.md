---
uid: Microsoft.Quantum.Canon.ApplyFermionicSWAP
title: ApplyFermionicSWAP, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyFermionicSWAP
qsharp.summary: Applies the Fermionic SWAP.
ms.openlocfilehash: 25dd91b200700d1474cf27bf1d0fa71d57f2e09b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718272"
---
# <a name="applyfermionicswap-operation"></a><span data-ttu-id="0d0a2-102">ApplyFermionicSWAP, operacja</span><span class="sxs-lookup"><span data-stu-id="0d0a2-102">ApplyFermionicSWAP operation</span></span>

<span data-ttu-id="0d0a2-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="0d0a2-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="0d0a2-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0d0a2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0d0a2-105">Stosuje Fermionic ZAMIANę.</span><span class="sxs-lookup"><span data-stu-id="0d0a2-105">Applies the Fermionic SWAP.</span></span>

```qsharp
operation ApplyFermionicSWAP (qubit1 : Qubit, qubit2 : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="0d0a2-106">Opis</span><span class="sxs-lookup"><span data-stu-id="0d0a2-106">Description</span></span>

<span data-ttu-id="0d0a2-107">Zasadniczo polega to na wymianie qubits przy zastosowaniu globalnej fazy-1, jeśli oba qubits są 1.</span><span class="sxs-lookup"><span data-stu-id="0d0a2-107">This essentially swaps the qubits while applying a global phase of -1 if both qubits are 1s.</span></span> <span data-ttu-id="0d0a2-108">Zachowuje symmetrization z orbitals.</span><span class="sxs-lookup"><span data-stu-id="0d0a2-108">Preserves anti-symmetrization of orbitals.</span></span>
<span data-ttu-id="0d0a2-109">Aby uzyskać więcej informacji, zobacz .</span><span class="sxs-lookup"><span data-stu-id="0d0a2-109">See  for more information.</span></span>

<span data-ttu-id="0d0a2-110">Ta operacja jest reprezentowana przez operatora jednostki \begin{align} f_ {swap} \mathrel{: =} \begin{bmatrix} 1 & 0 & 0 & 0 \\ \\ 0 & 0 & 1 & 0 \\ \\ 0 & 1 & 0 & 0 0 & 0 & 0 & \\ \\ -1 \\ \\ \end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="0d0a2-110">This operation is represented by the unitary operator \begin{align} f_{swap} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & -1 \\\\ \end{bmatrix}.</span></span>
<span data-ttu-id="0d0a2-111">\end{align}</span><span class="sxs-lookup"><span data-stu-id="0d0a2-111">\end{align}</span></span>

## <a name="input"></a><span data-ttu-id="0d0a2-112">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="0d0a2-112">Input</span></span>

### <a name="qubit1--qubit"></a><span data-ttu-id="0d0a2-113">qubit1: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="0d0a2-113">qubit1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="0d0a2-114">Pierwszy qubit, który ma zostać zamieniony.</span><span class="sxs-lookup"><span data-stu-id="0d0a2-114">The first qubit to be swapped.</span></span>


### <a name="qubit2--qubit"></a><span data-ttu-id="0d0a2-115">qubit2: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="0d0a2-115">qubit2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="0d0a2-116">Druga qubit do zamiany.</span><span class="sxs-lookup"><span data-stu-id="0d0a2-116">The second qubit to be swapped.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0d0a2-117">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0d0a2-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="0d0a2-118">Dokumentacja</span><span class="sxs-lookup"><span data-stu-id="0d0a2-118">References</span></span>

- [<span data-ttu-id="0d0a2-119">*Ryan Babbush, Nathana Wiebe, Jarrod McClean, Kuba McClain, Hartmut Neven, Garnet Kin-Lic kanał* , ArXiv: 1706.00023</span><span class="sxs-lookup"><span data-stu-id="0d0a2-119"> *Ryan Babbush, Nathan Wiebe, Jarrod McClean, James McClain, Hartmut Neven, Garnet Kin-Lic Chan* , arXiv:1706.00023 </span></span>](https://arxiv.org/pdf/1706.00023.pdf)

## <a name="see-also"></a><span data-ttu-id="0d0a2-120">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="0d0a2-120">See Also</span></span>

- [<span data-ttu-id="0d0a2-121">Microsoft. Quantum. wewnętrzna. SWAP</span><span class="sxs-lookup"><span data-stu-id="0d0a2-121">Microsoft.Quantum.Intrinsic.SWAP</span></span>](xref:Microsoft.Quantum.Intrinsic.SWAP)