---
uid: Microsoft.Quantum.Canon.ApplyToRestA
title: ApplyToRestA, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToRestA
qsharp.summary: Applies an operation to all but the first element of an array.
ms.openlocfilehash: 69001f6c8d65806e7259f2d2f2741d48866daa84
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841263"
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