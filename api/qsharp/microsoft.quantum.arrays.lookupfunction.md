---
uid: Microsoft.Quantum.Arrays.LookupFunction
title: LookupFunction, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: LookupFunction
qsharp.summary: Given an array, returns a function which returns elements of that array.
ms.openlocfilehash: 22b56bb7e9f03ebc5b2225efb2e6450d56022664
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845696"
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