---
uid: Microsoft.Quantum.Convert.FunctionAsOperation
title: FunctionAsOperation, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: FunctionAsOperation
qsharp.summary: Converts functions to operations.
ms.openlocfilehash: 10703818242cf6b3853f08a45bfb9094f397f6c2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224381"
---
# <a name="functionasoperation-function"></a>FunctionAsOperation, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Konwertuje funkcje na operacje.

```qsharp
function FunctionAsOperation<'Input, 'Output> (fn : ('Input -> 'Output)) : ('Input => 'Output)
```


## <a name="description"></a>Opis

Dana funkcja zwraca operację, która wywołuje tę funkcję, i która nic nie robi.

## <a name="input"></a>Dane wejściowe

### <a name="fn--input---output"></a>fn: dane wyjściowe "Input->"

Funkcja, która ma zostać przekonwertowana na operację.



## <a name="output--input--output"></a>Wyjście: dane wyjściowe "Input =>" 

Operacja `op` , która `op(input)` jest taka sama jak `fn(input)` dla wszystkich `input` .

## <a name="type-parameters"></a>Parametry typu

### <a name="input"></a>"Dane wejściowe

Typ danych wejściowych funkcji do przekonwertowania.
### <a name="output"></a>"Dane wyjściowe

Typ danych wyjściowych funkcji do przekonwertowania.

## <a name="remarks"></a>Uwagi

Jest to przydatne głównie do przekazywania funkcji do funkcji lub operacji, które oczekują operacji jako dane wejściowe.