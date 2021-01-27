---
uid: Microsoft.Quantum.Preparation.PrepareIdentity
title: PrepareIdentity, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareIdentity
qsharp.summary: >-
  Given a register, prepares that register in the maximally mixed state.

  The register is prepared in the $\boldone / 2^N$ state by applying the complete depolarizing channel to each qubit, where $N$ is the length of the register.
ms.openlocfilehash: ec7e813110ccd9e6d499fc469fa27249a182b870
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855888"
---
# <a name="prepareidentity-operation"></a><span data-ttu-id="cdb2b-102">PrepareIdentity, operacja</span><span class="sxs-lookup"><span data-stu-id="cdb2b-102">PrepareIdentity operation</span></span>

<span data-ttu-id="cdb2b-103">Przestrzeń nazw: [Microsoft. Quantum. przygotowaniu](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="cdb2b-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="cdb2b-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cdb2b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="cdb2b-105">Uwzględniając rejestr, przygotuje ten rejestr w stanie mieszanym Maximally.</span><span class="sxs-lookup"><span data-stu-id="cdb2b-105">Given a register, prepares that register in the maximally mixed state.</span></span>

<span data-ttu-id="cdb2b-106">Rejestr jest przygotowywany w stanie $ \boldone/2 ^ N $ przez zastosowanie kompletnego kanału depolarizing do każdego qubit, gdzie $N $ jest długością rejestru.</span><span class="sxs-lookup"><span data-stu-id="cdb2b-106">The register is prepared in the $\boldone / 2^N$ state by applying the complete depolarizing channel to each qubit, where $N$ is the length of the register.</span></span>

```qsharp
operation PrepareIdentity (register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="cdb2b-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="cdb2b-107">Input</span></span>

### <a name="register--qubit"></a><span data-ttu-id="cdb2b-108">Rejestr: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="cdb2b-108">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="cdb2b-109">Rejestr, którego stan ma zostać określony w sposób opisany powyżej.</span><span class="sxs-lookup"><span data-stu-id="cdb2b-109">A register whose state is to be depolarized in the manner described above.</span></span>



## <a name="output--unit"></a><span data-ttu-id="cdb2b-110">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cdb2b-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="cdb2b-111">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="cdb2b-111">See Also</span></span>

- [<span data-ttu-id="cdb2b-112">Microsoft. Quantum. przygotowaniu. PrepareSingleQubitIdentity</span><span class="sxs-lookup"><span data-stu-id="cdb2b-112">Microsoft.Quantum.Preparation.PrepareSingleQubitIdentity</span></span>](xref:Microsoft.Quantum.Preparation.PrepareSingleQubitIdentity)