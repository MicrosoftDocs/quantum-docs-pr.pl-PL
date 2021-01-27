---
uid: Microsoft.Quantum.Preparation.PrepareSingleQubitIdentity
title: PrepareSingleQubitIdentity, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareSingleQubitIdentity
qsharp.summary: >-
  Prepares a qubit in the maximally mixed state.

  It prepares the given qubit in the $\boldone / 2$ state by applying the depolarizing channel $$ \begin{align} \Omega(\rho) \mathrel{:=} \frac{1}{4} \sum_{\mu \in \{0, 1, 2, 3\}} \sigma\_{\mu} \rho \sigma\_{\mu}^{\dagger}, \end{align} $$ where $\sigma\_i$ is the $i$th Pauli operator, and where $\rho$ is a density operator representing a mixed state.
ms.openlocfilehash: c6c9b5724354d6ee034dd8b6733901ebdd8072d6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856868"
---
# <a name="preparesinglequbitidentity-operation"></a><span data-ttu-id="52a9d-102">PrepareSingleQubitIdentity, operacja</span><span class="sxs-lookup"><span data-stu-id="52a9d-102">PrepareSingleQubitIdentity operation</span></span>

<span data-ttu-id="52a9d-103">Przestrzeń nazw: [Microsoft. Quantum. przygotowaniu](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="52a9d-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="52a9d-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="52a9d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="52a9d-105">Przygotowuje qubit w stanie mieszanym Maximally.</span><span class="sxs-lookup"><span data-stu-id="52a9d-105">Prepares a qubit in the maximally mixed state.</span></span>

<span data-ttu-id="52a9d-106">Przygotowuje daną qubit w stanie $ \boldone/$2 przez zastosowanie depolarizing kanału $ $ \begin{align} \Omega (\rho) \mathrel{: =} \frac {1} {4} \ sum_ {\mu \In \{ 0, 1, 2, 3 \} } \sigma \_ {\mu} \rho \sigma \_ {\mu} ^ {\dagger}, \end{align} $ $ WHERE $ \sigma \_ i $ jest operatorem $i $ th Pauli i gdzie $ \rho $ jest operatorem gęstości reprezentującym stan mieszany.</span><span class="sxs-lookup"><span data-stu-id="52a9d-106">It prepares the given qubit in the $\boldone / 2$ state by applying the depolarizing channel $$ \begin{align} \Omega(\rho) \mathrel{:=} \frac{1}{4} \sum_{\mu \in \{0, 1, 2, 3\}} \sigma\_{\mu} \rho \sigma\_{\mu}^{\dagger}, \end{align} $$ where $\sigma\_i$ is the $i$th Pauli operator, and where $\rho$ is a density operator representing a mixed state.</span></span>

```qsharp
operation PrepareSingleQubitIdentity (qubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="52a9d-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="52a9d-107">Input</span></span>

### <a name="qubit--qubit"></a><span data-ttu-id="52a9d-108">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="52a9d-108">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="52a9d-109">Qubit, którego stan ma zostać określony w sposób opisany powyżej.</span><span class="sxs-lookup"><span data-stu-id="52a9d-109">A qubit whose state is to be depolarized in the manner described above.</span></span>



## <a name="output--unit"></a><span data-ttu-id="52a9d-110">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="52a9d-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="52a9d-111">Uwagi</span><span class="sxs-lookup"><span data-stu-id="52a9d-111">Remarks</span></span>

<span data-ttu-id="52a9d-112">Stan mieszany $ \boldone/$2 opisujący wynik zastosowania tej operacji do stanu niejawnie opisuje wartość oczekiwaną w przypadku losowych wyborów wykonanych w tej operacji.</span><span class="sxs-lookup"><span data-stu-id="52a9d-112">The mixed state $\boldone / 2$ describing the result of applying this operation to a state implicitly describes an expectation value over random choices made in this operation.</span></span>
<span data-ttu-id="52a9d-113">W tym przypadku dla każdej pojedynczej aplikacji ta operacja mapuje czyste Stany w czyste Stany, ale działa zgodnie z opisem w temacie oczekiwanie.</span><span class="sxs-lookup"><span data-stu-id="52a9d-113">Thus, for any single application, this operation maps pure states to pure states, but it acts as described in expectation.</span></span>
<span data-ttu-id="52a9d-114">W szczególności tej operacji można użyć w procesie Tomography, aby mierzyć składniki *niebędące jednostką* kanału.</span><span class="sxs-lookup"><span data-stu-id="52a9d-114">In particular, this operation can be used in process tomography to measure the *non-unital* components of a channel.</span></span>