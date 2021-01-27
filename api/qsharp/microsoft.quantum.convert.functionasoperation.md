---
uid: Microsoft.Quantum.Convert.FunctionAsOperation
title: FunctionAsOperation, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: FunctionAsOperation
qsharp.summary: Converts functions to operations.
ms.openlocfilehash: cf4f8c97bf38b3a64eb952d0a502bc21c29c579c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98833837"
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