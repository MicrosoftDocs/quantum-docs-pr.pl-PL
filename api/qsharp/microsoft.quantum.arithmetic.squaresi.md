---
uid: Microsoft.Quantum.Arithmetic.SquareSI
title: SquareSI, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: SquareSI
qsharp.summary: Square signed integer `xs` and store the result in `result`, which must be zero initially.
ms.openlocfilehash: c8c4e3cca001aa6d7ce1b9df106ce77f74524301
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719532"
---
# <a name="squaresi-operation"></a>SquareSI, operacja

Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)

Package [](https://nuget.org/packages/)


Kwadratowa liczba całkowita ze znakiem `xs` i przechowywanie wyniku `result` , który musi być początkowy od zera.

```qsharp
operation SquareSI (xs : Microsoft.Quantum.Arithmetic.SignedLittleEndian, result : Microsoft.Quantum.Arithmetic.SignedLittleEndian) : Unit
```


## <a name="input"></a>Dane wejściowe

### <a name="xs--signedlittleendian"></a>XS: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)

n-bitowa liczba całkowita do kwadratu (SignedLittleEndian)


### <a name="result--signedlittleendian"></a>wynik: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)

wynik 2n-bitowy (SignedLittleEndian) musi być w stanie $ \ket {0} $.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Uwagi

Implementacja opiera się na IntegerSquare.