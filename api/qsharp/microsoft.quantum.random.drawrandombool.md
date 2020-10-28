---
uid: Microsoft.Quantum.Random.DrawRandomBool
title: DrawRandomBool, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomBool
qsharp.summary: Given a success probability, returns a single Bernoulli trial that is true with the given probability.
ms.openlocfilehash: 05cf8ad939691aac90625c5d056ea79aa062f553
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720276"
---
# <a name="drawrandombool-operation"></a>DrawRandomBool, operacja

Przestrzeń nazw: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

Package [](https://nuget.org/packages/)


W wyniku prawdopodobieństwa sukcesu funkcja zwraca pojedynczą wersję próbną Bernoulliego, która ma wartość true z danym prawdopodobieństwem.

```qsharp
operation DrawRandomBool (successProbability : Double) : Bool
```


## <a name="input"></a>Dane wejściowe

### <a name="successprobability--double"></a>successProbability: [Double](xref:microsoft.quantum.lang-ref.double)

Prawdopodobieństwo, z którym `true` należy zwrócić.



## <a name="output--bool"></a>Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` z prawdopodobieństwem `successProbability` i `false` z prawdopodobieństwem `1.0 - successProbability` .