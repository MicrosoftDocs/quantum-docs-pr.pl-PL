---
uid: Microsoft.Quantum.Arithmetic.PhaseLittleEndian
title: PhaseLittleEndian typ zdefiniowany przez użytkownika
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: PhaseLittleEndian
qsharp.summary: >-
  Little-endian unsigned integers in QFT basis.

  For example, if $\ket{x}$ is the little-endian encoding of the integer $x$ in the computational basis, then $\operatorname{QFTLE} \ket{x}$ is the encoding of $x$ in the QFT basis.
ms.openlocfilehash: 45b824a74d664df0d5707264a3c616fb27c477b3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222426"
---
# <a name="phaselittleendian-user-defined-type"></a><span data-ttu-id="654fc-102">PhaseLittleEndian typ zdefiniowany przez użytkownika</span><span class="sxs-lookup"><span data-stu-id="654fc-102">PhaseLittleEndian user defined type</span></span>

<span data-ttu-id="654fc-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="654fc-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="654fc-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="654fc-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="654fc-105">Małe liczby całkowite bez znaku endian w QFT.</span><span class="sxs-lookup"><span data-stu-id="654fc-105">Little-endian unsigned integers in QFT basis.</span></span>

<span data-ttu-id="654fc-106">Na przykład jeśli $ \ket{x} $ jest kodowaniem little-endian liczby całkowitej $x $ w oparciu o obliczenia, a następnie $ \operatorname{QFTLE} \ket{x} $ to kodowanie $x $ na podstawie QFT.</span><span class="sxs-lookup"><span data-stu-id="654fc-106">For example, if $\ket{x}$ is the little-endian encoding of the integer $x$ in the computational basis, then $\operatorname{QFTLE} \ket{x}$ is the encoding of $x$ in the QFT basis.</span></span>

```qsharp

newtype PhaseLittleEndian = (Qubit[]);
```



## <a name="remarks"></a><span data-ttu-id="654fc-107">Uwagi</span><span class="sxs-lookup"><span data-stu-id="654fc-107">Remarks</span></span>

<span data-ttu-id="654fc-108">Skracamy `PhaseLittleEndian` `PhaseLE` się w dokumentacji.</span><span class="sxs-lookup"><span data-stu-id="654fc-108">We abbreviate `PhaseLittleEndian` as `PhaseLE` in the documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="654fc-109">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="654fc-109">See Also</span></span>

- [<span data-ttu-id="654fc-110">Microsoft. Quantum. Canon. QFT</span><span class="sxs-lookup"><span data-stu-id="654fc-110">Microsoft.Quantum.Canon.QFT</span></span>](xref:Microsoft.Quantum.Canon.QFT)
- [<span data-ttu-id="654fc-111">Microsoft. Quantum. Canon. QFTLE</span><span class="sxs-lookup"><span data-stu-id="654fc-111">Microsoft.Quantum.Canon.QFTLE</span></span>](xref:Microsoft.Quantum.Canon.QFTLE)