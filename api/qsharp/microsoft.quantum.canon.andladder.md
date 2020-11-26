---
uid: Microsoft.Quantum.Canon.AndLadder
title: AndLadder, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: AndLadder
qsharp.summary: Performs a controlled "AND ladder" on a register of target qubits.
ms.openlocfilehash: 2c6114ec8a5caabdeea8ab7e26a4877e1633671c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209727"
---
# <a name="andladder-operation"></a>AndLadder, operacja

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Wykonuje kontrolowane "i drabinę" w rejestrze docelowej qubits.

```qsharp
operation AndLadder (ccnot : Microsoft.Quantum.Canon.CCNOTop, controls : Qubit[], targets : Qubit[]) : Unit is Adj
```


## <a name="description"></a>Opis

Ta operacja dotyczy transformacji opisanej przez następujące mapowanie podstawy obliczeniowej, $ $ \begin{align} \ket{x \_ 1, \dots, x \_ n} \ket{y \_ 1, \dots, y \_ {n-1}} \mapsto \ket{x \_ 1, \dots, x \_ n} \ket{y \_ 1 \oplus (x \_ 1 \land x \_ 2), \dots, y \_ {n-1} \oplus (x \_ 1 \land x \_ 2 \land \cdots \land x \_ {n-1}}, \end{align} $ $ WHERE $ \ket{x \_ 1, \dots, x n} $ odwołuje się do \_ Stanów bazowych `controls` , i gdzie $ \ket{y \_ 1, \dots, y \_ {n-1}} $ odnosi się do Stanów bazowych `targets` .

## <a name="input"></a>Dane wejściowe

### <a name="ccnot--ccnotop"></a>ccnot: [CCNOTop](xref:Microsoft.Quantum.Canon.CCNOTop)

Brama CCNOT do użycia na potrzeby konstruowania.


### <a name="controls--qubit"></a>kontrolki: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Rejestr qubits, który ma być używany jako kontrolki i Drabinka.
Ta operacja pozostawia podstawowe Stany `controls` niezmiennej.
Długość `controls` musi wynosić co najmniej 2 i musi być równa 1 i długości `targets` .


### <a name="targets--qubit"></a>elementy docelowe: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Długość `targets` musi być co najmniej 1 i równa długości `controls` minus jeden.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Uwagi

- Używane jako część <xref:microsoft.quantum.canon.applymulticontrolledc> i <xref:microsoft.quantum.canon.applymulticontrolledca> .
- Aby uzyskać informacje na temat diagramu wyjaśnień i obwodów, zobacz rysunek 4,10, sekcja 4,3 w Nielsen & Czuang.

## <a name="references"></a>Odwołania

- [*Michael a. Nielsen, Tomasz L. Czuang*, obliczenia Quantum i informacje o Quantum](http://doi.org/10.1017/CBO9780511976667)