---
uid: Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTable
title: ApplyXControlledOnTruthTable, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyXControlledOnTruthTable
qsharp.summary: Applies the @"microsoft.quantum.intrinsic.x" operation on `target`, if the Boolean function `func` evaluates to true for the classical assignment in `controlRegister`.
ms.openlocfilehash: 73d63936f02a52dfbbad7b8575110177a9e4463d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725246"
---
# <a name="applyxcontrolledontruthtable-operation"></a>ApplyXControlledOnTruthTable, operacja

Przestrzeń nazw: [Microsoft. Quantum. Synteza](xref:Microsoft.Quantum.Synthesis)

Package [](https://nuget.org/packages/)


Stosuje @"microsoft.quantum.intrinsic.x" operację na `target` , jeśli funkcja logiczna `func` zwróci wartość true dla klasycznego przypisania w `controlRegister` .

```qsharp
operation ApplyXControlledOnTruthTable (func : BigInt, controlRegister : Qubit[], target : Qubit) : Unit
```


## <a name="description"></a>Opis

Operacja implementuje operacje jednostkowe \begin{align} U\ket {x} \ KET {y} = \ket{x}\ket{y \oplus f (x)} \end{align}, gdzie $x $ i $y $ reprezentuje `controlRegister` odpowiednio i `target` .

Funkcja logiczna $f $ jest reprezentowana jako tabela prawdy w warunkach dużej liczby całkowitej.
Na przykład większość funkcji na trzech danych wejściowych jest reprezentowana przez bitstring `11101000` , gdzie najbardziej znaczący bit `1` odpowiada przypisaniu wejściowemu `(1, 1, 1)` , a najmniej znaczący bit `0` odpowiada przypisaniu wejściowemu `(0, 0, 0)` .
Może być reprezentowana przez dużą liczbę całkowitą `0xE8L` w notacji szesnastkowej lub jako `232L` notację dziesiętną.  `L`Sufiks wskazuje, że stała jest typu `BigInt` .
Więcej szczegółów na temat tej reprezentacji można znaleźć w [tabelach prawdy Kata](https://github.com/microsoft/QuantumKatas/tree/main/TruthTables).

Implementacja wykorzystuje @"microsoft.quantum.intrinsic.cnot" @"microsoft.quantum.intrinsic.r1" bramy i.

## <a name="input"></a>Dane wejściowe

### <a name="func--bigint"></a>Func: [bigint](xref:microsoft.quantum.lang-ref.bigint)

Tabela wartości logicznych prawdy reprezentowana jako duża liczba całkowita


### <a name="controlregister--qubit"></a>controlRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Rejestr kontroli qubits


### <a name="target--qubit"></a>obiekt docelowy: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit docelowy



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>Dokumentacja

- [*N. Schuch* , *J. Siewert* , PRL 91, no. 027902, 2003, ArXiv: Quant-pH/0303063](https://arxiv.org/abs/quant-ph/0303063)
- [*Mathias Soeken* , *Martin Roetteler* , ArXiv: 2005.12310](https://arxiv.org/abs/2005.12310)

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. synteza. ApplyXControlledOnTruthTableWithCleanTarget](xref:Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTableWithCleanTarget)