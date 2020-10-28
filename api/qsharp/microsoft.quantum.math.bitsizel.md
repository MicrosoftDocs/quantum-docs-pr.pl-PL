---
uid: Microsoft.Quantum.Math.BitSizeL
title: BitSizeL, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BitSizeL
qsharp.summary: >-
  For a non-negative integer `a`, returns the number of bits required to represent `a`.

  That is, returns the smallest $n$ such that $a < 2^n$.
ms.openlocfilehash: 97068f12050317a9aa17c95f33650ef6f406066d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723188"
---
# <a name="bitsizel-function"></a><span data-ttu-id="5b2dd-102">BitSizeL, funkcja</span><span class="sxs-lookup"><span data-stu-id="5b2dd-102">BitSizeL function</span></span>

<span data-ttu-id="5b2dd-103">Przestrzeń nazw: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="5b2dd-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="5b2dd-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5b2dd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5b2dd-105">Dla nieujemnej liczby całkowitej `a` zwraca liczbę bitów wymaganych do reprezentowania `a` .</span><span class="sxs-lookup"><span data-stu-id="5b2dd-105">For a non-negative integer `a`, returns the number of bits required to represent `a`.</span></span>

<span data-ttu-id="5b2dd-106">Oznacza to, że program zwraca najmniejszy $n $, który $a < 2 ^ n $.</span><span class="sxs-lookup"><span data-stu-id="5b2dd-106">That is, returns the smallest $n$ such that $a < 2^n$.</span></span>

```qsharp
function BitSizeL (a : BigInt) : Int
```


## <a name="input"></a><span data-ttu-id="5b2dd-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="5b2dd-107">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="5b2dd-108">Odp.: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="5b2dd-108">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="5b2dd-109">Liczba całkowita, której rozmiar bitowy ma zostać obliczony.</span><span class="sxs-lookup"><span data-stu-id="5b2dd-109">The integer whose bit-size is to be computed.</span></span>



## <a name="output--int"></a><span data-ttu-id="5b2dd-110">Wynik: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5b2dd-110">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5b2dd-111">Rozmiar bitowy `a` .</span><span class="sxs-lookup"><span data-stu-id="5b2dd-111">The bit-size of `a`.</span></span>