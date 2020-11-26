---
uid: Microsoft.Quantum.Canon.Angle
title: Funkcja Angle
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Angle
qsharp.summary: Returns 1, if `index` has an odd number of 1s and -1, if `index` has an even number of 1s.
ms.openlocfilehash: 1d8a9c2c19469e4949f043edd1ba91021fa42e78
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219417"
---
# <a name="angle-function"></a>Funkcja Angle

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Zwraca wartość 1, jeśli `index` ma nieparzystą liczbę wartości 1 i-1, jeśli `index` ma parzystą liczbę 1.

```qsharp
function Angle (index : Int) : Int
```


## <a name="description"></a>Opis

Wartość odpowiada znakowi współczynnika Rademacher-Walsh spektrum n-zmiennej i funkcji dla danego przypisania, które decyduje o kącie obrotu.

## <a name="input"></a>Dane wejściowe

### <a name="index--int"></a>indeks: [int](xref:microsoft.quantum.lang-ref.int)

Przypisanie wejściowe jako liczba całkowita (od 0 do 2 ^ n-1)



## <a name="output--int"></a>Wynik: [int](xref:microsoft.quantum.lang-ref.int)

