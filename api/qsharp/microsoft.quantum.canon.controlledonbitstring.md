---
uid: Microsoft.Quantum.Canon.ControlledOnBitString
title: ControlledOnBitString, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ControlledOnBitString
qsharp.summary: Returns a unitary operation that applies an oracle on the target register if the control register state corresponds to a specified bit mask.
ms.openlocfilehash: ca5a6e116eff187060f7a160e42836b170f0362d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716445"
---
# <a name="controlledonbitstring-function"></a>ControlledOnBitString, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package [](https://nuget.org/packages/)


Zwraca operację jednostkową, która stosuje platformę Oracle w rejestrze docelowym, jeśli stan rejestru kontroli odpowiada określonej masce bitów.

```qsharp
function ControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)
```


## <a name="description"></a>Opis

Wynikiem tej funkcji jest operacja, która może być reprezentowana przez transformację jednostkową $U $, która \begin{align} U \ket{b_0 b_1 \cdots b_ {n-1}} \ket{\psi} = \ket{b_0 b_1 \cdots b_ {n-1}} \otimes \begin{Cases} V \ket{\psi} & \textrm{if} (b_0 b_1 \cdots b_ {n-1}) = \texttt{BITS} \\ \\ \ket{\psi} & \textrm{Otherwise} \end{cases}, \end{align}, gdzie $V $ to transformacja jednostkowa, która reprezentuje akcję `oracle` operacji.

## <a name="input"></a>Dane wejściowe

### <a name="bits--bool"></a>bity: [bool](xref:microsoft.quantum.lang-ref.bool)[]

Ciąg bitowy, który kontroluje daną operację jednostkową na.


### <a name="oracle--t--unit-adj--ctl"></a>Oracle: 'T => skorygowania [jednostki](xref:microsoft.quantum.lang-ref.unit) + CTL

Operacja jednostkowa do zastosowania w rejestrze docelowym.



## <a name="output--qubitt--unit-adj--ctl"></a>Output: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[], t) => skorygowania [jednostki](xref:microsoft.quantum.lang-ref.unit) + CTL

Operacja jednostkowa stosowana `oracle` w rejestrze docelowym, jeśli stan rejestru kontroli odpowiada masce bitów `bits` .

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C



## <a name="remarks"></a>Uwagi

Wzorzec określony przez `bits` może być krótszy niż `controlRegister` , w którym to przypadku dodatkowe qubits kontroli są ignorowane (to nie jest ani kontrolowane w $ \ket {0} $ ani $ \ket {1} $).
Jeśli `bits` jest dłuższa niż `controlRegister` , zostanie zgłoszony błąd.

Dana tablica logiczna `bits` i operacja jednostkowa `oracle` są wynikiem operacji, która wykonuje następujące czynności:

* Zastosuj `X` operację do każdego qubitu rejestru kontroli, który odnosi się do `false` elementu `bits` ;
* Zastosuj `Controlled oracle` do rejestrów kontrolki i celu;
* Zastosuj `X` operację do każdego qubitu rejestru kontroli, który odnosi się do `false` elementu ponownie, `bits` Aby przywrócić pierwotny stan.

Dane wyjściowe `Controlled` Funktor są szczególnym przypadkiem, `ControlledOnBitString` gdzie `bits` jest równe `[true, ..., true]` .