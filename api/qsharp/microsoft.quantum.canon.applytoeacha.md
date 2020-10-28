---
uid: Microsoft.Quantum.Canon.ApplyToEachA
title: ApplyToEachA, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachA
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `A` indicates that the single-qubit operation is adjointable.
ms.openlocfilehash: 9485c6549ed4e1a6fb3abdfa3f85ba35579d8b0b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717579"
---
# <a name="applytoeacha-operation"></a>ApplyToEachA, operacja

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package [](https://nuget.org/packages/)


Stosuje operację pojedynczego qubit do każdego elementu w rejestrze.
Modyfikator `A` wskazuje, że operacja pojedynczego qubit jest sąsiedni.

```qsharp
operation ApplyToEachA<'T> (singleElementOperation : ('T => Unit is Adj), register : 'T[]) : Unit
```


## <a name="input"></a>Dane wejściowe

### <a name="singleelementoperation--t--unit-adj"></a>singleElementOperation: 'T => korekta [jednostki](xref:microsoft.quantum.lang-ref.unit)

Operacja do zastosowania do każdego qubitu.


### <a name="register--t"></a>Rejestr: t []

Tablica qubits, na której ma zostać zastosowana dana operacja.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C

Obiekt docelowy, na którym działa operacja.

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. Canon. ApplyToEach](xref:Microsoft.Quantum.Canon.ApplyToEach)