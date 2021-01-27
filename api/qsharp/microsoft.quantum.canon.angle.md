---
uid: Microsoft.Quantum.Canon.Angle
title: Funkcja Angle
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Angle
qsharp.summary: Returns 1, if `index` has an odd number of 1s and -1, if `index` has an even number of 1s.
ms.openlocfilehash: 0528f21b2d9c98b6497e28741964e6497d4d0fb9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842053"
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

