---
uid: Microsoft.Quantum.Synthesis.DecomposedOn
title: DecomposedOn, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: DecomposedOn
qsharp.summary: Decomposes a permutation on a variable
ms.openlocfilehash: 79f952e7bc7ba9f5337cf5e7a625e0d270a2e17a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203233"
---
# <a name="decomposedon-function"></a>DecomposedOn, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Synteza](xref:Microsoft.Quantum.Synthesis)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

