---
uid: Microsoft.Quantum.Bitwise.LeftShiftedL
title: LeftShiftedL, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: LeftShiftedL
qsharp.summary: Shifts the bitwise representation of a number left by a given number of bits.
ms.openlocfilehash: 17e5c845755f74e9703381bc82bfd63be836d038
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718632"
---
# <a name="leftshiftedl-function"></a>LeftShiftedL, funkcja

Przestrzeń nazw: [Microsoft. Quantum. bitowe](xref:Microsoft.Quantum.Bitwise)

Package [](https://nuget.org/packages/)


Przenosi bitową reprezentację liczby pozostawionej przez daną liczbę bitów.

```qsharp
function LeftShiftedL (value : BigInt, amount : Int) : BigInt
```


## <a name="input"></a>Dane wejściowe

### <a name="value--bigint"></a>wartość: [bigint](xref:microsoft.quantum.lang-ref.bigint)

Liczba, której reprezentacja bitowa ma zostać przesunięta w lewo (bardziej znaczące).


### <a name="amount--int"></a>kwota: [int](xref:microsoft.quantum.lang-ref.int)

Liczba bitów, przez którą ma `value` zostać przesunięty w lewo.



## <a name="output--bigint"></a>Dane wyjściowe: [bigint](xref:microsoft.quantum.lang-ref.bigint)

Wartość `value` , przesunięta w lewo przez `amount` bity.

## <a name="remarks"></a>Uwagi

Następujące elementy są równoważne:

```Q#
let c = a <<< b;
let c = LeftShiftedL(a, b);
```