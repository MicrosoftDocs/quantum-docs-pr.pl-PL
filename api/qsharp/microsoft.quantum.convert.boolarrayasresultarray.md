---
uid: Microsoft.Quantum.Convert.BoolArrayAsResultArray
title: BoolArrayAsResultArray, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolArrayAsResultArray
qsharp.summary: Converts a `Bool[]` type to a `Result[]` type, where `true` is mapped to `One` and `false` is mapped to `Zero`.
ms.openlocfilehash: b30da07272ee1a6c19ae13afa618ba5deb7aaa2d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98834188"
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