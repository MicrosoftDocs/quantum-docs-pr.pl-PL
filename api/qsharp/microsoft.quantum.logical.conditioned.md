---
uid: Microsoft.Quantum.Logical.Conditioned
title: Funkcja warunkowa
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Conditioned
qsharp.summary: Returns one of two values, depending on the value of a Boolean condition.
ms.openlocfilehash: ea3b8eba960acceb6540978c6fccd9f796b0f67d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98817300"
---
# <a name="conditioned-function"></a>Funkcja warunkowa

Przestrzeń nazw: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Zwraca jedną z dwóch wartości, w zależności od wartości warunku logicznego.

```qsharp
function Conditioned<'T> (condition : Bool, ifTrue : 'T, ifFalse : 'T) : 'T
```


## <a name="input"></a>Dane wejściowe

### <a name="condition--bool"></a>warunek: [bool](xref:microsoft.quantum.lang-ref.bool)

Warunek służący do kontrolowania, które dane wejściowe są zwracane.


### <a name="iftrue--t"></a>ifTrue: 'T

Wartość, która ma zostać zwrócona, gdy `condition` jest `true` .


### <a name="iffalse--t"></a>ifFalse: 'T

Wartość, która ma zostać zwrócona, gdy `condition` jest `false` .



## <a name="output--t"></a>Dane wyjściowe: 'T

`ifTrue` Jeśli `condition` jest `true` , i `ifFalse` w inny sposób.

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C



## <a name="remarks"></a>Uwagi

W przeciwieństwie do `?|` operatora, ta funkcja nie jest krótka obwód, tak że oba dane wejściowe są w pełni oceniane.

W przypadku zachowania do krótkiego obwodu następujące elementy są równoważne:

```qsharp
let x = condition ? ifTrue | ifFalse;
let x = Conditioned(condition, ifTrue, ifFalse);
```