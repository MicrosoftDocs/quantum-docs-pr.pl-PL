---
uid: Microsoft.Quantum.Canon.ArrangedQubits
title: ArrangedQubits, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ArrangedQubits
qsharp.summary: Arrange control, target, and helper qubits according to an index
ms.openlocfilehash: 07a4ed5fe99dedb333246f7161d157dcd01a01da
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841074"
---
# <a name="arrangedqubits-function"></a>ArrangedQubits, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Rozmieszczanie formantów, obiektów docelowych i qubits pomocnika zgodnie z indeksem

```qsharp
function ArrangedQubits (controls : Qubit[], target : Qubit, helper : Qubit[]) : Qubit[]
```


## <a name="description"></a>Opis

Zwraca tablicę qubit z elementem docelowym przy indeksie 0 i kontrolujem indeks 2 ^ i.  Qubits pomocnika są wstawiane do wszystkich innych pozycji w tablicy.

## <a name="input"></a>Dane wejściowe

### <a name="controls--qubit"></a>kontrolki: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]




### <a name="target--qubit"></a>obiekt docelowy: [qubit](xref:microsoft.quantum.lang-ref.qubit)




### <a name="helper--qubit"></a>pomocnik: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]





## <a name="output--qubit"></a>Wynik: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

