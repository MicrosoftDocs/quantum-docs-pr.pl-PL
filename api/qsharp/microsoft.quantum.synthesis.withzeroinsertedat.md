---
uid: Microsoft.Quantum.Synthesis.WithZeroInsertedAt
title: WithZeroInsertedAt, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: WithZeroInsertedAt
qsharp.summary: Insert a 0-bit into an integer
ms.openlocfilehash: 414b703151b9152aa69709d9c28e68e5ae63506f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228869"
---
# <a name="withzeroinsertedat-function"></a>WithZeroInsertedAt, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Synteza](xref:Microsoft.Quantum.Synthesis)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Wstaw 0-bitowe do liczby całkowitej

```qsharp
function WithZeroInsertedAt (position : Int, value : Int) : Int
```


## <a name="description"></a>Opis

Ta operacja Pobiera liczbę całkowitą, wstawia 0 w bitach `position` i zwraca zaktualizowaną wartość jako liczbę całkowitą.  Na przykład wstawianie 0 w pozycji 2 w liczbie 10 (10 zł _ {10} = 1010_ {2} $) zwraca liczbę 18 ($18 _ {10} = 10010_ {2} $).

## <a name="input"></a>Dane wejściowe

### <a name="position--int"></a>Pozycja: [int](xref:microsoft.quantum.lang-ref.int)

Położenie, w którym wstawiono 0


### <a name="value--int"></a>wartość: [int](xref:microsoft.quantum.lang-ref.int)

Wartość, która została zmodyfikowana



## <a name="output--int"></a>Wynik: [int](xref:microsoft.quantum.lang-ref.int)

Zmodyfikowana wartość