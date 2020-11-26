---
uid: Microsoft.Quantum.Arithmetic.MultiplySI
title: MultiplySI, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplySI
qsharp.summary: Multiply signed integer `xs` by signed integer `ys` and store the result in `result`, which must be zero initially.
ms.openlocfilehash: 4e7f43f88654f10ece4f9c30c5bfde9a779b18ba
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222443"
---
# <a name="multiplysi-operation"></a>MultiplySI, operacja

Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)

Pakiet: [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)


Pomnóż liczbę całkowitą ze znakiem, `xs` która została ze znakiem liczb całkowitych `ys` i Zapisz wynik w `result` , który musi być początkowy od zera.

```qsharp
operation MultiplySI (xs : Microsoft.Quantum.Arithmetic.SignedLittleEndian, ys : Microsoft.Quantum.Arithmetic.SignedLittleEndian, result : Microsoft.Quantum.Arithmetic.SignedLittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>Dane wejściowe

### <a name="xs--signedlittleendian"></a>XS: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)

n-bitowy multiplicand (SignedLittleEndian)


### <a name="ys--signedlittleendian"></a>YS: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)

mnożnik n-bitowy (SignedLittleEndian)


### <a name="result--signedlittleendian"></a>wynik: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)

wynik 2n-bitowy (SignedLittleEndian) musi być w stanie $ \ket {0} $.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)

