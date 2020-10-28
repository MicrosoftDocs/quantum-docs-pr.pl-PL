---
uid: Microsoft.Quantum.Arrays.LookupFunction
title: LookupFunction, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: LookupFunction
qsharp.summary: Given an array, returns a function which returns elements of that array.
ms.openlocfilehash: c929054b96ee499db896cacf0e3ae4da6f6c4b98
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719073"
---
# <a name="lookupfunction-function"></a>LookupFunction, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Package [](https://nuget.org/packages/)


Dana tablica zwraca funkcję, która zwraca elementy tej tablicy.

```qsharp
function LookupFunction<'T> (array : 'T[]) : (Int -> 'T)
```


## <a name="input"></a>Dane wejściowe

### <a name="array--t"></a>Tablica: t []

Tablica, która ma być reprezentowana jako funkcja wyszukiwania.



## <a name="output--int---t"></a>Wynik: [int](xref:microsoft.quantum.lang-ref.int) -> 't

Funkcja `f` , która `f(idx) == f[idx]` .

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C

Typ elementów tablicy reprezentowanej jako funkcja wyszukiwania.

## <a name="remarks"></a>Uwagi

Ta funkcja jest głównie przydatna do współdziałania z funkcjami i operacjami, które przyjmują `Int -> 'T` funkcje jako argumenty. Jest to typowe, na przykład w bibliotece reprezentacji generatora, gdzie funkcje są używane, aby uniknąć konieczności rejestrowania całej tablicy w pamięci.