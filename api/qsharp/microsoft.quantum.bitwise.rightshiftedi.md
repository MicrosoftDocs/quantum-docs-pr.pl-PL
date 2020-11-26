---
uid: Microsoft.Quantum.Bitwise.RightShiftedI
title: RightShiftedI, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: RightShiftedI
qsharp.summary: Shifts the bitwise representation of a number right by a given number of bits.
ms.openlocfilehash: b20a4a8c281a470af9a4828f8a5ca905a7918723
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209778"
---
# <a name="rightshiftedi-function"></a>RightShiftedI, funkcja

Przestrzeń nazw: [Microsoft. Quantum. bitowe](xref:Microsoft.Quantum.Bitwise)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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