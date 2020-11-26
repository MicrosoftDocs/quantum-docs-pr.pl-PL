---
uid: Microsoft.Quantum.Logical.LexographicComparison
title: LexographicComparison, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LexographicComparison
qsharp.summary: Given a comparison function, returns a new function that lexographically compares two arrays.
ms.openlocfilehash: 4d8596c52b0fc8082a2b766d95d4052a4964b8b9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197588"
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