---
uid: Microsoft.Quantum.Synthesis.FastHadamardTransformed
title: FastHadamardTransformed, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: FastHadamardTransformed
qsharp.summary: Computes Hadamard transform of a Boolean function in {-1,1} encoding using Yates's method
ms.openlocfilehash: be54413ef2d3fdaf7ddc726bc0906adb4ec382ff
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855452"
---
# <a name="fasthadamardtransformed-function"></a><span data-ttu-id="a78a3-102">FastHadamardTransformed, funkcja</span><span class="sxs-lookup"><span data-stu-id="a78a3-102">FastHadamardTransformed function</span></span>

<span data-ttu-id="a78a3-103">Przestrzeń nazw: [Microsoft. Quantum. Synteza](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="a78a3-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="a78a3-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a78a3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a78a3-105">Oblicza Hadamard transformację funkcji logicznej w {-1,1} kodowaniu przy użyciu metody Yates</span><span class="sxs-lookup"><span data-stu-id="a78a3-105">Computes Hadamard transform of a Boolean function in {-1,1} encoding using Yates's method</span></span>

```qsharp
function FastHadamardTransformed (func : Int[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="a78a3-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="a78a3-106">Input</span></span>

### <a name="func--int"></a><span data-ttu-id="a78a3-107">Func: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="a78a3-107">func : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="a78a3-108">Tabela prawdy w {-1,1} kodowaniu</span><span class="sxs-lookup"><span data-stu-id="a78a3-108">Truth table in {-1,1} encoding</span></span>



## <a name="output--int"></a><span data-ttu-id="a78a3-109">Wynik: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="a78a3-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="a78a3-110">Współczynniki widma funkcji</span><span class="sxs-lookup"><span data-stu-id="a78a3-110">Spectral coefficients of the function</span></span>

## <a name="example"></a><span data-ttu-id="a78a3-111">Przykład</span><span class="sxs-lookup"><span data-stu-id="a78a3-111">Example</span></span>

```qsharp
FastHadamardTransformed([1, 1, 1, -1]); // [2, 2, 2, -2]
```