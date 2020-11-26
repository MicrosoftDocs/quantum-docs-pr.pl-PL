---
uid: Microsoft.Quantum.Canon.HY
title: HY, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: HY
qsharp.summary: >-
  Applies the Y-basis analog to the Hadamard transformation that interchanges the Z and Y axes.

  The Y Hadamard transformation $H_Y = S H$ on a single qubit is:

  \begin{align} H_Y \mathrel{:=} \frac{1}{\sqrt{2}} \begin{bmatrix} 1 & 1 \\\\ i & -i \end{bmatrix}. \end{align}
ms.openlocfilehash: ceca8eab8cb8f16333cd7a1e3c24e6cebe4ec8d7
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206837"
---
# <a name="hy-operation"></a><span data-ttu-id="2faf4-102">HY, operacja</span><span class="sxs-lookup"><span data-stu-id="2faf4-102">HY operation</span></span>

<span data-ttu-id="2faf4-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="2faf4-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="2faf4-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2faf4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2faf4-105">Stosuje analogową wartość Y do transformacji Hadamard, która polega na wzajemnym zmianie osi Z i Y.</span><span class="sxs-lookup"><span data-stu-id="2faf4-105">Applies the Y-basis analog to the Hadamard transformation that interchanges the Z and Y axes.</span></span>

<span data-ttu-id="2faf4-106">Przekształcanie Hadamard Y $H _Y = S H $ na jednym qubit to:</span><span class="sxs-lookup"><span data-stu-id="2faf4-106">The Y Hadamard transformation $H_Y = S H$ on a single qubit is:</span></span>

<span data-ttu-id="2faf4-107">\begin{align} H_Y \mathrel{: =} \frac {1} {\sqrt {2} } \begin{bmatrix} 1 & 1 \\ \\ i &-i \end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="2faf4-107">\begin{align} H_Y \mathrel{:=} \frac{1}{\sqrt{2}} \begin{bmatrix} 1 & 1 \\\\ i & -i \end{bmatrix}.</span></span>
<span data-ttu-id="2faf4-108">\end{align}</span><span class="sxs-lookup"><span data-stu-id="2faf4-108">\end{align}</span></span>

```qsharp
operation HY (target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="2faf4-109">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="2faf4-109">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="2faf4-110">obiekt docelowy: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="2faf4-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="2faf4-111">Qubit, do którego należy zastosować bramę.</span><span class="sxs-lookup"><span data-stu-id="2faf4-111">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2faf4-112">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2faf4-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="2faf4-113">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="2faf4-113">See Also</span></span>

- [<span data-ttu-id="2faf4-114">Microsoft. Quantum. wewnętrzna. H</span><span class="sxs-lookup"><span data-stu-id="2faf4-114">Microsoft.Quantum.Intrinsic.H</span></span>](xref:Microsoft.Quantum.Intrinsic.H)