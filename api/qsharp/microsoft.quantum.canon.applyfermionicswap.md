---
uid: Microsoft.Quantum.Canon.ApplyFermionicSWAP
title: ApplyFermionicSWAP, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyFermionicSWAP
qsharp.summary: Applies the Fermionic SWAP.
ms.openlocfilehash: 0c470705843a6360df0a72374570d86571397e41
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218805"
---
# <a name="applyfermionicswap-operation"></a><span data-ttu-id="93807-102">ApplyFermionicSWAP, operacja</span><span class="sxs-lookup"><span data-stu-id="93807-102">ApplyFermionicSWAP operation</span></span>

<span data-ttu-id="93807-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="93807-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="93807-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="93807-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="93807-105">Stosuje Fermionic ZAMIANę.</span><span class="sxs-lookup"><span data-stu-id="93807-105">Applies the Fermionic SWAP.</span></span>

```qsharp
operation ApplyFermionicSWAP (qubit1 : Qubit, qubit2 : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="93807-106">Opis</span><span class="sxs-lookup"><span data-stu-id="93807-106">Description</span></span>

<span data-ttu-id="93807-107">Zasadniczo polega to na wymianie qubits przy zastosowaniu globalnej fazy-1, jeśli oba qubits są 1.</span><span class="sxs-lookup"><span data-stu-id="93807-107">This essentially swaps the qubits while applying a global phase of -1 if both qubits are 1s.</span></span> <span data-ttu-id="93807-108">Zachowuje symmetrization z orbitals.</span><span class="sxs-lookup"><span data-stu-id="93807-108">Preserves anti-symmetrization of orbitals.</span></span>
<span data-ttu-id="93807-109">Aby uzyskać więcej informacji, zobacz .</span><span class="sxs-lookup"><span data-stu-id="93807-109">See  for more information.</span></span>

<span data-ttu-id="93807-110">Ta operacja jest reprezentowana przez operatora jednostki \begin{align} f_ {swap} \mathrel{: =} \begin{bmatrix} 1 & 0 & 0 & 0 \\ \\ 0 & 0 & 1 & 0 \\ \\ 0 & 1 & 0 & 0 0 & 0 & 0 & \\ \\ -1 \\ \\ \end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="93807-110">This operation is represented by the unitary operator \begin{align} f_{swap} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & -1 \\\\ \end{bmatrix}.</span></span>
<span data-ttu-id="93807-111">\end{align}</span><span class="sxs-lookup"><span data-stu-id="93807-111">\end{align}</span></span>

## <a name="input"></a><span data-ttu-id="93807-112">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="93807-112">Input</span></span>

### <a name="qubit1--qubit"></a><span data-ttu-id="93807-113">qubit1: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="93807-113">qubit1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="93807-114">Pierwszy qubit, który ma zostać zamieniony.</span><span class="sxs-lookup"><span data-stu-id="93807-114">The first qubit to be swapped.</span></span>


### <a name="qubit2--qubit"></a><span data-ttu-id="93807-115">qubit2: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="93807-115">qubit2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="93807-116">Druga qubit do zamiany.</span><span class="sxs-lookup"><span data-stu-id="93807-116">The second qubit to be swapped.</span></span>



## <a name="output--unit"></a><span data-ttu-id="93807-117">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="93807-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="93807-118">Odwołania</span><span class="sxs-lookup"><span data-stu-id="93807-118">References</span></span>

- [<span data-ttu-id="93807-119">*Ryan Babbush, Nathana Wiebe, Jarrod McClean, Kuba McClain, Hartmut Neven, Garnet Kin-Lic kanał*, ArXiv: 1706.00023</span><span class="sxs-lookup"><span data-stu-id="93807-119"> *Ryan Babbush, Nathan Wiebe, Jarrod McClean, James McClain, Hartmut Neven, Garnet Kin-Lic Chan*, arXiv:1706.00023 </span></span>](https://arxiv.org/pdf/1706.00023.pdf)

## <a name="see-also"></a><span data-ttu-id="93807-120">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="93807-120">See Also</span></span>

- [<span data-ttu-id="93807-121">Microsoft. Quantum. wewnętrzna. SWAP</span><span class="sxs-lookup"><span data-stu-id="93807-121">Microsoft.Quantum.Intrinsic.SWAP</span></span>](xref:Microsoft.Quantum.Intrinsic.SWAP)