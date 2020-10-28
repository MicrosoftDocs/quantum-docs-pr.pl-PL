---
uid: Microsoft.Quantum.Arrays.DrawMany
title: DrawMany, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: DrawMany
qsharp.summary: Repeats an operation for a given number of samples, collecting its outputs in an array.
ms.openlocfilehash: 601fe603a869dcf977c1ceade5819ee64f634d53
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719373"
---
# <a name="drawmany-operation"></a>DrawMany, operacja

Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Package [](https://nuget.org/packages/)


Powtarza operację dla danej liczby próbek, zbierając wyniki wyjściowe w tablicy.

```qsharp
operation DrawMany<'TInput, 'TOutput> (op : ('TInput => 'TOutput), nSamples : Int, input : 'TInput) : 'TOutput[]
```


## <a name="input"></a>Dane wejściowe

### <a name="op--tinput--toutput"></a>op: "TInput =>" TOutput 

Operacja, która ma być wywoływana wielokrotnie.


### <a name="nsamples--int"></a>nSamples: [int](xref:microsoft.quantum.lang-ref.int)

Liczba próbek wywołujących `op` do zebrania.


### <a name="input--tinput"></a>dane wejściowe: "TInput

Dane wejściowe do przesłania `op` .



## <a name="output--toutput"></a>Dane wyjściowe: "TOutput []



## <a name="type-parameters"></a>Parametry typu

### <a name="tinput"></a>'TInput


### <a name="toutput"></a>'TOutput



## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. Canon. REPEAT](xref:Microsoft.Quantum.Canon.Repeat)