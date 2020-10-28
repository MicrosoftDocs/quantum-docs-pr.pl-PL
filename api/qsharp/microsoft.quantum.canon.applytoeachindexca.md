---
uid: Microsoft.Quantum.Canon.ApplyToEachIndexCA
title: ApplyToEachIndexCA, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndexCA
qsharp.summary: Applies a single-qubit operation to each indexed element in a register. The modifier `CA` indicates that the single-qubit operation is adjointable and controllable.
ms.openlocfilehash: c5bb61aadbdaab9c74a3dcd418088c532b495ff5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717514"
---
# <a name="applytoeachindexca-operation"></a>ApplyToEachIndexCA, operacja

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package [](https://nuget.org/packages/)


Stosuje pojedyncze qubit operacji do każdego indeksowanego elementu w rejestrze.
Modyfikator `CA` wskazuje, że operacja pojedynczego qubit jest sąsiednia i kontrolowany.

```qsharp
operation ApplyToEachIndexCA<'T> (singleElementOperation : ((Int, 'T) => Unit is Adj + Ctl), register : 'T[]) : Unit
```


## <a name="input"></a>Dane wejściowe

### <a name="singleelementoperation--intt--unit-adj--ctl"></a>singleElementOperation: ([int](xref:microsoft.quantum.lang-ref.int), t) => skorygowania [jednostki](xref:microsoft.quantum.lang-ref.unit) + CTL

Operacja do zastosowania do każdego qubitu.


### <a name="register--t"></a>Rejestr: t []

Tablica qubits, na której ma zostać zastosowana dana operacja.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C

Obiekt docelowy, na którym działa każda z operacji.

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. Canon. ApplyToEachIndex](xref:Microsoft.Quantum.Canon.ApplyToEachIndex)