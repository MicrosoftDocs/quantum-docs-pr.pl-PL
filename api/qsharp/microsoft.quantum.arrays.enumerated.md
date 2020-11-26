---
uid: Microsoft.Quantum.Arrays.Enumerated
title: Funkcja wyliczana
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Enumerated
qsharp.summary: Given an array, returns a new array containing elements of the original array along with the indices of each element.
ms.openlocfilehash: 94e8fdb7288bc43ed84d10a3292819b455a2be31
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221423"
---
# <a name="enumerated-function"></a>Funkcja wyliczana

Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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