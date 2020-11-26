---
uid: Microsoft.Quantum.Diagnostics.AllowAtMostNCallsCA
title: AllowAtMostNCallsCA, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllowAtMostNCallsCA
qsharp.summary: Between a call to this operation and its adjoint, asserts that a given operation is called at most a certain number of times.
ms.openlocfilehash: 7caf33e33318bb74cb160436940eff9f0f2782cc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202570"
---
# <a name="allowatmostncallsca-operation"></a>AllowAtMostNCallsCA, operacja

Przestrzeń nazw: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Między wywołaniem tej operacji i jej częścią, potwierdza, że dana operacja jest wywoływana co najwyżej określoną liczbę razy.

```qsharp
operation AllowAtMostNCallsCA<'TInput, 'TOutput> (nTimes : Int, op : ('TInput => 'TOutput is Adj + Ctl), message : String) : Unit is Adj
```


## <a name="input"></a>Dane wejściowe

### <a name="ntimes--int"></a>nTimes: [int](xref:microsoft.quantum.lang-ref.int)

Maksymalna liczba przypadków, gdy `op` może być wywoływana.


### <a name="op--tinput--toutput--is-adj--ctl"></a>op: "TInput =>" TOutput to przymiotnik + CTL

Operacja, której wywołania mają być ograniczone.


### <a name="message--string"></a>komunikat: [ciąg](xref:microsoft.quantum.lang-ref.string)

Komunikat, który ma być wyświetlany w przypadku awarii.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametry typu

### <a name="tinput"></a>'TInput


### <a name="toutput"></a>'TOutput



## <a name="remarks"></a>Uwagi

Ta operacja może zostać zamieniona na elementy docelowe, które ich nie obsługują.