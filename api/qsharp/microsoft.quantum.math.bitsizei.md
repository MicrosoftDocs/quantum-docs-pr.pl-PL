---
uid: Microsoft.Quantum.Math.BitSizeI
title: BitSizeI, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BitSizeI
qsharp.summary: >-
  For a non-negative integer `a`, returns the number of bits required to represent `a`.

  That is, returns the smallest $n$ such that $a < 2^n$.
ms.openlocfilehash: 561450ef43144aa4d7820e1f15d9300018104acd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96195855"
---
# <a name="bitsizei-function"></a><span data-ttu-id="be66e-102">BitSizeI, funkcja</span><span class="sxs-lookup"><span data-stu-id="be66e-102">BitSizeI function</span></span>

<span data-ttu-id="be66e-103">Przestrzeń nazw: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="be66e-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="be66e-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="be66e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="be66e-105">Dla nieujemnej liczby całkowitej `a` zwraca liczbę bitów wymaganych do reprezentowania `a` .</span><span class="sxs-lookup"><span data-stu-id="be66e-105">For a non-negative integer `a`, returns the number of bits required to represent `a`.</span></span>

<span data-ttu-id="be66e-106">Oznacza to, że program zwraca najmniejszy $n $, który $a < 2 ^ n $.</span><span class="sxs-lookup"><span data-stu-id="be66e-106">That is, returns the smallest $n$ such that $a < 2^n$.</span></span>

```qsharp
function BitSizeI (a : Int) : Int
```


## <a name="input"></a><span data-ttu-id="be66e-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="be66e-107">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="be66e-108">Odp.: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="be66e-108">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="be66e-109">Liczba całkowita, której rozmiar bitowy ma zostać obliczony.</span><span class="sxs-lookup"><span data-stu-id="be66e-109">The integer whose bit-size is to be computed.</span></span>



## <a name="output--int"></a><span data-ttu-id="be66e-110">Wynik: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="be66e-110">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="be66e-111">Rozmiar bitowy `a` .</span><span class="sxs-lookup"><span data-stu-id="be66e-111">The bit-size of `a`.</span></span>