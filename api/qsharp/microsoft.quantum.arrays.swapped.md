---
uid: Microsoft.Quantum.Arrays.Swapped
title: Zamieniono funkcję
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Swapped
qsharp.summary: Applies a swap of two elements in an array.
ms.openlocfilehash: fa5b37b4caf5d8f19ed05075ddd7bc4217036bfb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718824"
---
# <a name="swapped-function"></a>Zamieniono funkcję

Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Package [](https://nuget.org/packages/)


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

