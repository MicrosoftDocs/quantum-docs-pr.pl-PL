---
uid: Microsoft.Quantum.Canon.ApplyControlledOnBitString
title: ApplyControlledOnBitString, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyControlledOnBitString
qsharp.summary: Applies a unitary operation on the target register, controlled on a a state specified by a given bit mask.
ms.openlocfilehash: 82adc74e23e1d50cb6436176a973fdd1a0eeb3bd
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841943"
---
# <a name="applycontrolledonbitstring-operation"></a>ApplyControlledOnBitString, operacja

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Stosuje operacje jednostkowe na rejestrze docelowym, kontrolowane na podstawie stanu określonego przez daną maskę bitową.

```qsharp
operation ApplyControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl), controlRegister : Qubit[], targetRegister : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a>Dane wejściowe

### <a name="bits--bool"></a>bity: [bool](xref:microsoft.quantum.lang-ref.bool)[]

Ciąg bitowy, który kontroluje daną operację jednostkową na.


### <a name="oracle--t--unit--is-adj--ctl"></a>Oracle: t = [jednostka](xref:microsoft.quantum.lang-ref.unit) > jest korektą i listą CTL

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