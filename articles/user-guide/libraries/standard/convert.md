---
title: Konwersje typów w Q# bibliotekach standardowych
description: Poznaj typowe i zdefiniowane przez użytkownika funkcje konwersji typów w Q# bibliotekach standardowych.
author: cgranade
uid: microsoft.quantum.libraries.convert
ms.author: chgranad
ms.topic: conceptual
no-loc:
- Q#
- $$v
ms.openlocfilehash: 67f47339363a52097f342c8ae4e43a8a93d606a8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858021"
---
# <a name="type-conversions"></a>Konwersje typu #

Q# jest językiem o **jednoznacznie określonym typie** .
W szczególności nie Q# rzutuje niejawnie między różnymi typami. Na przykład `1 + 2.0` nie jest prawidłowym Q# wyrażeniem.
Zamiast tego Q# oferuje różne funkcje konwersji typów do konstruowania nowych wartości danego typu.

Na przykład <xref:Microsoft.Quantum.Core.Length> ma typ danych wyjściowych `Int` , więc jego dane wyjściowe muszą być najpierw konwertowane na, `Double` zanim będzie można go użyć jako części wyrażenia zmiennoprzecinkowego.
Można to zrobić za pomocą <xref:Microsoft.Quantum.Convert.IntAsDouble> funkcji:

```qsharp
open Microsoft.Quantum.Convert as Convert;

function HalfLength<'T>(arr : 'T[]) : Double {
    return Convert.IntAsDouble(Length(arr)) / 2.0;
}
```

<xref:Microsoft.Quantum.Convert>Przestrzeń nazw zawiera typowe funkcje konwersji typów do pracy z podstawowymi wbudowanymi typami, takimi jak `Int` ,,, `Double` `BigInt` `Result` i `Bool` :

```qsharp
let bool = Convert.ResultAsBool(One);        // true
let big = Convert.IntAsBigInt(271);          // 271L
let indices = Convert.RangeAsIntArray(0..4); // [0, 1, 2, 3, 4]
```

<xref:Microsoft.Quantum.Convert>Przestrzeń nazw udostępnia również kilka bardziej egzotycznych konwersji, takich jak `FunctionAsOperation` , które konwertują funkcje `'T -> 'U` na nowe operacje `'T => 'U` .

Na koniec Q# Biblioteka standardowa zawiera wiele typów zdefiniowanych przez użytkownika, takich jak <xref:Microsoft.Quantum.Math.Complex> i <xref:Microsoft.Quantum.Arithmetic.LittleEndian> .
Wraz z tymi typami Biblioteka standardowa udostępnia funkcje takie jak <xref:Microsoft.Quantum.Arithmetic.BigEndianAsLittleEndian> :

```qsharp
open Microsoft.Quantum.Arithmetic as Arithmetic;

let register = Arithmetic.BigEndian(qubits);
IncrementByInteger(Arithmetic.BigEndianAsLittleEndian(register));
```
