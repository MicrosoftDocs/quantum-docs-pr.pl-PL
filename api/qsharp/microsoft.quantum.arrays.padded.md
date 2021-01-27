---
uid: Microsoft.Quantum.Arrays.Padded
title: Funkcja uzupełniona
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Padded
qsharp.summary: Returns an array padded at with specified values up to a specified length.
ms.openlocfilehash: 556e5f5175ee54470a99f32c037eeb2cd80588d0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845559"
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

## <a name="example"></a>Przykład

```qsharp
let array = [10, 11, 12];
// The following line returns [10, 12, 15, 2, 2, 2].
let output = Padded(-6, array, 2);
// The following line returns [2, 2, 2, 10, 12, 15].
let output = Padded(6, array, 2);
```