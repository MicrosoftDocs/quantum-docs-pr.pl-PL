---
uid: Microsoft.Quantum.Arrays.IndexRange
title: IndexRange, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexRange
qsharp.summary: Given an array, returns a range over the indices of that array, suitable for use in a for loop.
ms.openlocfilehash: 043b56a1ac3cbe5cd59cdd45d3725f301d81a6ee
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845778"
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

## <a name="example"></a>Przykład

Następujące `for` pętle są równoważne:

```qsharp
for (idx in IndexRange(array)) { ... }
for (idx in IndexRange(array)) { ... }
```