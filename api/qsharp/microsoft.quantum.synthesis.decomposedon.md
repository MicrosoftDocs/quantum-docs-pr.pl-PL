---
uid: Microsoft.Quantum.Synthesis.DecomposedOn
title: DecomposedOn, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: DecomposedOn
qsharp.summary: Decomposes a permutation on a variable
ms.openlocfilehash: b033723a50fb85e77c9d4baec1f94231327e9b25
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725218"
---
# <a name="decomposedon-function"></a>DecomposedOn, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Synteza](xref:Microsoft.Quantum.Synthesis)

Package [](https://nuget.org/packages/)


Dekomponowauje permutację na zmiennej

```qsharp
function DecomposedOn (perm : Int[], index : Int) : ((Int[], Int[]), Int[])
```


## <a name="description"></a>Opis

Nadana Permutacja $ \pi $ ( `perm` ) i indeks $i $ ( `index` ), ta metoda zwraca trzy Permutacje $ ((\ pi_l, \ pi_r), \pi ') $ w taki sposób, że obrazy $ \ pi_l $ i $ \ pi_r $ nie zmieniają bitów w ich elementach w indeksach innych niż $i $ i obrazy $ \pi ' $ nie zmieniają bitu $i $ w ich elementach.

## <a name="input"></a>Dane wejściowe

### <a name="perm--int"></a>uprawnienie: [int](xref:microsoft.quantum.lang-ref.int)[]




### <a name="index--int"></a>indeks: [int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--intintint"></a>Wynik: (([int](xref:microsoft.quantum.lang-ref.int)[],[int](xref:microsoft.quantum.lang-ref.int)[]),[int](xref:microsoft.quantum.lang-ref.int)[])

