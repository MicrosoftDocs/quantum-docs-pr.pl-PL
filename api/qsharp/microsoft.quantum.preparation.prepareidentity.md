---
uid: Microsoft.Quantum.Preparation.PrepareIdentity
title: PrepareIdentity, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareIdentity
qsharp.summary: >-
  Given a register, prepares that register in the maximally mixed state.

  The register is prepared in the $\boldone / 2^N$ state by applying the complete depolarizing channel to each qubit, where $N$ is the length of the register.
ms.openlocfilehash: a3f96fbdafb19c90fb2b563243600cca60841566
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724891"
---
# <a name="prepareidentity-operation"></a><span data-ttu-id="9a56a-102">PrepareIdentity, operacja</span><span class="sxs-lookup"><span data-stu-id="9a56a-102">PrepareIdentity operation</span></span>

<span data-ttu-id="9a56a-103">Przestrzeń nazw: [Microsoft. Quantum. przygotowaniu](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="9a56a-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="9a56a-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9a56a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9a56a-105">Uwzględniając rejestr, przygotuje ten rejestr w stanie mieszanym Maximally.</span><span class="sxs-lookup"><span data-stu-id="9a56a-105">Given a register, prepares that register in the maximally mixed state.</span></span>

<span data-ttu-id="9a56a-106">Rejestr jest przygotowywany w stanie $ \boldone/2 ^ N $ przez zastosowanie kompletnego kanału depolarizing do każdego qubit, gdzie $N $ jest długością rejestru.</span><span class="sxs-lookup"><span data-stu-id="9a56a-106">The register is prepared in the $\boldone / 2^N$ state by applying the complete depolarizing channel to each qubit, where $N$ is the length of the register.</span></span>

```qsharp
operation PrepareIdentity (register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="9a56a-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="9a56a-107">Input</span></span>

### <a name="register--qubit"></a><span data-ttu-id="9a56a-108">Rejestr: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="9a56a-108">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="9a56a-109">Rejestr, którego stan ma zostać określony w sposób opisany powyżej.</span><span class="sxs-lookup"><span data-stu-id="9a56a-109">A register whose state is to be depolarized in the manner described above.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9a56a-110">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9a56a-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="9a56a-111">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="9a56a-111">See Also</span></span>

- [<span data-ttu-id="9a56a-112">Microsoft. Quantum. przygotowaniu. PrepareSingleQubitIdentity</span><span class="sxs-lookup"><span data-stu-id="9a56a-112">Microsoft.Quantum.Preparation.PrepareSingleQubitIdentity</span></span>](xref:Microsoft.Quantum.Preparation.PrepareSingleQubitIdentity)