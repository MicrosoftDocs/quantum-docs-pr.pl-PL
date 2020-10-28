---
uid: Microsoft.Quantum.Arrays.IndexRange
title: IndexRange, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexRange
qsharp.summary: Given an array, returns a range over the indices of that array, suitable for use in a for loop.
ms.openlocfilehash: 7f9779acd4a781c50388217aa780710bd0b99ff3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719148"
---
# <a name="indexrange-function"></a>IndexRange, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Package [](https://nuget.org/packages/)


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