---
uid: Microsoft.Quantum.Arithmetic.PhaseLittleEndian
title: PhaseLittleEndian typ zdefiniowany przez użytkownika
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: PhaseLittleEndian
qsharp.summary: >-
  Little-endian unsigned integers in QFT basis.

  For example, if $\ket{x}$ is the little-endian encoding of the integer $x$ in the computational basis, then $\operatorname{QFTLE} \ket{x}$ is the encoding of $x$ in the QFT basis.
ms.openlocfilehash: f1f792d62004a2765d4e63870f5a41a4377b0d34
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719733"
---
# <a name="phaselittleendian-user-defined-type"></a><span data-ttu-id="f7fbb-102">PhaseLittleEndian typ zdefiniowany przez użytkownika</span><span class="sxs-lookup"><span data-stu-id="f7fbb-102">PhaseLittleEndian user defined type</span></span>

<span data-ttu-id="f7fbb-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="f7fbb-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="f7fbb-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f7fbb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f7fbb-105">Małe liczby całkowite bez znaku endian w QFT.</span><span class="sxs-lookup"><span data-stu-id="f7fbb-105">Little-endian unsigned integers in QFT basis.</span></span>

<span data-ttu-id="f7fbb-106">Na przykład jeśli $ \ket{x} $ jest kodowaniem little-endian liczby całkowitej $x $ w oparciu o obliczenia, a następnie $ \operatorname{QFTLE} \ket{x} $ to kodowanie $x $ na podstawie QFT.</span><span class="sxs-lookup"><span data-stu-id="f7fbb-106">For example, if $\ket{x}$ is the little-endian encoding of the integer $x$ in the computational basis, then $\operatorname{QFTLE} \ket{x}$ is the encoding of $x$ in the QFT basis.</span></span>

```qsharp

newtype PhaseLittleEndian = (Qubit[]);
```



## <a name="remarks"></a><span data-ttu-id="f7fbb-107">Uwagi</span><span class="sxs-lookup"><span data-stu-id="f7fbb-107">Remarks</span></span>

<span data-ttu-id="f7fbb-108">Skracamy `PhaseLittleEndian` `PhaseLE` się w dokumentacji.</span><span class="sxs-lookup"><span data-stu-id="f7fbb-108">We abbreviate `PhaseLittleEndian` as `PhaseLE` in the documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="f7fbb-109">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="f7fbb-109">See Also</span></span>

- [<span data-ttu-id="f7fbb-110">Microsoft. Quantum. Canon. QFT</span><span class="sxs-lookup"><span data-stu-id="f7fbb-110">Microsoft.Quantum.Canon.QFT</span></span>](xref:Microsoft.Quantum.Canon.QFT)
- [<span data-ttu-id="f7fbb-111">Microsoft. Quantum. Canon. QFTLE</span><span class="sxs-lookup"><span data-stu-id="f7fbb-111">Microsoft.Quantum.Canon.QFTLE</span></span>](xref:Microsoft.Quantum.Canon.QFTLE)