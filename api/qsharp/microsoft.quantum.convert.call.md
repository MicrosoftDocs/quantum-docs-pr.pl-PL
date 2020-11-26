---
uid: Microsoft.Quantum.Convert.Call
title: Operacja wywołania
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: Call
qsharp.summary: Calls a function with a given input.
ms.openlocfilehash: 92c159cef878fb587b0ed514fd6660dd19527cab
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214215"
---
# <a name="call-operation"></a>Operacja wywołania

Przestrzeń nazw: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Wywołuje funkcję z danymi wejściowymi.

```qsharp
operation Call<'Input, 'Output> (fn : ('Input -> 'Output), input : 'Input) : 'Output
```


## <a name="description"></a>Opis

Dana funkcja i dane wejściowe do tej funkcji, wywołuje funkcję i zwraca dane wyjściowe.

## <a name="input"></a>Dane wejściowe

### <a name="fn--input---output"></a>fn: dane wyjściowe "Input->"

Funkcja, która ma zostać wywołana.


### <a name="input--input"></a>dane wejściowe: "wejście

Dane wejściowe do przesłania do funkcji.



## <a name="output--output"></a>Dane wyjściowe: "output"

Wynik wywołania `fn` .

## <a name="type-parameters"></a>Parametry typu

### <a name="input"></a>"Dane wejściowe


### <a name="output"></a>"Dane wyjściowe



## <a name="remarks"></a>Uwagi

Ta operacja jest szczególnie przydatna w przypadku wymuszania wywołania funkcji w konkretnym miejscu w ramach operacji lub do wywołania funkcji, w której oczekiwana jest operacja.