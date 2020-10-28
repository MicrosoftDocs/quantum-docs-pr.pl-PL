---
uid: Microsoft.Quantum.Canon.ArrangedQubits
title: ArrangedQubits, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ArrangedQubits
qsharp.summary: Arrange control, target, and helper qubits according to an index
ms.openlocfilehash: 7f5cce3429b72f0ff6e00c2079241272881512da
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716744"
---
# <a name="arrangedqubits-function"></a>ArrangedQubits, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package [](https://nuget.org/packages/)


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

