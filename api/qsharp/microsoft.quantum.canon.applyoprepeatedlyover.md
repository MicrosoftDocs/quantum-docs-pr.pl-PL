---
uid: Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver
title: ApplyOpRepeatedlyOver, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyOpRepeatedlyOver
qsharp.summary: Applies the same op over a qubit register multiple times.
ms.openlocfilehash: 09f54be33a7b5c58a317a949290f5cd6d54fe841
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717850"
---
# <a name="applyoprepeatedlyover-operation"></a>ApplyOpRepeatedlyOver, operacja

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package [](https://nuget.org/packages/)


Stosuje tę samą wartość operacji w przypadku rejestru qubit wiele razy.

```qsharp
operation ApplyOpRepeatedlyOver (op : (Qubit[] => Unit), targets : Int[][], register : Qubit[]) : Unit
```


## <a name="input"></a>Dane wejściowe

### <a name="op--qubit--unit"></a>op: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [Jednostka](xref:microsoft.quantum.lang-ref.unit)> 

Operacja do zastosowania wiele razy w rejestrze qubit


### <a name="targets--int"></a>elementy docelowe: [int](xref:microsoft.quantum.lang-ref.int)[] []

Zagnieżdżone tablice opisujące cele operacji. Każda tablica powinna zawierać listę liczby całkowite opisujących qubits, które mają być używane.


### <a name="register--qubit"></a>Rejestr: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Zarejestruj się, aby zarejestrować się w qubit.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. Canon. ApplySeriesOfOps](xref:Microsoft.Quantum.Canon.ApplySeriesOfOps)