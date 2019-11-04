---
title: 'Biblioteki Q # standardowe — konwersje typów | Microsoft Docs'
description: 'Biblioteki Q # standardowe — konwersje typów'
author: cgranade
uid: microsoft.quantum.libraries.convert
ms.author: chgranad@microsoft.com
ms.topic: article
ms.openlocfilehash: 4716f0d9562229f08ef6f0f5f80961f793de4c5c
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2019
ms.locfileid: "73184478"
---
# <a name="type-conversions"></a>Konwersje typów #

Q # to język o **jednoznacznie określonym typie** .
W szczególności polecenie Q # nie niejawnie rzutuje między różnymi typami. Na przykład `1 + 2.0` nie jest prawidłowym wyrażeniem Q #.
Zamiast tego funkcja Q # zapewnia różnorodne funkcje konwersji typów do konstruowania nowych wartości danego typu.

Na przykład <xref:microsoft.quantum.core.length> ma typ danych wyjściowych `Int`, dlatego dane wyjściowe muszą zostać najpierw skonwertowane na `Double`, zanim będzie można go użyć jako części wyrażenia zmiennoprzecinkowego.
Można to zrobić za pomocą funkcji <xref:microsoft.quantum.convert.intasdouble>:

```qsharp
open Microsoft.Quantum.Convert as Convert;

function HalfLength<'T>(arr : 'T[]) : Double {
    return Convert.IntAsDouble(Length(arr)) / 2.0;
}
```

Przestrzeń nazw <xref:microsoft.quantum.convert> zawiera wspólne funkcje konwersji typów do pracy z podstawowymi wbudowanymi typami, takimi jak `Int`, `Double`, `BigInt`, `Result`i `Bool`:

```qsharp
let bool = Convert.ResultAsBool(One);        // true
let big = Convert.IntAsBigInt(271);          // 271L
let indices = Convert.RangeAsIntArray(0..4); // [0, 1, 2, 3, 4]
```

Przestrzeń nazw <xref:microsoft.quantum.convert> udostępnia również kilka bardziej egzotycznych konwersji, takich jak `FunctionAsOperation`, które konwertują funkcje `'T -> 'U` na nowe operacje `'T => 'U`.

Na koniec standardowa biblioteka Q # zawiera wiele typów zdefiniowanych przez użytkownika, takich jak <xref:microsoft.quantum.math.complex> i <xref:microsoft.quantum.arithmetic.littleendian>.
Wraz z tymi typami Biblioteka standardowa zawiera funkcje, takie jak <xref:microsoft.quantum.arithmetic.bigendianaslittleendian>:

```Q#
open Microsoft.Quantum.Arithmetic as Arithmetic;

let register = Arithmetic.BigEndian(qubits);
IncrementByInteger(Arithmetic.BigEndianAsLittleEndian(register));
```
