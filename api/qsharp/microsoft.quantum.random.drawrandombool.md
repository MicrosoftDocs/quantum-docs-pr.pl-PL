---
uid: Microsoft.Quantum.Random.DrawRandomBool
title: DrawRandomBool, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomBool
qsharp.summary: Given a success probability, returns a single Bernoulli trial that is true with the given probability.
ms.openlocfilehash: 7c13f8305756421b8d07baf22ff87764efac0418
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853687"
---
# <a name="drawrandombool-operation"></a>DrawRandomBool, operacja

Przestrzeń nazw: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


W wyniku prawdopodobieństwa sukcesu funkcja zwraca pojedynczą wersję próbną Bernoulliego, która ma wartość true z danym prawdopodobieństwem.

```qsharp
operation DrawRandomBool (successProbability : Double) : Bool
```


## <a name="input"></a>Dane wejściowe

### <a name="successprobability--double"></a>successProbability: [Double](xref:microsoft.quantum.lang-ref.double)

Prawdopodobieństwo, z którym `true` należy zwrócić.



## <a name="output--bool"></a>Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` z prawdopodobieństwem `successProbability` i `false` z prawdopodobieństwem `1.0 - successProbability` .

## <a name="example"></a>Przykład

Następujące przykłady fragmentów kodu Q # są przerzucane z zastosowanej monety:

```qsharp
let flips = DrawMany(DrawRandomBool, 10, 0.6);
```