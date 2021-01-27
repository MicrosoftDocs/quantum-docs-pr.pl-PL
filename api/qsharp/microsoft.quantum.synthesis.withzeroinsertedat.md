---
uid: Microsoft.Quantum.Synthesis.WithZeroInsertedAt
title: WithZeroInsertedAt, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: WithZeroInsertedAt
qsharp.summary: Insert a 0-bit into an integer
ms.openlocfilehash: 7d5f8838b6ae555524fb0e82e14f93e6c77e43d4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855195"
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