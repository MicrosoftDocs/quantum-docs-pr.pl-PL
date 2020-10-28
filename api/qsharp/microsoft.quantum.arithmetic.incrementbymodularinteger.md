---
uid: Microsoft.Quantum.Arithmetic.IncrementByModularInteger
title: IncrementByModularInteger, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementByModularInteger
qsharp.summary: Performs a modular increment of a qubit register by an integer constant.
ms.openlocfilehash: 271033b32b0de6cf600dca82126dab19c2bb4f5d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721101"
---
# <a name="incrementbymodularinteger-operation"></a>IncrementByModularInteger, operacja

Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)

Package [](https://nuget.org/packages/)


Wykonuje modularny przyrost qubit rejestru przez stałą całkowitą.

```qsharp
operation IncrementByModularInteger (increment : Int, modulus : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a>Opis

Poinformuj nas `increment` o $a $, `modulus` przez $N $ i Integer zakodowane w `target` $y $.
Następnie operacja wykonuje następujące przekształcenia: \begin{align} \ket{y} \mapsto \ket{(y + a) \operatorname{mod} N} \end{align} INTEGERS są kodowane w formacie little-endian.

## <a name="input"></a>Dane wejściowe

### <a name="increment--int"></a>Zwiększ: [int](xref:microsoft.quantum.lang-ref.int)

Przyrost liczby całkowitej $a $, który ma zostać dodany do $y $.


### <a name="modulus--int"></a>Moduł: [int](xref:microsoft.quantum.lang-ref.int)

Liczba całkowita $N $, która modyfikacje $y + a $.


### <a name="target--littleendian"></a>obiekt docelowy: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Liczba całkowita $y $ w `LittleEndian` formacie, który `increment` $a $ jest dodawany do.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Uwagi

Przyjęto, że początkowa wartość docelowa jest mniejsza niż $N $ i że przyrost $a $ jest mniejszy niż $N $.
Należy pamiętać, że <xref:microsoft.quantum.arithmetic.incrementphasebymodularinteger> implementuje tę samą operację na `PhaseLittleEndian` podstawie.

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. arytmetyczne. IncrementPhaseByModularInteger](xref:Microsoft.Quantum.Arithmetic.IncrementPhaseByModularInteger)