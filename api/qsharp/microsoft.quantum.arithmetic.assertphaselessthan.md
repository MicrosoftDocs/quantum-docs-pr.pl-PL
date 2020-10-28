---
uid: Microsoft.Quantum.Arithmetic.AssertPhaseLessThan
title: AssertPhaseLessThan, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertPhaseLessThan
qsharp.summary: Asserts that the `number` encoded in PhaseLittleEndian is less than `value`.
ms.openlocfilehash: d003d83a84356ce52c5601135000813c7f119e4d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721377"
---
# <a name="assertphaselessthan-operation"></a>AssertPhaseLessThan, operacja

Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)

Package [](https://nuget.org/packages/)


Potwierdza, że `number` zakodowany w PhaseLittleEndian jest mniejszy niż `value` .

```qsharp
operation AssertPhaseLessThan (value : Int, number : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit
```


## <a name="input"></a>Dane wejściowe

### <a name="value--int"></a>wartość: [int](xref:microsoft.quantum.lang-ref.int)

`number` musi być mniejszy niż ten.


### <a name="number--phaselittleendian"></a>Liczba: [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)

Liczba całkowita bez znaku, która jest porównywana z `value` .



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Uwagi

Kontrolowana wersja tej operacji ignoruje kontrolki.