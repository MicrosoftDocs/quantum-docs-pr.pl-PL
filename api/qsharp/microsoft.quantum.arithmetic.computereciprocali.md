---
uid: Microsoft.Quantum.Arithmetic.ComputeReciprocalI
title: ComputeReciprocalI, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ComputeReciprocalI
qsharp.summary: Computes the reciprocal 1/x for an unsigned integer x using integer division. The result, interpreted as an integer, will be `floor(2^(2*n-1) / x)`.
ms.openlocfilehash: b99e816ed69af6e6d1758442d6f95c5ab0e5c07a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721224"
---
# <a name="computereciprocali-operation"></a>ComputeReciprocalI, operacja

Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)

Package [](https://nuget.org/packages/)


Oblicza odwrotność 1/x dla nieoznaczonej liczby całkowitej x przy użyciu dzielenia liczb całkowitych. Wynikiem jest interpretowana jako liczba całkowita `floor(2^(2*n-1) / x)` .

```qsharp
operation ComputeReciprocalI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a>Dane wejściowe

### <a name="xs--littleendian"></a>XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

n-bitowa liczba całkowita bez znaku


### <a name="result--littleendian"></a>wynik: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

2n-bitowe dane wyjściowe muszą znajdować się w $ \ket {0} $.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Uwagi

Dla danych wejściowych x = 0, dane wyjściowe będą wszystkie.