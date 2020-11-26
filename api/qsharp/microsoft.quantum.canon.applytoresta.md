---
uid: Microsoft.Quantum.Canon.ApplyToRestA
title: ApplyToRestA, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToRestA
qsharp.summary: Applies an operation to all but the first element of an array.
ms.openlocfilehash: 34cb5071dd939d0831e39bb8f1670670ae1fad31
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208310"
---
# <a name="applytoresta-operation"></a>ApplyToRestA, operacja

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Stosuje operację do wszystkich elementów oprócz pierwszego elementu tablicy.

```qsharp
operation ApplyToRestA<'T> (op : ('T[] => Unit is Adj), targets : 'T[]) : Unit is Adj
```


## <a name="description"></a>Opis

`op`Ma zastosowanie operacja i Tablica elementów docelowych `targets` `op(Rest(targets))` .

## <a name="input"></a>Dane wejściowe

### <a name="op--t--unit--is-adj"></a>op: t [] => [Jednostka](xref:microsoft.quantum.lang-ref.unit)  jest korektą

Operacja, która ma zostać zastosowana.


### <a name="targets--t"></a>elementy docelowe: t []

Tablica elementów docelowych, z których wszystkie oprócz pierwszej zostaną zastosowane do `op` .



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C

Typ wejściowy operacji, która ma zostać zastosowana.

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. Canon. ApplyToRest](xref:Microsoft.Quantum.Canon.ApplyToRest)
- [Microsoft. Quantum. Canon. ApplyToRestC](xref:Microsoft.Quantum.Canon.ApplyToRestC)
- [Microsoft. Quantum. Canon. ApplyToRestCA](xref:Microsoft.Quantum.Canon.ApplyToRestCA)