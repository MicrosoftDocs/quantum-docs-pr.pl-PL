---
uid: Microsoft.Quantum.Canon.Compose
title: Funkcja redagowania
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Compose
qsharp.summary: Returns the composition of two functions.
ms.openlocfilehash: 02cff7eef4d55d27d5d72e6219a90b7d8f5beb3b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716492"
---
# <a name="compose-function"></a>Funkcja redagowania

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package [](https://nuget.org/packages/)


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