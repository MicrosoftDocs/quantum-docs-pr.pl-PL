---
uid: Microsoft.Quantum.Arrays.DrawMany
title: DrawMany, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: DrawMany
qsharp.summary: Repeats an operation for a given number of samples, collecting its outputs in an array.
ms.openlocfilehash: bf63ce308679cef97c776d3383ff732ed4d4e500
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846201"
---
# <a name="drawmany-operation"></a>DrawMany, operacja

Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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



## <a name="example"></a>Przykład

Następujące przykłady są liczbami całkowitymi, w przypadku operacji, która próbkuje pojedynczy bit w danym momencie.

```qsharp
let randomInteger = BoolArrayAsInt(DrawMany(SampleRandomBit, 16, ()));
```

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. Canon. REPEAT](xref:Microsoft.Quantum.Canon.Repeat)