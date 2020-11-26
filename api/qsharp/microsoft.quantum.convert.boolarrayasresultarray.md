---
uid: Microsoft.Quantum.Convert.BoolArrayAsResultArray
title: BoolArrayAsResultArray, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolArrayAsResultArray
qsharp.summary: Converts a `Bool[]` type to a `Result[]` type, where `true` is mapped to `One` and `false` is mapped to `Zero`.
ms.openlocfilehash: 388fb67ba33810fc813fb646577bfa7f4a2b51ae
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224466"
---
# <a name="boolarrayasresultarray-function"></a>BoolArrayAsResultArray, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Konwertuje `Bool[]` Typ na `Result[]` Typ, gdzie `true` jest mapowany na `One` i `false` jest mapowany na `Zero` .

```qsharp
function BoolArrayAsResultArray (input : Bool[]) : Result[]
```


## <a name="input"></a>Dane wejściowe

### <a name="input--bool"></a>Wejście: [bool](xref:microsoft.quantum.lang-ref.bool)[]

`Bool[]` do przekonwertowania.



## <a name="output--__invalidresult__"></a>Dane wyjściowe __: <Result> nieprawidłowe__[]

`Result[]`Reprezentujący `input` .