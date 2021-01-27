---
uid: Microsoft.Quantum.Logical.LexographicComparison
title: LexographicComparison, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LexographicComparison
qsharp.summary: Given a comparison function, returns a new function that lexographically compares two arrays.
ms.openlocfilehash: de8179ab6e835d08e7f41287f31a876b7ecc91c5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98814378"
---
# <a name="lexographiccomparison-function"></a>LexographicComparison, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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