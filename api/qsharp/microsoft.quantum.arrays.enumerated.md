---
uid: Microsoft.Quantum.Arrays.Enumerated
title: Funkcja wyliczana
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Enumerated
qsharp.summary: Given an array, returns a new array containing elements of the original array along with the indices of each element.
ms.openlocfilehash: 0a591025a4eef79e08b47527c0bdb556f5645334
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719304"
---
# <a name="enumerated-function"></a>Funkcja wyliczana

Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Package [](https://nuget.org/packages/)


Dana tablica zwraca nową tablicę zawierającą elementy oryginalnej tablicy wraz z indeksami każdego elementu.

```qsharp
function Enumerated<'TElement> (array : 'TElement[]) : (Int, 'TElement)[]
```


## <a name="input"></a>Dane wejściowe

### <a name="array--telement"></a>Array: "TEle []

Tablica, której elementy mają zostać wyliczone.



## <a name="output--inttelement"></a>Wynik: ([int](xref:microsoft.quantum.lang-ref.int), "tele") []

Nowa tablica zawierająca elementy oryginalnej tablicy wraz z ich indeksami.

## <a name="type-parameters"></a>Parametry typu

### <a name="telement"></a>"TEle

Typ elementów tablicy.