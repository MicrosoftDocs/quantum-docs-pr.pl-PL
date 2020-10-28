---
uid: Microsoft.Quantum.Canon.ApplyToEachC
title: ApplyToEachC, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachC
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `C` indicates that the single-qubit operation is controllable.
ms.openlocfilehash: dfa18b6eb7a2c42fa2982994a2fc92170b52599c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717565"
---
# <a name="applytoeachc-operation"></a>ApplyToEachC, operacja

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package [](https://nuget.org/packages/)


Stosuje operację pojedynczego qubit do każdego elementu w rejestrze.
Modyfikator `C` wskazuje, że operacje pojedynczej qubit są kontrolowane.

```qsharp
operation ApplyToEachC<'T> (singleElementOperation : ('T => Unit is Ctl), register : 'T[]) : Unit
```


## <a name="input"></a>Dane wejściowe

### <a name="singleelementoperation--t--unit-ctl"></a>singleElementOperation: t => [jednostki](xref:microsoft.quantum.lang-ref.unit) CTL

Operacja do zastosowania do każdego qubitu.


### <a name="register--t"></a>Rejestr: t []

Tablica qubits, na której ma zostać zastosowana dana operacja.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C

Obiekt docelowy, na którym działa operacja.

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. Canon. ApplyToEach](xref:Microsoft.Quantum.Canon.ApplyToEach)