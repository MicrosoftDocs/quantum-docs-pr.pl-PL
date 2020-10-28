---
uid: Microsoft.Quantum.Arithmetic.MultiplyAndAddByModularInteger
title: MultiplyAndAddByModularInteger, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyAndAddByModularInteger
qsharp.summary: Performs a modular multiply-and-add by integer constants on a qubit register.
ms.openlocfilehash: 3f85f6aaea1d6f8095709c6f387322df7a5e047c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719808"
---
# <a name="multiplyandaddbymodularinteger-operation"></a>MultiplyAndAddByModularInteger, operacja

Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)

Package [](https://nuget.org/packages/)


Wykonuje modułowe mnożenie i Dodawanie przez stałe wartości całkowite w rejestrze qubit.

```qsharp
operation MultiplyAndAddByModularInteger (constMultiplier : Int, modulus : Int, multiplier : Microsoft.Quantum.Arithmetic.LittleEndian, summand : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a>Opis

Implementuje mapę $ $ \begin{align} \ket{x} \ket{b} \mapsto \ket{x} \ket{(b + a \cdot x) \operatorname{mod} N} \end{align} $ $ dla danego modułu $N $, mnożnik stałych $a $ i summand $y $.

## <a name="input"></a>Dane wejściowe

### <a name="constmultiplier--int"></a>constMultiplier: [int](xref:microsoft.quantum.lang-ref.int)

Liczba całkowita $a $ do dodania do każdej etykiety stanu podstawy.


### <a name="modulus--int"></a>Moduł: [int](xref:microsoft.quantum.lang-ref.int)

Moduł $N $, który Dodawanie i mnożenie jest wykonywane w odniesieniu do.


### <a name="multiplier--littleendian"></a>mnożnik: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Rejestr Quantum reprezentujący liczbę całkowitą bez znaku, którego wartość ma zostać dodana do każdej etykiety stanu podstawy `summand` .


### <a name="summand--littleendian"></a>summand: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Rejestr Quantum reprezentujący liczbę całkowitą bez znaku, który ma być używany jako element docelowy dla tej operacji.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Uwagi

- Aby zapoznać się ze schematem obwodu i wyjaśnieniem, zobacz rysunek 6 na [stronie 7 z ArXiv: Quant-pH/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=7)
- Ta operacja odpowiada CMULT (a) MOD (N) w [ArXiv: Quant-pH/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf)

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. arytmetyczne. MultiplyAndAddPhaseByModularInteger](xref:Microsoft.Quantum.Arithmetic.MultiplyAndAddPhaseByModularInteger)