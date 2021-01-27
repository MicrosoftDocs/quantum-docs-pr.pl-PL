---
uid: Microsoft.Quantum.Bitwise.RightShiftedI
title: RightShiftedI, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: RightShiftedI
qsharp.summary: Shifts the bitwise representation of a number right by a given number of bits.
ms.openlocfilehash: 5c3106eb73178554184cbfb37333c027805c69f3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845254"
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

```qsharp
let c = a >>> b;
let c = RightShiftedI(a, b);
```