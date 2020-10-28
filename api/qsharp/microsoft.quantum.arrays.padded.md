---
uid: Microsoft.Quantum.Arrays.Padded
title: Funkcja uzupełniona
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Padded
qsharp.summary: Returns an array padded at with specified values up to a specified length.
ms.openlocfilehash: 8742d4726e7ee32349bf3d0bd5077352ffca350b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718980"
---
# <a name="padded-function"></a>Funkcja uzupełniona

Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Package [](https://nuget.org/packages/)


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