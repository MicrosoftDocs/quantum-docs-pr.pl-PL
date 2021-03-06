---
uid: Microsoft.Quantum.Canon.ControlledOnBitString
title: ControlledOnBitString, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ControlledOnBitString
qsharp.summary: Returns a unitary operation that applies an oracle on the target register if the control register state corresponds to a specified bit mask.
ms.openlocfilehash: 176170cc972ca67b812b84f79cf97ba5418be9b6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840805"
---
# <a name="controlledonbitstring-function"></a>ControlledOnBitString, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Zwraca operację jednostkową, która stosuje platformę Oracle w rejestrze docelowym, jeśli stan rejestru kontroli odpowiada określonej masce bitów.

```qsharp
function ControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)
```


## <a name="description"></a>Opis

Wynikiem tej funkcji jest operacja, która może być reprezentowana przez transformację jednostkową $U $, która \begin{align} U \ket{b_0 b_1 \cdots b_ {n-1}} \ket{\psi} = \ket{b_0 b_1 \cdots b_ {n-1}} \otimes \begin{Cases} V \ket{\psi} & \textrm{if} (b_0 b_1 \cdots b_ {n-1}) = \texttt{BITS} \\ \\ \ket{\psi} & \textrm{Otherwise} \end{cases}, \end{align}, gdzie $V $ to transformacja jednostkowa, która reprezentuje akcję `oracle` operacji.

## <a name="input"></a>Dane wejściowe

### <a name="bits--bool"></a>bity: [bool](xref:microsoft.quantum.lang-ref.bool)[]

Ciąg bitowy, który kontroluje daną operację jednostkową na.


### <a name="oracle--t--unit--is-adj--ctl"></a>Oracle: t = [jednostka](xref:microsoft.quantum.lang-ref.unit) > jest korektą i listą CTL

Operacja jednostkowa do zastosowania w rejestrze docelowym.



## <a name="output--qubitt--unit--is-adj--ctl"></a>Output: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[], t) => [Unit](xref:microsoft.quantum.lang-ref.unit)  to przymiotnik + CTL

Operacja jednostkowa stosowana `oracle` w rejestrze docelowym, jeśli stan rejestru kontroli odpowiada masce bitów `bits` .

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C



## <a name="example"></a>Przykład

Następujące fragmenty kodu są równoważne:

```qsharp
(ControlledOnBitString(bits, oracle))(controlRegister, targetRegister);
```

oraz

```qsharp
within {
    ApplyPauliFromBitString(PauliX, false, bits, controlRegister);
} apply {
    Controlled oracle(controlRegister, targetRegister);
}
```

Poniższy kod przygotowuje stan $ \frac {1} {2} (\ket {00} -\ket {01} + \ket {10} + \ket {11} ) $:

```qsharp
using (register = Qubit[2]) {
    ApplyToEach(H, register);
    (ControlledOnBitString([false], Z))(register[0..0], register[1]);
}
```

## <a name="remarks"></a>Uwagi

Wzorzec określony przez `bits` może być krótszy niż `controlRegister` , w którym to przypadku dodatkowe qubits kontroli są ignorowane (to nie jest ani kontrolowane w $ \ket {0} $ ani $ \ket {1} $).
Jeśli `bits` jest dłuższa niż `controlRegister` , zostanie zgłoszony błąd.

Dana tablica logiczna `bits` i operacja jednostkowa `oracle` są wynikiem operacji, która wykonuje następujące czynności:

* Zastosuj `X` operację do każdego qubitu rejestru kontroli, który odnosi się do `false` elementu `bits` ;
* Zastosuj `Controlled oracle` do rejestrów kontrolki i celu;
* Zastosuj `X` operację do każdego qubitu rejestru kontroli, który odnosi się do `false` elementu ponownie, `bits` Aby przywrócić pierwotny stan.

Dane wyjściowe `Controlled` Funktor są szczególnym przypadkiem, `ControlledOnBitString` gdzie `bits` jest równe `[true, ..., true]` .