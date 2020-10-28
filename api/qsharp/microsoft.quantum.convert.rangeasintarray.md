---
uid: Microsoft.Quantum.Convert.RangeAsIntArray
title: RangeAsIntArray, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: RangeAsIntArray
qsharp.summary: Creates an array `arr` of integers enumerated by start..step..end.
ms.openlocfilehash: bd3ac51d2925d7a4450b2bc5e6f7899fcab18f2c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713365"
---
# <a name="rangeasintarray-function"></a>RangeAsIntArray, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)

Package [](https://nuget.org/packages/)


Tworzy tablicę `arr` liczb całkowitych wyliczanych przez początek.. krok.. punktów.

```qsharp
function RangeAsIntArray (range : Range) : Int[]
```


## <a name="input"></a>Dane wejściowe

### <a name="range--range"></a>zakres: [zakres](xref:microsoft.quantum.lang-ref.range)

`Range`Wartości `start..step..end` do przekonwertowania na tablicę.



## <a name="output--int"></a>Wynik: [int](xref:microsoft.quantum.lang-ref.int)[]

Nowa tablica liczb całkowitych odpowiadających wartościom powtarzanym przez `range` .