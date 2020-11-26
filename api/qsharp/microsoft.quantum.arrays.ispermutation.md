---
uid: Microsoft.Quantum.Arrays.IsPermutation
title: Ispermutacja — funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IsPermutation
qsharp.summary: Outputs true if and only if a given array represents a permutation.
ms.openlocfilehash: 144f683818b5d75de5b075328365d3e994de29d1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220930"
---
# <a name="ispermutation-function"></a>Ispermutacja — funkcja

Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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