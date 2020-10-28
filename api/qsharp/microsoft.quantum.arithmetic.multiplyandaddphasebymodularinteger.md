---
uid: Microsoft.Quantum.Arithmetic.MultiplyAndAddPhaseByModularInteger
title: MultiplyAndAddPhaseByModularInteger, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyAndAddPhaseByModularInteger
qsharp.summary: The same as MultiplyAndAddByModularInteger, but assumes that the summand encodes integers in QFT basis.
ms.openlocfilehash: be7df50f040697329c2fe8bbc319c8cebb8b2687
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719805"
---
# <a name="multiplyandaddphasebymodularinteger-operation"></a>MultiplyAndAddPhaseByModularInteger, operacja

Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)

Package [](https://nuget.org/packages/)


Taka sama jak MultiplyAndAddByModularInteger, ale zakłada, że summand koduje liczby całkowite na bazie QFT.

```qsharp
operation MultiplyAndAddPhaseByModularInteger (constMultiplier : Int, modulus : Int, multiplier : Microsoft.Quantum.Arithmetic.LittleEndian, phaseSummand : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit
```


## <a name="input"></a>Dane wejściowe

### <a name="constmultiplier--int"></a>constMultiplier: [int](xref:microsoft.quantum.lang-ref.int)

Liczba całkowita $a $ do dodania do każdej etykiety stanu podstawy.


### <a name="modulus--int"></a>Moduł: [int](xref:microsoft.quantum.lang-ref.int)

Moduł $N $, który Dodawanie i mnożenie jest wykonywane w odniesieniu do.


### <a name="multiplier--littleendian"></a>mnożnik: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Rejestr Quantum reprezentujący liczbę całkowitą bez znaku, którego wartość ma zostać dodana do każdej etykiety stanu podstawy `summand` .


### <a name="phasesummand--phaselittleendian"></a>phaseSummand: [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)

Rejestr Quantum reprezentujący liczbę całkowitą bez znaku, który ma być używany jako element docelowy dla tej operacji.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Uwagi

Zakłada, że `phaseSummand` najwyższy bit ma ustawioną wartość 0.
Zakłada również, że wartość `phaseSummand` jest mniejsza niż $N $.

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. arytmetyczne. MultiplyAndAddByModularInteger](xref:Microsoft.Quantum.Arithmetic.MultiplyAndAddByModularInteger)