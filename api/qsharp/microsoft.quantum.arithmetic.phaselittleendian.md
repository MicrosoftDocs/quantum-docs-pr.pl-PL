---
uid: Microsoft.Quantum.Arithmetic.PhaseLittleEndian
title: PhaseLittleEndian typ zdefiniowany przez użytkownika
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: PhaseLittleEndian
qsharp.summary: >-
  Little-endian unsigned integers in QFT basis.

  For example, if $\ket{x}$ is the little-endian encoding of the integer $x$ in the computational basis, then $\operatorname{QFTLE} \ket{x}$ is the encoding of $x$ in the QFT basis.
ms.openlocfilehash: 59df1db31090f875ccd261fe6cc43995ba57b963
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842996"
---
# <a name="phaselittleendian-user-defined-type"></a><span data-ttu-id="fd688-102">PhaseLittleEndian typ zdefiniowany przez użytkownika</span><span class="sxs-lookup"><span data-stu-id="fd688-102">PhaseLittleEndian user defined type</span></span>

<span data-ttu-id="fd688-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="fd688-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="fd688-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fd688-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fd688-105">Małe liczby całkowite bez znaku endian w QFT.</span><span class="sxs-lookup"><span data-stu-id="fd688-105">Little-endian unsigned integers in QFT basis.</span></span>

<span data-ttu-id="fd688-106">Na przykład jeśli $ \ket{x} $ jest kodowaniem little-endian liczby całkowitej $x $ w oparciu o obliczenia, a następnie $ \operatorname{QFTLE} \ket{x} $ to kodowanie $x $ na podstawie QFT.</span><span class="sxs-lookup"><span data-stu-id="fd688-106">For example, if $\ket{x}$ is the little-endian encoding of the integer $x$ in the computational basis, then $\operatorname{QFTLE} \ket{x}$ is the encoding of $x$ in the QFT basis.</span></span>

```qsharp

newtype PhaseLittleEndian = (Qubit[]);
```



## <a name="remarks"></a><span data-ttu-id="fd688-107">Uwagi</span><span class="sxs-lookup"><span data-stu-id="fd688-107">Remarks</span></span>

<span data-ttu-id="fd688-108">Skracamy `PhaseLittleEndian` `PhaseLE` się w dokumentacji.</span><span class="sxs-lookup"><span data-stu-id="fd688-108">We abbreviate `PhaseLittleEndian` as `PhaseLE` in the documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="fd688-109">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="fd688-109">See Also</span></span>

- [<span data-ttu-id="fd688-110">Microsoft. Quantum. Canon. QFT</span><span class="sxs-lookup"><span data-stu-id="fd688-110">Microsoft.Quantum.Canon.QFT</span></span>](xref:Microsoft.Quantum.Canon.QFT)
- [<span data-ttu-id="fd688-111">Microsoft. Quantum. Canon. QFTLE</span><span class="sxs-lookup"><span data-stu-id="fd688-111">Microsoft.Quantum.Canon.QFTLE</span></span>](xref:Microsoft.Quantum.Canon.QFTLE)