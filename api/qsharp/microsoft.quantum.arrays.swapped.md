---
uid: Microsoft.Quantum.Arrays.Swapped
title: Zamieniono funkcję
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Swapped
qsharp.summary: Applies a swap of two elements in an array.
ms.openlocfilehash: 575d6b76e52f198d91ab5557ada8032df491cfa3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850949"
---
# <a name="swapped-function"></a>Zamieniono funkcję

Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Stosuje wymianę dwóch elementów w tablicy.

```qsharp
function Swapped<'T> (firstIndex : Int, secondIndex : Int, arr : 'T[]) : 'T[]
```


## <a name="input"></a>Dane wejściowe

### <a name="firstindex--int"></a>firstIndex: [int](xref:microsoft.quantum.lang-ref.int)

Indeks pierwszego elementu, który ma zostać zamieniony.


### <a name="secondindex--int"></a>secondIndex: [int](xref:microsoft.quantum.lang-ref.int)

Indeks drugiego elementu, który ma zostać zamieniony.


### <a name="arr--t"></a>ARR: t []

Tablica z elementami, które mają zostać zamienione.



## <a name="output--t"></a>Wynik: t []

Tablica z zastosowanym zamianą w miejscu.

## <a name="example"></a>Przykład

```qsharp
// The following returns [0, 3, 2, 1, 4]
Swapped(1, 3, [0, 1, 2, 3, 4]);
```

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C

