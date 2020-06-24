---
title: Konwersje typów w bibliotekach standardowych Q
description: 'Poznaj typowe i zdefiniowane przez użytkownika funkcje konwersji typów w bibliotekach Q # Standard.'
author: cgranade
uid: microsoft.quantum.libraries.convert
ms.author: chgranad@microsoft.com
ms.topic: article
ms.openlocfilehash: e941d7e3d76459546861410e91a03d7315183867
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275738"
---
# <a name="type-conversions"></a>Konwersje typu #

Q # to język o **jednoznacznie określonym typie** .
W szczególności polecenie Q # nie niejawnie rzutuje między różnymi typami. Na przykład `1 + 2.0` nie jest prawidłowym wyrażeniem Q #.
Zamiast tego funkcja Q # zapewnia różnorodne funkcje konwersji typów do konstruowania nowych wartości danego typu.

Na przykład <xref:microsoft.quantum.core.length> ma typ danych wyjściowych `Int` , więc jego dane wyjściowe muszą być najpierw konwertowane na, `Double` zanim będzie można go użyć jako części wyrażenia zmiennoprzecinkowego.
Można to zrobić za pomocą <xref:microsoft.quantum.convert.intasdouble> funkcji:

```qsharp
open Microsoft.Quantum.Convert as Convert;

function HalfLength<'T>(arr : 'T[]) : Double {
    return Convert.IntAsDouble(Length(arr)) / 2.0;
}
```

<xref:microsoft.quantum.convert>Przestrzeń nazw zawiera typowe funkcje konwersji typów do pracy z podstawowymi wbudowanymi typami, takimi jak `Int` ,,, `Double` `BigInt` `Result` i `Bool` :

```qsharp
let bool = Convert.ResultAsBool(One);        // true
let big = Convert.IntAsBigInt(271);          // 271L
let indices = Convert.RangeAsIntArray(0..4); // [0, 1, 2, 3, 4]
```

<xref:microsoft.quantum.convert>Przestrzeń nazw udostępnia również kilka bardziej egzotycznych konwersji, takich jak `FunctionAsOperation` , które konwertują funkcje `'T -> 'U` na nowe operacje `'T => 'U` .

Na koniec standardowa biblioteka Q # zawiera wiele typów zdefiniowanych przez użytkownika, takich jak <xref:microsoft.quantum.math.complex> i <xref:microsoft.quantum.arithmetic.littleendian> .
Wraz z tymi typami Biblioteka standardowa udostępnia funkcje takie jak <xref:microsoft.quantum.arithmetic.bigendianaslittleendian> :

```Q#
open Microsoft.Quantum.Arithmetic as Arithmetic;

let register = Arithmetic.BigEndian(qubits);
IncrementByInteger(Arithmetic.BigEndianAsLittleEndian(register));
```
