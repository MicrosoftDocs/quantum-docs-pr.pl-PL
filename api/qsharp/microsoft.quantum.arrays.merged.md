---
uid: Microsoft.Quantum.Arrays.Merged
title: Funkcja scalona
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Merged
qsharp.summary: Given two sorted arrays, returns a single array containing the elements of both in sorted order. Used internally by merge sort.
ms.openlocfilehash: b3383f8a04e6fa23562aa81e5b911d06752f4fb5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220641"
---
# <a name="merged-function"></a>Funkcja scalona

Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


W przypadku dwóch posortowanych tablic funkcja zwraca pojedynczą tablicę zawierającą elementy obu elementów w sortowanej kolejności. Używane wewnętrznie przez scalanie sortowania.

```qsharp
function Merged<'T> (comparison : (('T, 'T) -> Bool), left : 'T[], right : 'T[]) : 'T[]
```


## <a name="input"></a>Dane wejściowe

### <a name="comparison--tt---bool"></a>Porównanie: (t, t)-> [bool](xref:microsoft.quantum.lang-ref.bool)




### <a name="left--t"></a>Left: t []




### <a name="right--t"></a>Right: t []





## <a name="output--t"></a>Wynik: t []



## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C

