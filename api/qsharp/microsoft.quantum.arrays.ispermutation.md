---
uid: Microsoft.Quantum.Arrays.IsPermutation
title: Ispermutacja — funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IsPermutation
qsharp.summary: Outputs true if and only if a given array represents a permutation.
ms.openlocfilehash: 361bb21bedc725c25a1f3dfc811e9cfda4cb45ff
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719109"
---
# <a name="ispermutation-function"></a>Ispermutacja — funkcja

Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Package [](https://nuget.org/packages/)


Zwraca wartość PRAWDA, jeśli i tylko wtedy, gdy dana tablica reprezentuje permutację.

```qsharp
function IsPermutation (permuation : Int[]) : Bool
```


## <a name="description"></a>Opis

Dana tablica `array` o długości `n` zwraca wartość PRAWDA, jeśli i tylko wtedy, gdy każda liczba całkowita z `0` ma `n - 1` być wyświetlana dokładnie raz w `array` , na przykład, która `array` może być interpretowana jako Permutacja dla `n` elementów.

## <a name="input"></a>Dane wejściowe

### <a name="permuation--int"></a>permuation: [int](xref:microsoft.quantum.lang-ref.int)[]

Tablica, która może lub nie może reprezentować permutacji.



## <a name="output--bool"></a>Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)



## <a name="remarks"></a>Uwagi

Tablica o długości zero jest prosta permutacji.