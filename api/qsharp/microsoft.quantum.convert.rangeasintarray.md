---
uid: Microsoft.Quantum.Convert.RangeAsIntArray
title: RangeAsIntArray, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: RangeAsIntArray
qsharp.summary: Creates an array `arr` of integers enumerated by start..step..end.
ms.openlocfilehash: f756e42aef7dc600e1fc6943a02513ac791f2320
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214011"
---
# <a name="rangeasintarray-function"></a>RangeAsIntArray, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Tworzy tablicę `arr` liczb całkowitych wyliczanych przez początek.. krok.. punktów.

```qsharp
function RangeAsIntArray (range : Range) : Int[]
```


## <a name="input"></a>Dane wejściowe

### <a name="range--range"></a>zakres: [zakres](xref:microsoft.quantum.lang-ref.range)

`Range`Wartości `start..step..end` do przekonwertowania na tablicę.



## <a name="output--int"></a>Wynik: [int](xref:microsoft.quantum.lang-ref.int)[]

Nowa tablica liczb całkowitych odpowiadających wartościom powtarzanym przez `range` .