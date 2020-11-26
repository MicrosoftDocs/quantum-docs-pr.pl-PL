---
uid: Microsoft.Quantum.Logical.Conditioned
title: Funkcja warunkowa
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Conditioned
qsharp.summary: Returns one of two values, depending on the value of a Boolean condition.
ms.openlocfilehash: c0f55d4db95ad1f0d2b7f291cbc6ba8ae704cb81
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198490"
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

```Q#
let x = condition ? ifTrue | ifFalse;
let x = Conditioned(condition, ifTrue, ifFalse);
```