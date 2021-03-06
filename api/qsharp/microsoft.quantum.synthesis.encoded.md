---
uid: Microsoft.Quantum.Synthesis.Encoded
title: Funkcja zakodowana
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: Encoded
qsharp.summary: Encode truth table in {1,-1} coding
ms.openlocfilehash: 44f6b247e6bfab7b55c46146cb63f8b6d219955b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855498"
---
# <a name="encoded-function"></a>Funkcja zakodowana

Przestrzeń nazw: [Microsoft. Quantum. Synteza](xref:Microsoft.Quantum.Synthesis)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Koduj tabelę prawdy w {1,-1} kodowaniu

```qsharp
function Encoded (table : Bool[]) : Int[]
```


## <a name="input"></a>Dane wejściowe

### <a name="table--bool"></a>Tabela: [bool](xref:microsoft.quantum.lang-ref.bool)[]

Tabela prawdy jako tablica wartości prawdy



## <a name="output--int"></a>Wynik: [int](xref:microsoft.quantum.lang-ref.int)[]

Tabela prawdy jako tablica {1,-1} liczb całkowitych

## <a name="example"></a>Przykład

```qsharp
Encoded([false, false, false, true]); // [1, 1, 1, -1]
```