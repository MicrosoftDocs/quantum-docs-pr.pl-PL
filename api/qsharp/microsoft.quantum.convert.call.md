---
uid: Microsoft.Quantum.Convert.Call
title: Operacja wywołania
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: Call
qsharp.summary: Calls a function with a given input.
ms.openlocfilehash: 93458d08aa83ffa8b7b33de8bf51c970af291db9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850208"
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