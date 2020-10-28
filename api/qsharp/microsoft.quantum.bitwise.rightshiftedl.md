---
uid: Microsoft.Quantum.Bitwise.RightShiftedL
title: RightShiftedL, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: RightShiftedL
qsharp.summary: Shifts the bitwise representation of a number right by a given number of bits.
ms.openlocfilehash: 2929ba58b636847257391930e1019769fd2c2580
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718572"
---
# <a name="rightshiftedl-function"></a>RightShiftedL, funkcja

Przestrzeń nazw: [Microsoft. Quantum. bitowe](xref:Microsoft.Quantum.Bitwise)

Package [](https://nuget.org/packages/)


Przenosi bitową reprezentację liczby bezpośrednio przez daną liczbę bitów.

```qsharp
function RightShiftedL (value : BigInt, amount : Int) : BigInt
```


## <a name="input"></a>Dane wejściowe

### <a name="value--bigint"></a>wartość: [bigint](xref:microsoft.quantum.lang-ref.bigint)

Liczba, której reprezentacja bitowa ma zostać przesunięta w prawo (mniej znaczące).


### <a name="amount--int"></a>kwota: [int](xref:microsoft.quantum.lang-ref.int)

Liczba bitów, przez którą ma `value` zostać przesunięta w prawo.



## <a name="output--bigint"></a>Dane wyjściowe: [bigint](xref:microsoft.quantum.lang-ref.bigint)

Wartość `value` , przesunięta w prawo przez `amount` bity.

## <a name="remarks"></a>Uwagi

Następujące elementy są równoważne:

```Q#
let c = a >>> b;
let c = RightShiftedL(a, b);
```