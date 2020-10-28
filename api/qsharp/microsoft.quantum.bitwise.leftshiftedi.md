---
uid: Microsoft.Quantum.Bitwise.LeftShiftedI
title: LeftShiftedI, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: LeftShiftedI
qsharp.summary: Shifts the bitwise representation of a number left by a given number of bits.
ms.openlocfilehash: ce68311adf211169c2fb499bb189332370a6d6ac
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718665"
---
# <a name="leftshiftedi-function"></a>LeftShiftedI, funkcja

Przestrzeń nazw: [Microsoft. Quantum. bitowe](xref:Microsoft.Quantum.Bitwise)

Package [](https://nuget.org/packages/)


Przenosi bitową reprezentację liczby pozostawionej przez daną liczbę bitów.

```qsharp
function LeftShiftedI (value : Int, amount : Int) : Int
```


## <a name="input"></a>Dane wejściowe

### <a name="value--int"></a>wartość: [int](xref:microsoft.quantum.lang-ref.int)

Liczba, której reprezentacja bitowa ma zostać przesunięta w lewo (bardziej znaczące).


### <a name="amount--int"></a>kwota: [int](xref:microsoft.quantum.lang-ref.int)

Liczba bitów, przez którą ma `value` zostać przesunięty w lewo.



## <a name="output--int"></a>Wynik: [int](xref:microsoft.quantum.lang-ref.int)

Wartość `value` , przesunięta w lewo przez `amount` bity.

## <a name="remarks"></a>Uwagi

Następujące elementy są równoważne:

```Q#
let c = a <<< b;
let c = LeftShiftedI(a, b);
```