---
uid: Microsoft.Quantum.Math.BitSizeL
title: BitSizeL, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BitSizeL
qsharp.summary: >-
  For a non-negative integer `a`, returns the number of bits required to represent `a`.

  That is, returns the smallest $n$ such that $a < 2^n$.
ms.openlocfilehash: 8b3d4cceb69619ed32977337fc0fe7401db38cbd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211053"
---
# <a name="bitsizel-function"></a>BitSizeL, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dla nieujemnej liczby całkowitej `a` zwraca liczbę bitów wymaganych do reprezentowania `a` .

Oznacza to, że program zwraca najmniejszy $n $, który $a < 2 ^ n $.

```qsharp
function BitSizeL (a : BigInt) : Int
```


## <a name="input"></a>Dane wejściowe

### <a name="a--bigint"></a>Odp.: [bigint](xref:microsoft.quantum.lang-ref.bigint)

Liczba całkowita, której rozmiar bitowy ma zostać obliczony.



## <a name="output--int"></a>Wynik: [int](xref:microsoft.quantum.lang-ref.int)

Rozmiar bitowy `a` .