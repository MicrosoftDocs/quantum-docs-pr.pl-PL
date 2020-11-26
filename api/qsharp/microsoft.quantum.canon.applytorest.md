---
uid: Microsoft.Quantum.Canon.ApplyToRest
title: ApplyToRest, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToRest
qsharp.summary: Applies an operation to all but the first element of an array.
ms.openlocfilehash: fe49361f3c2259960eaa58d47df9b69b30b572a8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208273"
---
# <a name="applytorest-operation"></a>ApplyToRest, operacja

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Stosuje operację do wszystkich elementów oprócz pierwszego elementu tablicy.

```qsharp
operation ApplyToRest<'T> (op : ('T[] => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a>Opis

`op`Ma zastosowanie operacja i Tablica elementów docelowych `targets` `op(Rest(targets))` .

## <a name="input"></a>Dane wejściowe

### <a name="op--t--unit"></a>op: t [] = [jednostka](xref:microsoft.quantum.lang-ref.unit)> 

Operacja, która ma zostać zastosowana.


### <a name="targets--t"></a>elementy docelowe: t []

Tablica elementów docelowych, z których wszystkie oprócz pierwszej zostaną zastosowane do `op` .



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C

Typ wejściowy operacji, która ma zostać zastosowana.

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. Canon. ApplyToRestA](xref:Microsoft.Quantum.Canon.ApplyToRestA)
- [Microsoft. Quantum. Canon. ApplyToRestC](xref:Microsoft.Quantum.Canon.ApplyToRestC)
- [Microsoft. Quantum. Canon. ApplyToRestCA](xref:Microsoft.Quantum.Canon.ApplyToRestCA)