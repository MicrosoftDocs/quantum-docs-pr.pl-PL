---
uid: Microsoft.Quantum.Bitwise.RightShiftedL
title: RightShiftedL, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: RightShiftedL
qsharp.summary: Shifts the bitwise representation of a number right by a given number of bits.
ms.openlocfilehash: 03ed69c7151e62b91c4a036e301f99b45ce5ab62
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842094"
---
# <a name="rightshiftedl-function"></a>RightShiftedL, funkcja

Przestrzeń nazw: [Microsoft. Quantum. bitowe](xref:Microsoft.Quantum.Bitwise)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

```qsharp
let c = a >>> b;
let c = RightShiftedL(a, b);
```