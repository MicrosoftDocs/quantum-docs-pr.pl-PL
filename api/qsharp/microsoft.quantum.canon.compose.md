---
uid: Microsoft.Quantum.Canon.Compose
title: Funkcja redagowania
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Compose
qsharp.summary: Returns the composition of two functions.
ms.openlocfilehash: f8c6ad36220b48be1723c2d91cbf7c0a4947af14
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216765"
---
# <a name="compose-function"></a>Funkcja redagowania

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Zwraca składową dwóch funkcji.

```qsharp
function Compose<'T, 'U, 'V> (outer : ('U -> 'V), inner : ('T -> 'U)) : ('T -> 'V)
```


## <a name="description"></a>Opis

Podaną dwie funkcje $f $ i $g $, zwracają nową funkcję reprezentującą $f \circ g $.

## <a name="input"></a>Dane wejściowe

### <a name="outer--u---v"></a>zewnętrzne: "U->" V

Druga funkcja, która ma zostać zastosowana.


### <a name="inner--t---u"></a>wewnętrzny: brak > ' U

Pierwsza funkcja, która ma zostać zastosowana.



## <a name="output--t---v"></a>Dane wyjściowe: 'R-> ' V

Nowa funkcja $h $, która dla wszystkich wejść $x $, $f (g (x)) = h (x) $.

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C

Typ wejścia pierwszej funkcji, która ma zostać zastosowana.
### <a name="u"></a>' U

Typ wyjściowy pierwszej funkcji, która ma zostać zastosowana i typ wejściowy drugiej funkcji, która ma zostać zastosowana.
### <a name="v"></a>"V

Typ wyjściowy drugiej funkcji, która ma zostać zastosowana.