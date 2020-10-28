---
uid: Microsoft.Quantum.Math.BitSizeI
title: BitSizeI, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BitSizeI
qsharp.summary: >-
  For a non-negative integer `a`, returns the number of bits required to represent `a`.

  That is, returns the smallest $n$ such that $a < 2^n$.
ms.openlocfilehash: e7cfe03908a8a394fc8ceb1c9facbf02f3db2d48
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723197"
---
# <a name="bitsizei-function"></a><span data-ttu-id="21801-102">BitSizeI, funkcja</span><span class="sxs-lookup"><span data-stu-id="21801-102">BitSizeI function</span></span>

<span data-ttu-id="21801-103">Przestrzeń nazw: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="21801-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="21801-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="21801-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="21801-105">Dla nieujemnej liczby całkowitej `a` zwraca liczbę bitów wymaganych do reprezentowania `a` .</span><span class="sxs-lookup"><span data-stu-id="21801-105">For a non-negative integer `a`, returns the number of bits required to represent `a`.</span></span>

<span data-ttu-id="21801-106">Oznacza to, że program zwraca najmniejszy $n $, który $a < 2 ^ n $.</span><span class="sxs-lookup"><span data-stu-id="21801-106">That is, returns the smallest $n$ such that $a < 2^n$.</span></span>

```qsharp
function BitSizeI (a : Int) : Int
```


## <a name="input"></a><span data-ttu-id="21801-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="21801-107">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="21801-108">Odp.: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="21801-108">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="21801-109">Liczba całkowita, której rozmiar bitowy ma zostać obliczony.</span><span class="sxs-lookup"><span data-stu-id="21801-109">The integer whose bit-size is to be computed.</span></span>



## <a name="output--int"></a><span data-ttu-id="21801-110">Wynik: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="21801-110">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="21801-111">Rozmiar bitowy `a` .</span><span class="sxs-lookup"><span data-stu-id="21801-111">The bit-size of `a`.</span></span>