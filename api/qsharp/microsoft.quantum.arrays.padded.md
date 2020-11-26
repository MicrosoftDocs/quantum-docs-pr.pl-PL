---
uid: Microsoft.Quantum.Arrays.Padded
title: Funkcja uzupełniona
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Padded
qsharp.summary: Returns an array padded at with specified values up to a specified length.
ms.openlocfilehash: 2b7a80d1cf5c82a1ff52bc4aa207cfe335b40061
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220539"
---
# <a name="padded-function"></a>Funkcja uzupełniona

Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Zwraca tablicę uzupełnioną o określone wartości do określonej długości.

```qsharp
function Padded<'T> (nElementsTotal : Int, defaultElement : 'T, inputArray : 'T[]) : 'T[]
```


## <a name="input"></a>Dane wejściowe

### <a name="nelementstotal--int"></a>nElementsTotal: [int](xref:microsoft.quantum.lang-ref.int)

Długość zapełnionej tablicy. Jeśli jest to pozytywne, `inputArray` dopełniane na końcu. Jeśli jest to wartość ujemna, `inputArray` zostanie uzupełniona na ogon.


### <a name="defaultelement--t"></a>defaultelement: 'T

Wartość domyślna służąca do uzupełniania elementów.


### <a name="inputarray--t"></a>inputArray: t []

Tablica, której wartości znajdują się na początku tablicy wyjściowej.



## <a name="output--t"></a>Wynik: t []

Tablica `output` , która jest `inputArray` uzupełniona względem elementu `defaultElement` s do `output` długości `nElementsTotal`

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C

Typ elementów tablicy.