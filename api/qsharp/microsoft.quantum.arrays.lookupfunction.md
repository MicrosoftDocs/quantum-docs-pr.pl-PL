---
uid: Microsoft.Quantum.Arrays.LookupFunction
title: LookupFunction, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: LookupFunction
qsharp.summary: Given an array, returns a function which returns elements of that array.
ms.openlocfilehash: db20795719d11138cbdc5a38c0a19d0f247af059
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220777"
---
# <a name="lookupfunction-function"></a>LookupFunction, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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