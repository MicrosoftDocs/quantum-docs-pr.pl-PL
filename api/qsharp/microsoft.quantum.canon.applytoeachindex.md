---
uid: Microsoft.Quantum.Canon.ApplyToEachIndex
title: ApplyToEachIndex, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndex
qsharp.summary: Applies a single-qubit operation to each indexed element in a register.
ms.openlocfilehash: 4ce184b34add9238e26f9b35b40ec0bddb23ccf9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717542"
---
# <a name="applytoeachindex-operation"></a>ApplyToEachIndex, operacja

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package [](https://nuget.org/packages/)


Stosuje pojedyncze qubit operacji do każdego indeksowanego elementu w rejestrze.

```qsharp
operation ApplyToEachIndex<'T> (singleElementOperation : ((Int, 'T) => Unit), register : 'T[]) : Unit
```


## <a name="input"></a>Dane wejściowe

### <a name="singleelementoperation--intt--unit"></a>singleElementOperation: ([int](xref:microsoft.quantum.lang-ref.int), t) = [Jednostka](xref:microsoft.quantum.lang-ref.unit)> 

Operacja do zastosowania do każdego qubitu.


### <a name="register--t"></a>Rejestr: t []

Tablica qubits, na której ma zostać zastosowana dana operacja.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C

Obiekt docelowy, na którym działa każda z operacji.

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. Canon. ApplyToEach](xref:Microsoft.Quantum.Canon.ApplyToEach)
- [Microsoft. Quantum. Canon. ApplyToEachIndexA](xref:Microsoft.Quantum.Canon.ApplyToEachIndexA)
- [Microsoft. Quantum. Canon. ApplyToEachIndexC](xref:Microsoft.Quantum.Canon.ApplyToEachIndexC)
- [Microsoft. Quantum. Canon. ApplyToEachIndexCA](xref:Microsoft.Quantum.Canon.ApplyToEachIndexCA)