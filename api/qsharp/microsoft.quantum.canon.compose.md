---
uid: Microsoft.Quantum.Canon.Compose
title: Funkcja redagowania
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Compose
qsharp.summary: Returns the composition of two functions.
ms.openlocfilehash: 73eab66e2e9a9af56d01db927eb7af38bb56a23e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840904"
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