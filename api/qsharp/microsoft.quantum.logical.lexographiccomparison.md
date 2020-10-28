---
uid: Microsoft.Quantum.Logical.LexographicComparison
title: LexographicComparison, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LexographicComparison
qsharp.summary: Given a comparison function, returns a new function that lexographically compares two arrays.
ms.openlocfilehash: f0b68974a0ea26907b58971e4fa4b1f06f5714d2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709907"
---
# <a name="lexographiccomparison-function"></a>LexographicComparison, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

Package [](https://nuget.org/packages/)


Dana funkcja porównywania zwraca nową funkcję, która lexographically porównuje dwie tablice.

```qsharp
function LexographicComparison<'T> (elementComparison : (('T, 'T) -> Bool)) : (('T[], 'T[]) -> Bool)
```


## <a name="input"></a>Dane wejściowe

### <a name="elementcomparison--tt---bool"></a>elementComparison: (t, t)-> [bool](xref:microsoft.quantum.lang-ref.bool)

Funkcja, która porównuje dwa elementy `x` i `y` zwraca wartość, jeśli `x` jest mniejsza lub równa `y` .



## <a name="output--tt---bool"></a>Output: (t [], t [])-> [bool](xref:microsoft.quantum.lang-ref.bool)

Funkcja, która porównuje dwie tablice `xs` i `ys` zwraca, jeśli `xs` występuje przed lub `ys` w kolejności lexographical.

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C

Typ elementów porównywanych tablic.

## <a name="remarks"></a>Uwagi

Porównanie lexographic między dwiema tablicami `xs` i `ys` jest zdefiniowane przez poniższą procedurę. Załóżmy, że dwa elementy `x` i `y` są równoważne, jeśli `elementComparison(x, y)` i `elementComparison(y, x)` są spełnione.

- Obie tablice są porównywane element po elemencie do momentu pierwszej pary elementów, które nie są równoważne. Tablica zawierająca element, który występuje po raz pierwszy zgodnie z, `elementComparison` jest określana jako pierwsza w kolejności lexographical.
- Jeśli nie zostaną znalezione żadne nierównoważne elementy, a jedna tablica jest dłuższa niż pozostałe, to krótsza tablica jest określana jako pierwsza.

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. Arrays. posortowane](xref:Microsoft.Quantum.Arrays.Sorted)