---
uid: Microsoft.Quantum.Synthesis.FastHadamardTransformed
title: FastHadamardTransformed, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: FastHadamardTransformed
qsharp.summary: Computes Hadamard transform of a Boolean function in {-1,1} encoding using Yates's method
ms.openlocfilehash: 2b84e92d08a3baad2552780cae91f447830cac82
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725185"
---
# <a name="fasthadamardtransformed-function"></a><span data-ttu-id="d8b90-102">FastHadamardTransformed, funkcja</span><span class="sxs-lookup"><span data-stu-id="d8b90-102">FastHadamardTransformed function</span></span>

<span data-ttu-id="d8b90-103">Przestrzeń nazw: [Microsoft. Quantum. Synteza](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="d8b90-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="d8b90-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d8b90-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d8b90-105">Oblicza Hadamard transformację funkcji logicznej w {-1,1} kodowaniu przy użyciu metody Yates</span><span class="sxs-lookup"><span data-stu-id="d8b90-105">Computes Hadamard transform of a Boolean function in {-1,1} encoding using Yates's method</span></span>

```qsharp
function FastHadamardTransformed (func : Int[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="d8b90-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="d8b90-106">Input</span></span>

### <a name="func--int"></a><span data-ttu-id="d8b90-107">Func: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="d8b90-107">func : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="d8b90-108">Tabela prawdy w {-1,1} kodowaniu</span><span class="sxs-lookup"><span data-stu-id="d8b90-108">Truth table in {-1,1} encoding</span></span>



## <a name="output--int"></a><span data-ttu-id="d8b90-109">Wynik: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="d8b90-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="d8b90-110">Współczynniki widma funkcji</span><span class="sxs-lookup"><span data-stu-id="d8b90-110">Spectral coefficients of the function</span></span>