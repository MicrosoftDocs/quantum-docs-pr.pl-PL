---
uid: Microsoft.Quantum.Bitwise.RightShiftedI
title: RightShiftedI, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: RightShiftedI
qsharp.summary: Shifts the bitwise representation of a number right by a given number of bits.
ms.openlocfilehash: b0ca7d3cb84c58429e9b3a29893a6140a717006b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718581"
---
# <a name="rightshiftedi-function"></a>RightShiftedI, funkcja

Przestrzeń nazw: [Microsoft. Quantum. bitowe](xref:Microsoft.Quantum.Bitwise)

Package [](https://nuget.org/packages/)


Przenosi bitową reprezentację liczby bezpośrednio przez daną liczbę bitów.

```qsharp
function RightShiftedI (value : Int, amount : Int) : Int
```


## <a name="input"></a>Dane wejściowe

### <a name="value--int"></a>wartość: [int](xref:microsoft.quantum.lang-ref.int)

Liczba, której reprezentacja bitowa ma zostać przesunięta w prawo (mniej znaczące).


### <a name="amount--int"></a>kwota: [int](xref:microsoft.quantum.lang-ref.int)

Liczba bitów, przez którą ma `value` zostać przesunięta w prawo.



## <a name="output--int"></a>Wynik: [int](xref:microsoft.quantum.lang-ref.int)

Wartość `value` , przesunięta w prawo przez `amount` bity.

## <a name="remarks"></a>Uwagi

Następujące elementy są równoważne:

```Q#
let c = a >>> b;
let c = RightShiftedI(a, b);
```