---
uid: Microsoft.Quantum.Arrays.IndexRange
title: IndexRange, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexRange
qsharp.summary: Given an array, returns a range over the indices of that array, suitable for use in a for loop.
ms.openlocfilehash: 5afd4cc260ac3e384d2736bf7b43d941afd9ef73
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220947"
---
# <a name="indexrange-function"></a>IndexRange, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Dana tablica zwraca zakres przez indeksy tej tablicy, odpowiedni do użycia w pętli for.

```qsharp
function IndexRange<'TElement> (array : 'TElement[]) : Range
```


## <a name="input"></a>Dane wejściowe

### <a name="array--telement"></a>Array: "TEle []

Tablica, dla której należy zwrócić zakres indeksów.



## <a name="output--range"></a>Dane wyjściowe: [zakres](xref:microsoft.quantum.lang-ref.range)

Zakres na wszystkie indeksy tablicy.

## <a name="type-parameters"></a>Parametry typu

### <a name="telement"></a>"TEle

Typ elementów tablicy.