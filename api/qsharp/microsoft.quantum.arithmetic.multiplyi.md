---
uid: Microsoft.Quantum.Arithmetic.MultiplyI
title: MultiplyI, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyI
qsharp.summary: Multiply integer `xs` by integer `ys` and store the result in `result`, which must be zero initially.
ms.openlocfilehash: 7b44f64fdddfd95f51683c2c3b2f4d37d0cf6841
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719760"
---
# <a name="multiplyi-operation"></a>MultiplyI, operacja

Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)

Package [](https://nuget.org/packages/)


Pomnóż liczbę całkowitą `xs` przez liczbę całkowitą `ys` i Zapisz wynik w `result` , który musi być początkowy od zera.

```qsharp
operation MultiplyI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a>Dane wejściowe

### <a name="xs--littleendian"></a>XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$n $-bit multiplicand (LittleEndian)


### <a name="ys--littleendian"></a>YS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

mnożnik $n $-bitowy (LittleEndian)


### <a name="result--littleendian"></a>wynik: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

wynik $2n $-bit (LittleEndian) musi być w stanie $ \ket {0} $.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Uwagi

Używa standardowego podejścia Shift-and-Add do implementowania mnożenia.
Kontrolowana wersja została ulepszona przez skopiowanie $x _i $ do Ancilla qubit warunku na qubits sterowania, a następnie kontrolowanie dodawania na Ancilla qubit.