---
uid: Microsoft.Quantum.Canon.ApplyControlledOnBitString
title: ApplyControlledOnBitString, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyControlledOnBitString
qsharp.summary: Applies a unitary operation on the target register, controlled on a a state specified by a given bit mask.
ms.openlocfilehash: 7a054511bacff574e6f7e889ace048c78886cf91
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718356"
---
# <a name="applycontrolledonbitstring-operation"></a>ApplyControlledOnBitString, operacja

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package [](https://nuget.org/packages/)


Stosuje operacje jednostkowe na rejestrze docelowym, kontrolowane na podstawie stanu określonego przez daną maskę bitową.

```qsharp
operation ApplyControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl), controlRegister : Qubit[], targetRegister : 'T) : Unit
```


## <a name="input"></a>Dane wejściowe

### <a name="bits--bool"></a>bity: [bool](xref:microsoft.quantum.lang-ref.bool)[]

Ciąg bitowy, który kontroluje daną operację jednostkową na.


### <a name="oracle--t--unit-adj--ctl"></a>Oracle: 'T => skorygowania [jednostki](xref:microsoft.quantum.lang-ref.unit) + CTL

Operacja jednostkowa do zastosowania w rejestrze docelowym.


### <a name="controlregister--qubit"></a>controlRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Rejestr Quantum kontrolujący aplikację `oracle` .


### <a name="targetregister--t"></a>targetRegister: 'T

Docelowy rejestr, który ma zostać przesłany `oracle` jako dane wejściowe.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C



## <a name="remarks"></a>Uwagi

Wzorzec określony przez `bits` może być krótszy niż `controlRegister` , w którym to przypadku dodatkowe qubits kontroli są ignorowane (to nie jest ani kontrolowane w $ \ket {0} $ ani $ \ket {1} $).
Jeśli `bits` jest dłuższa niż `controlRegister` , zostanie zgłoszony błąd.

Na przykład `bits = [0,1,0,0,1]` oznacza, że `oracle` jest stosowana, jeśli `controlRegister` jest w stanie $ \ket {0} \ket {1} \ket {0} \ket {0} \ket {1} $.