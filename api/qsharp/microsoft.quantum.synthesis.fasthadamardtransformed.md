---
uid: Microsoft.Quantum.Synthesis.FastHadamardTransformed
title: FastHadamardTransformed, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: FastHadamardTransformed
qsharp.summary: Computes Hadamard transform of a Boolean function in {-1,1} encoding using Yates's method
ms.openlocfilehash: 3e48701f22ddf154721355866e15a85fca0bc7df
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203097"
---
# <a name="fasthadamardtransformed-function"></a><span data-ttu-id="ca48f-102">FastHadamardTransformed, funkcja</span><span class="sxs-lookup"><span data-stu-id="ca48f-102">FastHadamardTransformed function</span></span>

<span data-ttu-id="ca48f-103">Przestrzeń nazw: [Microsoft. Quantum. Synteza](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="ca48f-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="ca48f-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ca48f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ca48f-105">Oblicza Hadamard transformację funkcji logicznej w {-1,1} kodowaniu przy użyciu metody Yates</span><span class="sxs-lookup"><span data-stu-id="ca48f-105">Computes Hadamard transform of a Boolean function in {-1,1} encoding using Yates's method</span></span>

```qsharp
function FastHadamardTransformed (func : Int[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="ca48f-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="ca48f-106">Input</span></span>

### <a name="func--int"></a><span data-ttu-id="ca48f-107">Func: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="ca48f-107">func : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="ca48f-108">Tabela prawdy w {-1,1} kodowaniu</span><span class="sxs-lookup"><span data-stu-id="ca48f-108">Truth table in {-1,1} encoding</span></span>



## <a name="output--int"></a><span data-ttu-id="ca48f-109">Wynik: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="ca48f-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="ca48f-110">Współczynniki widma funkcji</span><span class="sxs-lookup"><span data-stu-id="ca48f-110">Spectral coefficients of the function</span></span>